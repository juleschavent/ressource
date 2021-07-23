# SQL

## Requête SQL
**SELECT** affiche les champs d'un tableau

    SELECT * FROM veste  WHERE couleur_veste LIKE 'rouge'
    AND 
    prix_veste < 20
    AND 
    matiere_veste LIKE 'coton'

**INSERT** ajoute un champ au tableau

    INSERT INTO iphone
    VALUE (null, 750, "large 6.7")

**UPDATE** modifie un champ du tableau 

    UPDATE fruits 
    SET couleur_fruits="vert" 
    WHERE id_fruits = 1

**DELETE** supprime un champ du tableau

    DELETE FROM iphone 
    WHERE id_iphone = 5