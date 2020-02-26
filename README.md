# pglp_3.1

1)  Non, cette classe de respecte pas SRP car  la classe Employe a 2 responsabilités différentes: 
*Calcul du salaire : calculSalaire()
*Affichage des coordonées : afficheCoordonee()


2)  Si on change la méthode de calcul de salaire,  cela va impacter la classe  car il y a une dépendance entre les 2 méthodes 


3) Si l'affichage est remplacé par  le stockage dans un fichier CSV, la clase Employe  va aussi changer car elle change de dépendance avec le module d'affichage  (Principes d'inversion de dépendance)


4)  Solution respectant SRP:
Comme solution, on peut laisser soit calculSalaire(), soit affichageCoordonee() dans la classe Employe
   - on crée un classe qui calcul le salaire
   
    public class CalculSalaire {
         public double calculSalaire(){
             //traitement
             return salaire;
         }
     }
         
   - ensuite la classe Employe va hériter de la classe CalculSalaire
   
    public class Employe extends CalculSalaire {
	      private String nom;
	      private String adresse;
       
       public void afficheCoordonnees() {
           System.out.println(nom + ","  + adresse);
       }
       
       @override
       public double calculSalaire(){
           // le nouveau traitement 
       }
    }
      
