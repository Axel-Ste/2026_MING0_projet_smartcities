# Tables
- nichoirs : Contient les informations des différents nichoirs.
- images : Contient les images en Binary Large Objets captées pas le TimerCam
- batteries : Contient les relever de batteries des nichoirs
- utilisateurs : Contient les utilisateurs de l'applications

## Relations
- utilisateurs et nichoirs : n pour n (un nichoir partager à plusieurs personnes)
- nichoirs et images : 1 pour n
- nichoirs et batteries 1 pour n

## Contraintes
- relations utilisateurs et nichoirs : Un seul propriétaire dans la relation