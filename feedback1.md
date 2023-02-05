



// Optimisation d'affichage 
Dans la liste des cartes, tu peux ajouter une information interessante :  la carte est-elle dans le deck  ( inDeck ) ? 
En utilisant la méthode map - dans mainController.js ligne 6

let cards = await dataMapper.getAllCards();
const session_cards =  req.session.cards ?? [];
cards = cards.map(card=> {
    card.inDeck= session_cards.find(c=> card.id==c.id) !== null; 
    return card;
})

 Tu peux ensuite mettre un opérateur ternaire (?:) pour afficher soit le bouton Ajouter ou Enlever du Deck,  en fonction du nouvel attribut inDeck.   


// card-item.ejs 
Dans ce cas utilise l'opérateur fusion plutôt que if/else  
    <p>Element: <%= card.element ?? "empty" %></p>