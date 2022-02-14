# projetexament
 api
IAI PROJET de validation
Commencer
Installation des dépendances
Python 3.9.7
pip 20.0.2 à partir de /usr/lib/python3/dist-packages/pip (python 3.9)
Suivez les instructions pour installer la dernière version de python pour votre plate-forme dans les documents python

Environnement virtuel
Nous vous recommandons de travailler dans un environnement virtuel chaque fois que vous utilisez Python pour des projets. Cela permet de garder vos dépendances pour chaque projet séparées et organisées. Les instructions pour la configuration d’un environnement virtuel pour votre plate-forme peuvent être trouvées dans les documents python

Dépendances PIP
Une fois que vous avez configuré et exécuté votre environnement virtuel, installez les dépendances en accédant au répertoire et en exécutant :/ProjetExament

pip install -r requirements.txt
or
pip3 install -r requirements.txt
Cela installera tous les packages requis que nous avons sélectionnés dans le fichier.requirements.txt

Dépendances clés
Flask est un framework de microservices backend léger. Flask est nécessaire pour traiter les demandes et les réponses.

SQLAlchemy est la boîte à outils SQL Python et ORM que nous utiliserons pour gérer la base de données sqlite légère. Vous travaillerez principalement dans ProjetExament.py.

Flask-CORS est l’extension que nous utiliserons pour gérer les demandes d’origine croisée de notre serveur frontal.

Exécution du serveur
À partir de l’annuaire, assurez-vous d’abord que vous travaillez à l’aide de l’environnement virtuel que vous avez créé.ProjetExament

Pour exécuter le serveur sous Linux ou Mac, exécutez :

export FLASK_APP=flaskr
export FLASK_ENV=development
flask run
Pour exécuter le serveur sous Windows, exécutez :

set FLASK_APP=flaskr
set FLASK_ENV=development
flask run
La définition de la variable sur détectera les modifications de fichiers et redémarrera automatiquement le serveur.FLASK_ENVdevelopment

Définition de la variable sur dirige flask pour utiliser le répertoire et le fichier pour trouver l’application.FLASK_APPflaskrflaskr__init__.py


Dabord le projet consite à crer un api qui permetra de gerer une biblioteque,donc nous avons possede comme suis

 ## GET/books

GENERAL:
    Cet endpoint retourne la liste des objets livres, la valeur du succès et le total des livres. 

    
EXEMPLE: curl https://bookapi-v1.herokuapp.com/books
        {
    "books": [
        {
            "auteur": "Gege Atakumi",
            "code_ISBN": "979-1-0328",
            "date_publication": "03-02-2022",
            "editeur": "Ki-oon",
            "id": 2,
            "titre": "Jujutsu Kaisen T13"
        },
        {
            "auteur": "Louis Saulnier, Théodore Gringoire",
            "code_ISBN": "978-2-0802",
            "date_publication": "26-02-2022",
            "editeur": "Flammarion",
            "id": 3,
            "titre": "Le répertoire de la cuisine"
        },
        {
            "auteur": "Katia Bricka",
            "code_ISBN": "978-2-8977",
            "date_publication": "25-02-2022",
            "editeur": "Modus Vivendi",
            "id": 4,
            "titre": "La recette parfaite"
        },
        {
            "auteur": "Azychika, Takumi Fukui",
            "code_ISBN": "979-1-0327",
            "date_publication": "03-02-2022",
            "editeur": "Ki-oon",
            "id": 1,
            "titre": "Jujutsu Kaisen"
        }
    ],
    "status_code": 200,
    "success": true,
    "total_books": 4
}
.##GET/books(book_id) GENERAL: Cet endpoint permet de récupérer les informations d'un livre particulier s'il existe par le biais de l'ID.

EXEMPLE: https://bookapi-v1.herokuapp.com/books/3
    {
        "auteur": "Louis Saulnier, Théodore Gringoire",
        "code_ISBN": "978-2-0802",
        "date_publication": "26-02-2022",
        "editeur": "Flammarion",
        "id": 3,
        "titre": "Le répertoire de la cuisine"
    }
. ## DELETE/books (book_id)

GENERAL:
    Supprimer un element si l'ID existe. Retourne l'ID du livre supprimé, la valeur du succès et le nouveau total.

    EXEMPLE: curl -X DELETE https://bookapi-v1.herokuapp.com/books/4
    {
        "id_book": 4,
        "new_total": 3,
        "success": true
    }
. ##PATCH/books(book_id) GENERAL: Cet endpoint permet de mettre à jour, le titre, l'auteur, et l'éditeur du livre. Il retourne un livre mis à jour.

EXEMPLE.....Avec Patch

  {
      "auteur": "Azychika, Takumi Fukui",
      "code_ISBN": "979-1-0327",
      "date_publication": "03-02-2022",
      "editeur": "Ki-oon",
      "id": 1,
      "titre": "Jujutsu Kaisen"
  }
  ```

. ## GET/categories

  GENERAL:
      Cet endpoint retourne la liste des categories de livres, la valeur du succès et le total des categories disponibles. 
  
      
  EXEMPLE: curl https://bookapi-v1.herokuapp.com/categories

      {
  "category": [
      {
          "categorie": "Litterature",
          "id": 1
      },
      {
          "categorie": "Humour",
          "id": 2
      },
      {
          "categorie": "Tourisme et voyage",
          "id": 3
      },
      {
          "categorie": "Histoire",
          "id": 5
      },
      {
          "categorie": "Cuisine",
          "id": 6
      },
      {
          "categorie": "Droit et Economie",
          "id": 7
      },
      {
          "categorie": "Informatique et internet",
          "id": 8
      },
      {
          "categorie": "Sciences sociales",
          "id": 9
      },
      {
          "categorie": "Essais et documents",
          "id": 10
      },
      {
          "categorie": "Religion et spiritualité",
          "id": 11
      },
      {
          "categorie": "Art, musique et cinéma",
          "id": 12
      },
      {
          "categorie": "Bandes Dessinées",
          "id": 4
      }
  ],
  "status_code": 200,
  "success": true,
  "total": 12
}
.##GET/categories(categorie_id) GENERAL: Cet endpoint permet de récupérer les informations d'une categorie si elle existe par le biais de l'ID.

EXEMPLE: https://bookapi-v1.herokuapp.com/categories/6
    {
        "categorie": "Cuisine",
        "id": 6
    }
. ## DELETE/categories (categories_id)

GENERAL:
    Supprimer un element si l'ID existe. Retourne l'ID da la catégorie supprimé, la valeur du succès et le nouveau total.

    EXEMPLE: curl -X DELETE https://bookapi-v1.herokuapp.com/categories/11
    {
        "id_cat": 11,
        "new_total": 10,
        "status": 200,
        "success": true
    }
. ##PATCH/categories(categorie_id) GENERAL: Cet endpoint permet de mettre à jour le libelle ou le nom de la categorie. Il retourne une nouvelle categorie avec la nouvelle valeur.

EXEMPLE.....Avec Patch

  {
      "categorie": "Bandes Dessinées",
      "id": 4
  }

.##GET/books/categories(categorie_id)
GENERAL:
Cet endpoint permet de lister les livres appartenant à une categorie donnée.
Il renvoie la classe de la categorie et les livres l'appartenant.

  EXEMPLE: https://bookapi-v1.herokuapp.com/categories/4/books
{
"Status_code": 200,
"Success": true,
"books": [
    {
        "auteur": "Gege Atakumi",
        "code_ISBN": "979-1-0328",
        "date_publication": "03-02-2022",
        "editeur": "Ki-oon",
        "id": 2,
        "titre": "Jujutsu Kaisen T13"
    },
    {
        "auteur": "Azychika, Takumi Fukui",
        "code_ISBN": "979-1-0327",
        "date_publication": "03-02-2022",
        "editeur": "Ki-oon",
        "id": 1,
        "titre": "Jujutsu Kaisen"
    }
],
"classe": {
    "categorie": "Bandes Dessinées",
    "id": 4
}
}



