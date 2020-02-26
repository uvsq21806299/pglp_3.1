# pglp_3.1

1)  Non, cette classe de respecte pas SRP car  la classe Employe a 2 responsabilités différentes: calculSalaire()
et afficheCoordonee()


2)  Si on change la méthode de calcul de salaire,  cela va impacter la classe  car il y a une dépendance entre les 2 méthodes 


3) Si l'affichage est remplacé par  le stockage dans un fichier CSV, la clase Employe  va aussi changer car elle change de dépendance avec le module d'affichage  (Principes d'inversion de dépendance)


4)  Solution respectant SRP:
 on crée une interface  pour le calcul de salaire: 
  interface calculSalaire(){
 
