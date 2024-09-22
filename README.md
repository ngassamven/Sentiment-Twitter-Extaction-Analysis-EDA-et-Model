# 🐦 Analyse de Sentiments sur des Tweets
Ce projet vise à analyser des tweets pour identifier le sentiment exprimé (positif, négatif ou neutre). L'objectif principal est d'extraire des segments de texte spécifiques de chaque tweet qui représentent le mieux son sentiment, et d'évaluer la similarité entre les textes originaux et les extraits sélectionnés.
# Installation
Pour configurer le projet, assure-toi d'avoir les bibliothèques suivantes :
bash
Copier le code
pip install numpy pandas matplotlib seaborn plotly nltk wordcloud 
De plus, vérifie que ces bibliothèques sont disponibles dans ton environnement :

- nltk pour le prétraitement des textes.
- tqdm pour les barres de progression.
- PIL pour le traitement d'images.
- spacy (actuellement commentée dans le script, mais utile pour d'autres tâches NLP).
# Utilisation
- Importer les bibliothèques nécessaires :

matplotlib, seaborn et plotly pour la visualisation des données.
nltk et re pour le nettoyage et la manipulation des textes.
Pandas pour la gestion des données.
Charger les jeux de données (train.csv, test.csv, sample_submission.csv) et effectuer un prétraitement de base, comme la suppression des données manquantes.

Les principales tâches sont :

Analyse Exploratoire des Données (EDA) : visualiser la distribution des sentiments et la fréquence des mots.
Calcul de la similarité de Jaccard pour mesurer la similitude entre le texte original et le texte sélectionné.
Création de nuages de mots pour les tweets positifs, négatifs et neutres.
Extraction des mots uniques dans les tweets selon leur sentiment.
Visualiser les résultats à l'aide de diagrammes à barres, de graphiques en entonnoir et d'estimations de densité par noyau (KDE) pour analyser la différence de nombre de mots et la distribution des scores de Jaccard.

# Structure du projet
bash
Copier le code
.
├── README.md
├── train.csv
├── test.csv
├── sample_submission.csv
├── main_script.ipynb  # Notebook Jupyter avec analyse détaillée.
└── images/            # Dossier pour stocker les visualisations et nuages de mots générés.
# Données
**Colonnes du jeu de données :** 
- textID : ID unique pour chaque tweet.
- text : Le tweet original.
- selected_text : La portion du tweet qui reflète le mieux le sentiment.
- sentiment : Le sentiment global du tweet (positif, négatif, neutre).
# Prétraitement :
- Nettoyage des textes : suppression de la ponctuation, des liens et des caractères inutiles.
- Calcul du nombre de mots dans le texte original et dans le texte sélectionné.
- Utilisation de la similarité de Jaccard pour mesurer la similitude entre text et selected_text.
# Fonctionnalités
- Similarité de Jaccard : Fonction pour calculer la similarité entre deux séquences de texte.
- Analyse de Fréquence des Mots : Identification des mots les plus courants selon les différentes catégories de sentiment.
# Visualisations :
  - Distribution des sentiments via des diagrammes en entonnoir et des graphiques à barres.
  - Nuages de mots pour représenter visuellement les mots fréquents dans chaque catégorie de sentiment.
  - Graphiques KDE et histogrammes pour comparer le nombre de mots et les scores de Jaccard dans différents sentiments.
# Résultats
La majorité des segments de texte sélectionnés sont beaucoup plus courts que les tweets originaux.
Les tweets positifs et négatifs ont des modèles d'utilisation de mots différents, avec des mots comme "love", "happy" et "good" fréquents dans les tweets positifs, tandis que "miss", "sad" et "hate" sont dominants dans les tweets négatifs.
La similarité de Jaccard est généralement plus élevée dans les tweets neutres que dans les tweets positifs ou négatifs.
# Références
Le code repose sur des bibliothèques Python telles que nltk, matplotlib, seaborn et plotly. Une fonction de similarité de Jaccard est également utilisée pour comparer le texte original et le texte sélectionné.
