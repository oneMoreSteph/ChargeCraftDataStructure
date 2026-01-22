# EV & Charging Stations — C11 Starter V2

## Présentation
Ce projet est une démonstration en C11 de structures de données appliquées à la gestion
de bornes de recharge pour véhicules électriques (IRVE).
Il met en œuvre plusieurs structures classiques pour organiser, indexer et traiter
des données issues de fichiers CSV et JSON.

---

## Modules choisis
Le projet s’appuie sur les modules suivants :

- **slist** : liste simplement chaînée (MRU) pour conserver les stations récemment utilisées
- **queue** : file FIFO pour le traitement des événements
- **stack** : pile utilisée pour l’évaluation d’expressions postfixées
- **station_index (AVL)** : arbre AVL pour indexer efficacement les stations
- **nary** : arbre n-aire (structure générique, parcours BFS)
- **events** : flux d’événements simulés
- **csv_loader** : chargement de stations depuis un fichier CSV
- **json_loader** : chargement de stations depuis un fichier JSON

---

## Scénario de la démo
La démonstration suit le scénario suivant :
1. Chargement des stations depuis des fichiers CSV et JSON
2. Ingestion d’événements simulés
3. Indexation des stations dans un arbre AVL
4. Mise à jour d’une liste MRU des stations récemment utilisées
5. Affichage des structures pour illustrer leur fonctionnement

---

## Compilation et exécution
Pour compiler et lancer la démo :

```bash
make
./ev_demo
