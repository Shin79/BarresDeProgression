# Mini-projet

## Barres de progression
  
<!DOCTYPE html>
<HTML>
    <head>
        <meta charset="utf-8"/>
        <meta name="description" content="barre de progression"/>
        <title>Barres de progression</title>
        <link rel="stylesheet" href="progressBar.css"/>
    </head>
    <body>
        <!--La barre de progression en HTML et CSS-->
        <div id="barre_progress_HTML">
            <p class="baba">Barre de progression HTML/CSS</p>
            <div class="Progress_html">
                <div class="html_bar"></div>
            </div>
        </div>
        <!--La barre de progression avec <progress>-->
        <div id="barre_progress_JS">
            <p>Barre de progression HTML/CSS/JS</p>
            <progress class="progressBarre" max="100" value="45">%</progress>
            <span class="pourcentage"></span>
        </div>
        <!--La barre de progression en HTML,CSS et JavaScript-->
        <p>Barre de progression HTML/CSS/JS</p>
        <div id="Progress_Status" onclick="update()"> 
            <div id="myprogressBar"><strong>0%</strong></div> 
          </div> 
        
        <script>
            let barre = document.getElementsByClassName("progressBarre")[1],
            prc = document.getElementsByClassName("pourcentage")[1];
            
            barre.addEventListener("click",function(event){
                var barre = document.getElementsByClassName("progressBarre")[1];
                barre.value += 1;
                prc.innerHTML= barre.value + " %";
                if (barre.value >= 100){
                    return barre.value=0;
                }
            })
                
            /*J'ajoute le code JS pour dynamiser la barre de progression*/
            function update() { 
                let element = document.getElementById("myprogressBar"), // On accède 
                width = 0,
                numColor = 0,
                identity = setInterval(scene, 500); // Je crée une variable identity qui fait intervenir la méthode setInterval pour déclenche la fonction scene à une intervalle de 500ms
                 function scene() { 
                     var colors = ["white","#387877","#977744","blue","red","blue","yellow","#707070","green","brown"]; // Je crée un tableau avec 10 couleurs différentes
                     if (width >= 100) { 
                        clearInterval(identity); // SI la barre est >=100, j'arrête l'exécution du timer de setInterval
                      } else { 
                        width+=10;  
                        numColor += 1;                                                     
                        element.style.width = width + "%";
                        element.style.backgroundColor = colors[numColor];
                        element.innerHTML = `${width} %`;
                // SINON, j'incrémente la valeur de width de 10, ainsi que la couleur.
                // Je mets à jour également dans la feuille de style, la largeur, le coloris.
                // Enfin, je fais évoluer le pourcentage inclus dans la barre.

        } 
  } 
            
                
            }
        </script>
    </body>
</HTML>
