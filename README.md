# gestion-stock
Application de gestion de stock en Java 
+-------------------+
|  Projet GESTION3  |
+-------------------+
        |
        v
+-------------------+
|      src/         |  (Code source)
+-------------------+
        |
        v
+-------------------+
|     com.monapp/   |  (Package racine)
+-------------------+
        |
   +------------+------------+
   |                         |
+--------+              +------------+
| controller/            | model/     |
+--------+              +------------+
   |                         |
+-------------------+   +-------------------+
| MouvementController|   | DatabaseConnection |
+-------------------+   +-------------------+
| ProduitController  |   | MouvementStock     |
+-------------------+   | Produit            |
                        +-------------------+
                        | MouvementStockDAO  |
                        | ProduitDAO         |
                        | ReportGenerator    |
                        | MainApp            |
                        +-------------------+
        |
        v
+-------------------+
|   resources/      |
+-------------------+
        |
        v
+-------------------+
|    views/         |
+-------------------+
        |
  +-----------+-----------+
  |                       |
+--------+            +---------+
| mouvements.fxml     | produit_view.fxml |
+--------+            +---------+
        |
+-------------------+
| report_template.jrxml |
+-------------------+
1. Projet GESTION3 :
C'est le projet global, contenant tous les fichiers et dossiers associés à l'application.

2. src/ (Code source) :
Ce dossier contient tout le code source de l'application. C'est là où se trouvent les fichiers Java qui vont définir la logique de ton application.

3. com.monapp/ (Package racine) :
C'est le package principal (racine) de ton application. En Java, l'organisation des classes et des fichiers se fait souvent par packages pour éviter les conflits de noms et pour structurer le code de manière logique.

A l'intérieur de ce package, il y a deux sous-dossiers principaux :

a. controller/ (Contrôleurs) :
Ce dossier contient les classes contrôleurs de l'application. En architecture MVC (Modèle-Vue-Contrôleur), les contrôleurs sont responsables de la gestion de l'interaction entre la vue (UI) et le modèle (les données). Ils contiennent la logique pour réagir aux actions de l'utilisateur.

MouvementController.java : C'est un contrôleur qui gère tout ce qui concerne les mouvements de stock.

ProduitController.java : Ce contrôleur gère tout ce qui concerne les produits.

b. model/ (Modèles et DAO) :
Ce dossier contient les modèles de données et les DAO (Data Access Objects) qui permettent d'interagir avec la base de données.

DatabaseConnection.java : Une classe qui gère la connexion à la base de données.

MouvementStock.java : C'est un modèle représentant un mouvement de stock (par exemple, un ajout ou une suppression de produits dans un entrepôt).

MouvementStockDAO.java : Une classe qui gère l'accès aux données des mouvements de stock dans la base de données.

Produit.java : Un modèle représentant un produit (avec ses caractéristiques comme nom, prix, quantité, etc.).

ProduitDAO.java : Une classe qui gère l'accès aux données des produits dans la base de données.

ReportGenerator.java : Une classe qui génère des rapports, probablement pour afficher des informations sur les stocks ou les produits. Elle est liée à JasperReports (un outil pour générer des rapports).

MainApp.java : La classe principale de l'application qui contient probablement le point d'entrée (public static void main()) et initialise l'application.

4. resources/ (Ressources) :
Ce dossier contient toutes les ressources nécessaires pour le projet, comme les fichiers de configuration, les vues, et les rapports.

a. views/ (Vues) :
Ce dossier contient les fichiers FXML, utilisés par JavaFX pour définir l'interface graphique (UI) de l'application. FXML est un langage basé sur XML qui permet de définir la structure de l'interface utilisateur de manière déclarative.

mouvements.fxml : La vue qui permettra à l'utilisateur de voir et interagir avec les mouvements de stock.

produit_view.fxml : La vue pour afficher et gérer les produits.

b. report_template.jrxml :
Ce fichier est un modèle de rapport utilisé par JasperReports. Il définit la structure d'un rapport (par exemple, un rapport sur les produits ou les mouvements de stock). Ce modèle sera utilisé pour générer des rapports dynamiques avec des données provenant de la base de données.

5. Interaction entre les parties :
Contrôleurs (controller/) : Lorsqu'un utilisateur interagit avec l'interface (par exemple, en cliquant sur un bouton ou en remplissant un formulaire), les contrôleurs prennent en charge l'événement, manipulent les données (via les modèles), et mettent à jour la vue.

Modèles (model/) : Les modèles représentent les données de ton application, comme les produits ou les mouvements de stock. Ils contiennent souvent des informations que tu récupères ou modifies dans la base de données. Les DAO sont responsables de l'accès aux données (ajouter, supprimer, modifier, ou récupérer des informations dans la base de données).

Ressources (resources/) : Les ressources incluent les fichiers FXML pour les vues (l'interface utilisateur) et le fichier JRXML pour générer des rapports. Ces ressources sont utilisées par ton application pour afficher les informations et générer des rapports à partir des données.
