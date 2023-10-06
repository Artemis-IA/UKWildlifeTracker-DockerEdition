# Projet Docker : Mammals API avec MongoDB, FastAPI et Streamlit 🐾🐬


Ce projet Docker contient trois containers : un MongoDB pour stocker les données sur les mammifères, un serveur FastAPI pour fournir une API pour accéder à ces données, et une application Streamlit pour visualiser les observations des mammifères sur une carte. 🚀

## Comment Démarrer 🛠️

Assurez-vous d'avoir Docker installé sur votre machine.

1. Clonez ce référentiel sur votre machine locale :
    ```bash
    git clone https://github.com/Artemis-IA/UKWildlifeTracker-DockerEdition.git
    cd ./UKWildlifeTracker-DockerEdition
    ```
2. Décompressez le CSV contenu dans Mammal.zip et mettez le dans le répertoire ./mongo_seed


4. Créez un fichier `.env` dans le répertoire racine avec les variables d'environnement nécessaires :
    ```plaintext
    MONGO_INITDB_ROOT_USERNAME=root
    MONGO_INITDB_ROOT_PASSWORD=example
    MONGO_INITDB_DATABASE=webapi
    DATABASE_URI=mongodb://root:example@mongo:27017/webapi?authSource=admin
    ```
    

5. Construisez et exécutez les containers Docker en utilisant Docker Compose :
    ```bash
    docker-compose up --build
    ```

Les services seront démarrés et accessibles aux ports suivants :
- MongoDB: `27017`
- FastAPI: `8002`
- Streamlit: `8501`

## Utilisation 🚀

### 1. FastAPI - Accès à l'API 🌍

L'API FastAPI est accessible à l'adresse `http://localhost:8002`.

- **Endpoint pour toutes les espèces :** `http://localhost:8002/all_species/`
- **Endpoint pour une espèce spécifique :** `http://localhost:8002/species/{species_id}`

### 2. Streamlit - Visualisation des Données 🗺️

L'application Streamlit est accessible à l'adresse `http://localhost:8501`.

1. **Sélectionnez un animal :** Choisissez un animal dans la liste déroulante.
2. **Sélectionnez une année :** Choisissez une année parmi les années disponibles.
3. **Visualisez les données :** Une carte affichera les observations de l'animal sélectionné pour l'année choisie.

## Structure des Fichiers 📂

- **`app/` :** Contient le fichier CSV avec les données des mammifères et le script Streamlit pour la visualisation.
- **`mongo_seed/` :** Contient le fichier CSV utilisé pour initialiser la base de données MongoDB.
- **`server/` :** Contient le code FastAPI pour l'API des mammifères et les scripts de connexion à la base de données.

## Remarques 📝

- Assurez-vous d'avoir les données nécessaires dans le fichier CSV (`National Mammal Atlas Project Clean.csv`) pour que l'application fonctionne correctement.
- Les données sont accessibles via l'API FastAPI et peuvent être visualisées avec l'application Streamlit.
- Voici les credentials par défaut du dotenv (.env) :

**Profitez de votre exploration des mammifères avec notre application Dockerisée ! 🐾✨**
