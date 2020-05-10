# Mini-projet

## Barres de progression
  
### On crée la première barre en HTML/ CSS 
code HTML:

        <div id="barre_progress_HTML>
          <p class="baba">Barre de progression HTML/CSS</p>
          <div class="progress_html">
            <div class="html_bar"></div>
          </div>
        </div>
        
On emboîte deux 'div' l'un dans l'autre afin de créer la barre de progression et la barre de valeur.
On les met en forme avec la feuille de style.

Code CSS pour l'ossature de la barre:
        
        .Progress_html { 
            width: 250px; 
            background-color: #ddd; 
            border-radius: 10px;}
            
Code CSS pour la barre de valeur:

        .html_bar { 
            width: 1%; 
            height: 35px; 
            background-color: #4CAF50; 
            text-align: center; 
            line-height: 32px; 
            color: black; 
            border-radius: 10px;}
  
Ensuite, on utilise la règle @keyframes afin de dynamiser la barre et séquencer l'animation qui augmentera la barre et changer la couleur de celle-ci selon l'étape atteinte (en %).

         @keyframes progress_keyframe { 
      0%{
          width:0%;
      }
      10%{
          background-color: #857800;
      }
      25%{
          background-color:pink;
      }
      50%{
          background-color: turquoise;
      }
      75%{
          background-color: gray;
      }
      100%{
          width:100%}}
          
Enfin, on va utiliser l'événement :hover pour que la barre commence à progresser lorsque la souris passera sur celle-ci.
La propriété 'animation' enclenchera la règle @keyframes sur une durée de 5 secondes en inversant le sens.

      .html_bar:hover{ 
            width:1%;
            animation: progress_keyframe 5s reverse; }
            

### On crée ensuite la barre de progression en HTML/CSS et JS

      <p>Barre de progression HTML/CSS/JS</p>
        <div id="Progress_Status"> 
            <div id="myprogressBar"><strong>0%</strong></div> 
          </div> 
          
Comme pour la première barre, on crée deux balises 'div' emboîtées, on ajoute juste une valeur "0%" dans la barre de valeur pour représenter le pourcentage.Les feuilles de style CSS restent quant à elles, identiques.

      #Progress_Status {  
    width: 250px; 
    background-color: #ddd; 
    border-radius: 10px;} 
      #myprogressBar { 
    width: 1%; 
    height: 35px; 
    background-color: #4CAF50; 
    text-align: center; 
    line-height: 32px; 
    color: black; 
    border-radius: 10px;}
    
On crée le script en JS pour faire fonctionner notre barre de progression. Pour cela, on va créer une première fonction update():

      function update() { 
                let element = document.getElementById("myprogressBar"), // On accède 
                width = 0,
                numColor = 0,
                identity = setInterval(scene, 500); }
                
On crée une variable 'identity' qui fera intervenir la méthode 'setInterval()' pour déclencher la fonction scene() à une intervalle de 500 ms que l'on va créer dans l'étape suivante et qui sera implémentée dans la première: update()

      function scene() { 
                     var colors = ["white","#387877","#977744","blue","red","blue","yellow","#707070","green","brown"];
                     if (width >= 100) { 
                        clearInterval(identity); 
                      } else { 
                        width+=10;  
                        numColor += 1;                                                     
                        element.style.width = width + "%";
                        element.style.backgroundColor = colors[numColor];
                        element.innerHTML = `${width} %`;}}

Dans cette fonction, nous allons créer un tableau qui réunira une liste de couleurs. Ensuite, on crée une conditionqui signifie que SI la variable 'width' >= 100,nous arrêtons l'exécution du timer de setInterval(), SINON, nous incrémentons la valeur de 'width' de 10, ainsi que la couleur; nous mettons ensuite à jour dans la feuille de style, la largeur et le coloris. Et nous terminons avec la propriété innerHTML, qui fera évoluer le pourcentage de la barre.

      <div id="Progress_Status" onclick="update()"> 
      
Enfin, nous ajoutons l'événement 'click' qui appellera la fonction update() à chaque fois que l'utilisateur cliquera sur la barre.
