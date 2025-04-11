# Analyse-des-Donnees-Cyclistic-pour-Optimiser-les-Adhesions-Annuelles

Ce projet contient l'analyse des données Cyclistic pour comprendre les différences d'utilisation entre les membres annuels et les cyclistes occasionnels. L'objectif est d'identifier les comportements distincts et de proposer des recommandations pour optimiser les opérations et convertir les occasionnels en membres.

---

## *Aperçu du projet*

### **Objectifs**
1. Identifier les différences de durée, distance et préférences de vélos entre membres et occasionnels.
2. Analyser les tendances saisonnières de fréquence et les schémas de déplacement géographique.
3. Déterminer les stations les plus populaires pour chaque groupe d'utilisateurs.
4. Fournir des recommandations stratégiques pour améliorer la disponibilité des vélos et augmenter les adhésions.

---

## **Jeux de données**

L'analyse repose sur un jeu de données unique agrégé à partir de plusieurs fichiers CSV :
1. [**Données Cyclistic.csv**](https://divvy-tripdata.s3.amazonaws.com/index.html) : Plus de 6 millions de trajets avec des détails sur les déplacements, les stations et les types d'utilisateurs.

---

## **Colonnes clés du jeu de données**
- `ride_id` : Identifiant unique de chaque trajet.
- `rideable_type` : Type de vélo (ex. : classique, électrique).
- `started_at` : Horodatage de début du trajet.
- `ended_at` : Horodatage de fin du trajet.
- `start_station_name`, `end_station_name` : Noms des stations de départ et d’arrivée.
- `start_lat`, `start_lng`, `end_lat`, `end_lng` : Coordonnées des stations.
- `member_casual` : Type d’utilisateur (membre ou occasionnel).

  ---
  
## **Méthodologie**

L'analyse a suivi ces étapes :
1. **Préparation des données**:
  - Chargement et nettoyage des données (ex. : gestion des noms de stations manquants, conversion des horodatages).
  - Calcul de la durée des trajets (ended_at - started_at) et de la distance (formule Haversine).
    
2. **Analyse exploratoire des données (EDA)**:
  - Étude des tendances de durée, distance, types de vélos et fréquence saisonnière.
  - Analyse des schémas de déplacement (trajets linéaires vs boucles) et popularité des stations.

3. **Analyse et insights**:
  - Comparaison des usages des membres et occasionnels selon les métriques clés.
  - Cartographie des fréquences des stations avec des visualisations interactives.

4. **Recommandations**:
  - Proposition de stratégies pour améliorer la distribution des vélos et la conversion en membres.

--- 

## **Résultats clés**

1. **Durée et distance des trajets**:
  - Membres : Moyenne ~12 min, ~2,15 km, stable toute l’année (10,8-13,1 min, 1,9-2,2 km). Usage utilitaire constant (ex. : trajets domicile-travail).
  - Occasionnels : Moyenne ~21 min, ~2,1 km, pic au printemps/été (~23 min), minimum en hiver (~15 min, 1,69 km). Usage récréatif, sensible aux saisons.

2. **Préférences des types de vélos**:
  - Membres : 51,7 % classiques, 46,8 % électriques. Légère préférence pour les classiques.
  - Occasionnels : 51,4 % classiques, 44,7 % électriques. Préférence similaire, mais moins d’électriques.

3. **Fréquence saisonnière**:
  - Membres : Été (1,27M trajets), Hiver (674K, -47 % vs été). Stable, avec une baisse en hiver.
  - Occasionnels : Été (937K trajets), Hiver (161K, -83 % vs été). Très saisonnier, pic en été.

4. **Schémas de déplacement**:
  - Membres : 89,86 % linéaires, 10,14 % boucles. Majorité de trajets aller simple (ex. : travail).
  - Occasionnels : 82,2 % linéaires, 17,79 % boucles. Plus de boucles, suggérant des balades loisirs.

5. **Stations populaires**:
  - Membres : "Kingsbury St & Kinzie St", "Clinton St & Washington Blvd" (quartiers d’affaires).
  - Occasionnels : "Streeter Dr & Grand Ave", "DuSable Lake Shore Dr & Monroe St" (zones touristiques, plus forte fréquentation occasionnelle).

---

## **Détails techniques**

### **Outils et bibliothèques**
- **Langage de programmation** : Python
- **Bibliothèques** :
  - `pandas` pour la manipulation des données.
  - `folium` pour les cartes interactives.
  - `matplotlib` et `seaborn` pour les visualisations.
  - `numpy` pour les calculs de distance.
 
---

## **Visualisations**

Le projet inclut des visualisations clés :
- Cartes interactives des fréquences des stations (globale et par type d’utilisateur).
- Graphiques en barres de la durée, l’usage des vélos et la fréquence saisonnière.
- Consultez map_visualization.ipynb pour voir les cartes en direct dans Jupyter Notebook.

---

## **Recommandations clés**

1. Augmenter les adhésions :
  - Ciblez les occasionnels estivaux (937K trajets) avec des essais gratuits ou des incitations pour les vélos électriques.
  - Proposez un "Pass Touriste" pour des stations comme "Streeter Dr & Grand Ave".
2. Optimiser la disponibilité des vélos :
  - Augmentez les vélos classiques et électriques dans les stations touristiques ("Streeter Dr") en été.
  - Assurez un stock constant de vélos classiques dans les zones d’affaires ("Clinton St") toute l’année.
3. Améliorer l’expérience utilisateur :
  - Promouvez les vélos électriques pour les trajets loisirs avec des itinéraires suggérés (ex. : bord du lac).
  - Offrez des réductions hivernales pour réduire la saisonnalité des occasionnels (161K trajets).
4. Exploiter les données des stations :
  - Adaptez le marketing : renouvellements à "Kingsbury St" (membres), conversion à "Streeter Dr" (occasionnels).

---

## Comment utiliser ce dépôt

Clonez le dépôt :
```bash
git clone https://github.com/Oladk/Analyse-des-Donnees-Cyclistic-pour-Optimiser-les-Adhesions-Annuelles.git

