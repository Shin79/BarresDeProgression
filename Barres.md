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
code CSS pour l'ossature de la barre:
        
        .Progress_html {  /*Ce code CSS va permettre de configurer la barre de progression*/
            width: 250px; 
            background-color: #ddd; 
            border-radius: 10px;}
            
code CSS pour la barre de valeur:

        .html_bar { /*Ce code correspond à la barre de valeur*/
            width: 1%; 
            height: 35px; 
            background-color: #4CAF50; 
            text-align: center; 
            line-height: 32px; 
            color: black; 
            border-radius: 10px;}
  
  
