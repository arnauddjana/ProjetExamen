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
Une fois que vous avez configuré et exécuté votre environnement virtuel, installez les dépendances en accédant au répertoire et en exécutant :/plants_api

pip install -r requirements.txt
or
pip3 install -r requirements.txt
Cela installera tous les packages requis que nous avons sélectionnés dans le fichier.requirements.txt

Dépendances clés
Flask est un framework de microservices backend léger. Flask est nécessaire pour traiter les demandes et les réponses.

SQLAlchemy est la boîte à outils SQL Python et ORM que nous utiliserons pour gérer la base de données sqlite légère. Vous travaillerez principalement dans ProjetExament.py.

Flask-CORS est l’extension que nous utiliserons pour gérer les demandes d’origine croisée de notre serveur frontal.

Exécution du serveur
À partir de l’annuaire, assurez-vous d’abord que vous travaillez à l’aide de l’environnement virtuel que vous avez créé.plants_api

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



