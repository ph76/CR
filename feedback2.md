
//deckController 
const client = require('./database');
cette variable n'est pas utilisée, donc tu peux la supprimer 


ligne 14
Vérifie d'abord si la carte n'est pas dans le deck avec l'id (l.16), cela évite d'interroger le serveur le cas échéant.


// dataMapper
const client = require('./database');
const database = require('./database');
Inutile d'instancier le même objet 2 fois. utilise database.

 : fonction getElements 
Cette fonction n'est pas optimale
// Recherche des cartes par éléments : 
Ton procédé : 
    1. Tu fais une requête  SQL   (coté server)qui va récupérer les cartes qui ont un élément (non null).. 
     -Pourquoi non null ?? Car si on sélectionne "aucun" la liste sera vide.
    2. Tu effectues un filtre sur l'attribut element (coté client) aprèd l'avoir récupéré. 
    -  Tu aurais du faire une requête entièrement (coté server) qui filtre directement l'élément sélectionné avec la clause 'element =`` ', il faut juste faire attention lorsque que l'élément est 'aucun' on chanque la clause en 'element is NULL'



// Fonctionnalités non réalisées :
   - Supprimer la carte du deck
   - Bonus