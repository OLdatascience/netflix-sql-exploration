# 🎬 Netflix Data Exploration with SQL & Python

Analyse complète du catalogue Netflix à l’aide de **PostgreSQL**, **Pandas**, **Plotly** et **Jupyter Notebook**.  

---

## Technologies utilisées

- PostgreSQL + pgAdmin
- Python (Pandas, SQLAlchemy, Plotly)
- Jupyter Notebook


---

## Fonctionnalités SQL couvertes

- Clauses `SELECT`, `WHERE`, `GROUP BY`, `ORDER BY`, `LIMIT`
- Agrégations : `COUNT`, `AVG`, `MAX`, `MIN`
- Fonctions de nettoyage : `REPLACE()`, `CAST()`, `REGEXP_REPLACE()`, `UNNEST()`
- Requêtes avancées : analyse de genres, durée moyenne, pays les plus producteurs, etc.


##  Résultats observés

-  70% des titres sont des films, 30% des séries
-  Pic de sorties en 2019
-  Les USA dominent le contenu, l’Inde et le Royaume-Uni suivent
-  Les séries les plus longues vont jusqu’à 15 saisons


##  Données

Les données proviennent du dataset [Netflix Movies and TV Shows on Kaggle](https://www.kaggle.com/datasets/shivamb/netflix-shows) (fourni ici via `netflix_titles.csv`).

---

##  Étapes d'installation

### Créer la base de données PostgreSQL

- Ouvrez **pgAdmin**
- Créez une base appelée **`netflix_db`**
- Créez la table et importez le fichier `netflix_titles.csv` avec la commande SQL suivante :

```sql
-- Création de la table
CREATE TABLE netflix_titles (
    show_id TEXT,
    content_type TEXT,
    title TEXT,
    director TEXT,
    cast_name TEXT,
    country TEXT,
    date_added TEXT,
    release_year INT,
    rating TEXT,
    duration TEXT,
    listed_in TEXT,
    description TEXT
);

-- Import des données
COPY netflix_titles 
FROM 'chemin/vers/netflix_titles.csv' 
DELIMITER ',' 
CSV HEADER;
```

---

### Créer un fichier `.env`

Créez un fichier `.env` dans le même dossier que le notebook :

```
DB_HOST=localhost
DB_PORT=5432
DB_NAME=netflix_db
DB_USER=postgres
DB_PASSWORD=votre_mot_de_passe_pgadmin
```
Ce fichier est ignoré par Git grâce au fichier .gitignore
---

### Créez un environnement virtuel & installer les dépendances

Ouvrez un Anaconda prompt et entrez y les commande suivantes : 

conda create -n netflix_env python=3.11
conda activate netflix_env
pip install -r requirements.txt
jupyter notebook

---

### Lancer le projet

Ouvrez le fichier `Netflix.ipynb` dans le navigateur.

