
# Correction MCD 
- Les relations que tu définis entre les entités doivent etre représentées par au moins un attribut commun! par exemple user_id devrait être présent dans l'entité adresse
- ce qui amène à la deuxième remarque aussi importante, nomme l'attribut qui identitie ton entité (id) différemment simplement {nom de l'entité}_id.
- Pour les relations entre les entités, utilise des symboles non rectangles (arrondis par exmeple)
- si l'utilisateur peut avoir plusieurs adresses de livraison alors il faut qu'une de ces adresses soit lié à ses commandes
-  Quant aux likes cela peut être une entité intermédiaire qui relie le user et le produit, ou alors on a une relation many to many et non pas 1,1 pour les 2 comme tu avais écrit.  


## USER 
- user_id
- email
- password


## Entité ADDRESS
- address_id
- adress
- city
- postal_code
- user_id     (RELATION 1,1)

## PRODUCT
- product_id
- name
- description
- mug_type
- amount

## ORDER
- order_id
- product_id  (RELATION 1,1)
- user_id  (RELATION 1,1)
- address_id (RELATION 1,1)
- status


## LIKES
- like_id
- user_id
- product_id
- created
