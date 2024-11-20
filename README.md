J'ai utilisé ce montage pour mes précédentes moto, R1100 et R1150.  
Pour ma R1200 de 2009, j'ai utilisé 2 modules car les 2 injecteurs sont indépendants, le temps de réaliser une version pour 2 injecteurs.

Le schéma se trouve dans le fichier [schema.pdf](https://github.com/user-attachments/files/17691398/schema.pdf)
Le microcontrôleur utilisé est un PIC16F628 (le 16F627 convient aussi).  

Son alimentation en 5V est confiée à un régulateur 78L05.  
Il y a aussi un afficheur 7 segments, un bouton poussoir, et un transistor IRF540N pour la commande de l'injecteur à la place du calculateur.  
La résistance R1 simule la présence de l'injecteur pour le calculateur, et on récupère le signal pour mesurer la longueur de l'injection. 

L'afficheur affiche les chiffres entre 0 et 9, et un autre symbole le temps du démarrage. Quand on roule à l'essence, avec le bouton poussoir, règler pour afficher 0 car le temps d'injection ne doit pas être prolongé.  
Pour les chiffres de 1 à 9, il faut multiplier la valeur affichée par 3 pour connaitre le pourcentage de prolongation de l'injection.  
Exemple :  
- En été, la valeur que j'utilise est 24%, donc je me mets sur 8 car 3 x 8 = 24.  
- En hiver, c'est plutôt 6 (soit 18%) car il y a plus d'essence dans l'E85. 
   
La valeur est mémorisée à chaque changement, donc elle est reprise au démarrage suivant.  
Pendant le temps du démarrage qui dure quelques secondes, le temps d'injection est doublé.  
Plus il fait froid, plus ce temps est allongé par la présence de la thermistance TH1.  
Cablage :  
- Le +12V est pris sur l'un des 2 fils de l'injecteur, c'est un 12V présent quand le contact est mis.
- La masse est prise sur la borne moins de la batterie.
L'autre fil de l'injecteur est coupé :
- le côté qui va au calculateur est branché à l'entrée ECU du module,
- et l'autre nommé INJ va à l'injecteur.  

Le fichier de programmation du PIC est 16F628.HEX.  

N'hésitez pas à me contacter si vous avez des questions.  

![E85x1-1](https://github.com/user-attachments/assets/95a4752e-2688-423d-af8b-d1cac8cd67ed)  

![E85x1-2](https://github.com/user-attachments/assets/23f46e19-5739-4d98-880b-a275d34dd45b)

