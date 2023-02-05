
Dans une page Web par exemple, la méthode fetch est un des outils que l'on utilise pour communiquer avec des serveurs/apis, pour recueillir des informations, ou déclencher une action sur le serveur sans avoir à envoyer un formulaire, ce qui obligerait à ce que  la page se rafraîchisse. On l'utilise notamment dans les requêtes AJAX, ce système permet de créer du dynamisme dans une page web sans avoir à rafraîchit la page, gain de temps, de traffic de données etc.

La fonction fetch envoie une requête à une url donnée et peut envoyer des données complémentaire en GET (dans l'url),POST (dans le body) et d'autres modes. C'est une fonction asynchrone ou (Promesse) elle fonctionne en 2 temps, c'est pratique car elle ne bloque pas le système - elle crée un processus en parallèle, et son résultat est géré par une autre fonction.

Un exemple avec le projet actuel : tu peux réaliser une recherche plus dynamique ou les résultats s'afficheraient en dessous de tes options de recherche, sans réactualisation dse la page, de cette manière tu peux modfifier tes options de recherche plus rapidement !

pour cela il suffirait pour la recherche par élément, de détourner le submit par un bouton onclick vers une fonction avec le contenu suivant :
// tu enleves le footer et le header de ta route search/element
// tu places une div en-dessous avec l'id "results"
// tu récupères element avec document.getElementById("element").value
const searchByElement = function(element){

fetch("/search/element?element=" + encodeURIComponent(element),

).then(result=>result.text())
.then(html=>{  
   document.getElementById("results").innerHTML=html
     })
