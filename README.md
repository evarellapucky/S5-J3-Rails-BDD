# Projet : Des app Rails avec BDD et Model - Chinook music


## Description 

Exercice : A partir d'une BDD, répondre aux question ci-dessous.

Ce ReadMe présente les requêtes effectuées.


## Questions 

### Niveau failce
- Quel est le nombre total d'objets Album contenus dans la base (sans regarder les id bien sûr) ? ==>`Album.count`

-  Qui est l'auteur de la chanson "White Room" ? ==> `Track.find_by(title: "White Room").artist`

- Quelle chanson dure exactement 188133 milliseconds ? ==> `Track.find_by(duration: "188133").title`

- Quel groupe a sorti l'album "Use Your Illusion II" ? ==> `Album.find_by(title: "Use Your Illusion II").artist`


### Niveau Moyen
- Combien y a t'il d'albums dont le titre contient "Great" ? ==> `Album.where("title like ?", "%great%").count`

- Supprime tous les albums dont le nom contient "music". ==> `Album.where("title LIKE ?", "%music%").destroy_all`

- Combien y a t'il d'albums écrits par AC/DC ? ==> `Album.where(artist: "AC/DC").count`

- Combien de chanson durent exactement 158589 millisecondes ? ==> `Track.where(duration: 158589).count`

### Niveau Difficile

- puts en console tous les titres de AC/DC. ==>
    `Track.where(artist: "AC/DC").each do |tracks| puts tracks.title end`

- puts en console tous les titres de l'album "Let There Be Rock". ==> `Track.where(album: "Let There Be Rock").each do |tracks| puts tracks.title end`

- Calcule le prix total de cet album ainsi que sa durée totale. ==> `Track.where(album: "Let There Be Rock").sum(:price)`

- Calcule le coût de l'intégralité de la discographie de "Deep Purple". ==> `Track.where(artist: "Deep Purple").sum(:price)`

- Modifie (via une boucle) tous les titres de "Eric Clapton" afin qu'ils soient affichés avec "Britney Spears" en artist. ==> `Track.where(artist: "Eric Clapton").each do |track| track.update(artist: "Britney Spears") end`


