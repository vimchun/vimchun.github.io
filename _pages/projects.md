---
title: "Projets"
layout: single
permalink: /projects/
author_profile: true
excerpt: "Projets fil rouge pendant mes formations"
header:
  overlay_image: /images/overlay_image.jpeg
  overlay_filter: 0.7  # 0 (opaque) -> 1 (transparent)
---

# 📊 Projet Data Engineer (2025)

**Analyse des offres d’emploi de la data et de la tech en France**


🖼️ <u>Galerie de screenshots</u>

  <!-- <div style="max-width: 400px; margin: 0 auto;">
    <video controls muted style="width: 100%; height: auto;">
      <source src="/videos/project-DE-slideshow.mp4" type="video/mp4">
    </video>
  </div> -->



(ℹ️ Cliquez sur une vignette pour l'afficher en plein écran)


<table>

  <tr>
    <td>Airflow</td>
    <td>
      <a href="../images/projet_DE/airflow_1.png" title="Airflow : 2 DAGs pour l'ETL">
        <img src="../images/projet_DE/airflow_1.png" alt="vignette" style="width: 80px; border: 1px solid black;">
      </a>
      <a href="../images/projet_DE/airflow_2.png" title="Airflow : version 3.0">
        <img src="../images/projet_DE/airflow_2.png" alt="vignette" style="width: 80px; border: 1px solid black;">
      </a>
    </td>
  </tr>

  <tr>
    <td>FastAPI</td>
    <td>
      <a href="../images/projet_DE/fastapi_1.png" class="image-popup" title="FastAPI : toutes les APIs">
        <img src="../images/projet_DE/fastapi_1.png" alt="vignette" style="width: 82px; border: 1px solid black;">
      </a>
      <a href="../images/projet_DE/fastapi_2.png" class="image-popup" title="FastAPI : récupère les attributs ajoutés issus des transformations">
        <img src="../images/projet_DE/fastapi_2.png" alt="vignette" style="width: 82px; border: 1px solid black;">
      </a>
      <a href="../images/projet_DE/fastapi_3.png" class="image-popup" title="FastAPI : récupère les offres d'emploi pour le métier Data Engineer, comprenant les offres expirées sur le code région 11 (IDF)">
        <img src="../images/projet_DE/fastapi_3.png" alt="vignette" style="width: 82px; border: 1px solid black;">
      </a>
    </td>
  </tr>

  <tr>
    <td>Power BI</td>
    <td>
      <a href="../images/projet_DE/powerbi_1.png" class="image-popup" title="Power BI : top 10 des qualifications professionnelles et qualifications">
        <img src="../images/projet_DE/powerbi_1.png" alt="vignette" style="width: 85px; border: 1px solid black;">
      </a>
      <a href="../images/projet_DE/powerbi_2.png" class="image-popup" title="Power BI : localisation des offres grâce aux transformations de l'ETL">
        <img src="../images/projet_DE/powerbi_2.png" alt="vignette" style="width: 85px; border: 1px solid black;">
      </a>
      <a href="../images/projet_DE/powerbi_2.png" class="image-popup" title="Power BI : comptage des mots-clés apparaissant le plus souvent dans les offres d'emploi">
        <img src="../images/projet_DE/powerbi_2.png" alt="vignette" style="width: 85px; border: 1px solid black;">
      </a>
    </td>
  </tr>

  <tr>
    <td>Grafana</td>
    <td>
      <a href="../images/projet_DE/monitoring_1.png" title="Grafana : en jaune le DAG 1, en bleu le DAG 2 (GUI d'Airflow)">
        <img src="../images/projet_DE/monitoring_1.png" alt="vignette" style="width: 85px; border: 1px solid black;">
      </a>
      <a href="../images/projet_DE/monitoring_2.png" title="Grafana (cAdvisor) : affichage de la consommation CPU et mémoire des conteneurs docker">
        <img src="../images/projet_DE/monitoring_2.png" alt="vignette" style="width: 85px; border: 1px solid black;">
      </a>
      <a href="../images/projet_DE/monitoring_3.png" title="Grafana (node-exporter) : affichage de la consommation CPU, mémoire, réseau et disque de la machine hôte">
        <img src="../images/projet_DE/monitoring_3.png" alt="vignette" style="width: 85px; border: 1px solid black;">
      </a>
    </td>
  </tr>

  <tr>
    <td>Architecture</td>
    <td>
      <a href="../images/projet_DE/architecture.png" title="Architecture du projet, principalement dockerisé">
        <img src="../images/projet_DE/architecture.png" alt="vignette" style="width: 80px; border: 1px solid black;">
      </a>
    </td>
  </tr>



🎯 <u>Résultats</u>

<div class="smaller-text">

  - Pipeline de données robuste exécuté quotidiennement
  - 200k offres d’emploi agrégées en 10 mois

</div>


📈 <u>Exemples d’insights</u>

<div class="smaller-text">

  - Compétences et soft skills les plus demandés par les recruteurs
  - Mots-clés les plus récurrents dans les offres d’emploi

</div>


📝 <u>Actions</u>

<div class="smaller-text">

- Pipeline ETL/ELT avec orchestration de tâches exécutés quotidiennement *[Airflow]* :

  - Collecte des offres d'emploi avec l'API de France Travail (JSON) :
    - Requêtes pour 60 métiers de la tech, dont ceux de la data
    - Parallélisation des requêtes avec gestion des erreurs 429 ("too much requests")

  - Transformations des données avant stockage *[Python]* :
    - Conservation des offres d'emploi en France métropolitaine uniquement
    - Ajout des données de localisation des offres d'emploi (ville, département, région) à partir de données récupérées sur le site de l'Insee, parfois à partir des coordonnées gps (avec la librairie Python geopy)

  - Stockage dans une base de données relationnelle *[PostgreSQL]* :
    - Modélisation en flocon de neige
    - Parallélisation des requêtes SQL pour écrire dans la base de données

  - Transformations des données après stockage *[SQL]* :
    - Ajout d'un attribut pour préciser si l'offre d'emploi est pour un DA, un DE ou un DS
    - Ajout d'un attribut pour si l'offre d'emploi contient des mots-clés prédéfinis



- Développement d’une API *[FastAPI]* :

  - Paramètres pour filtrer les offres d'emploi par leur localisation (région, département, ville), les offres d'emploi valides, et par les métiers de la data (Data Analyst, Data Engineer, Data Scientist)
  - Consultation des attributs d'une offre d'emploi par son identifiant
  - Voir les offres les plus récentes
  - Ajout, suppression d'une offre factice
  - Affichage de statistiques : nombre total des offres d'emploi, classements des régions/départements/villes qui recrutent le plus
  - Affichage des critères les plus demandés par les recruteurs, par exemple pour un Data Engineer :
    - la compétence la plus demandée : "Analyser, exploiter, structurer des données"
    - la qualité professionnelle la plus demandée : "Faire preuve d'autonomie"


- Conception de dashboards BI *[PowerBI]*



- Mise en place d’un système de monitoring *[Grafana/Prometheus]* :


  - Supervision des métriques d'Airflow (statsd_exporter), de la machine hôte (node_exporter), de la base de données (postgres_exporter) et des conteneurs (cadvisor)


- Conteneurisation du projet avec Docker Compose *[Docker]*


</div>


🛠️ <u>Stack</u>

<div class="smaller-text">

  - Python, Airflow, PostgreSQL, SQL, FastAPI, Power BI, Prometheus, Grafana, Docker

</div>


🔗 <u>Liens</u>

<div class="smaller-text">

  - [Github](https://github.com/vimchun/Job-Market-in-France/)
  - [Github Pages](https://vimchun.github.io/Job-Market-in-France/)

</div>

---

# 📊 Projet Data Analyst (2024)

**Analyse et prédiction des délais d’intervention des brigades de pompiers de Londres**

🎯 <u>Résultats</u>

<div class="smaller-text">

  - Création de data viz à partir de données totalisant 4 millions de lignes et 60 colonnes
  - Prédiction avec un modèle de classification et une précision de 70%

</div>


📈 <u>Exemples d’insights</u>

<div class="smaller-text">

  - Coûts liés aux fausses alertes
  - Causes les plus fréquentes des retards

</div>


📝 <u>Actions</u>

<div class="smaller-text">

  - Manipulation et préparation de la data, vérification de la qualité et la fiabilité des données
  - Storytelling avec mise en œuvre de tableaux de bord décisionnels
  - Features engineering et machine learning pour estimer les délais d’intervention

</div>


🛠️ <u>Stack</u>

<div class="smaller-text">

  - Python, Jupyter Notebook, Pandas, PySpark, Power BI, Scikit-learn

</div>


🔗 <u>Liens</u>

<div class="smaller-text">

  - A venir

</div>
