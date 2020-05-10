# Mini-projet

## Barres de progression
  
### On crée la première barre en HTML/ CSS et JS
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
