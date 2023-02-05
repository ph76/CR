router.js : inutile d'inclure express-session, on ne l'intègre que pendant l'instanciation du server dans index.js

//Affichage des cartes
cardList.ejs :
(l.11) cette balise est en trop </a> et ligne (l.16) </a> ne sert à rien...
le nom de chaque carte ne doit appaître qu'une fois ...

// Affichage des détails d'une carte :

1. dans mainController.js , la fonction cardPage doit afficher UNE carte, représentée par la varibale oneCard, elle est envoyée en attribut dans ton template avec le même nom (l.29)
2. dans cardDetails.ejs :
   (l.8) Nous n'avons pas besoin de faire de boucle étant donné que tu dois affciher UNE seule carte  -> le for est inutile, de plus les variables utilisées ne sont pas bonnes... car tu envoies uniqement oneCard, donc c'est oneCard que l'on doit retrouver ici à la place des occurences  'card' .  D'ou l'erreur affichée  

//dataMapper.js

- ta fonction getCardByElement (bien qu'elle n'est pas de paramètre element...) aurait du être utilisée pour ton controleur searchController à l aplace de cardElement. Le temps a dû te manquer ....
- d'autre part (searchController.js l.10) le parametre element n'existe car ta route est mal écrite  -> router.get('/search/element',...   au lieu de  router.get('/search/:element',

 Pour éviter la configuration spéciale de visual studio code Rajoute dans le .gitignore  : .vscode !!

   Fonctionnalité non réalisées :
    - Ajout suppression de carte dans le deck
    - Détails d'une carte
    - le deck
    - les bonus
