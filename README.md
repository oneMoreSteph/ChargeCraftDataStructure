# ChargeCraft - Supervision de Bornes de Recharge 

Ce projet implémente un noyau de gestion performant pour stations de recharge, basé sur des structures de données (AVL, Files, Arbres N-aires).

## 1. Modules Choisis
Conformément au cahier des charges, les modules fonctionnels suivants ont été implémentés :

* **Module A1 (Indexation & Recherche)** : Implémentation de requêtes par intervalle d'IDs (`si_range_ids`) et comptage par puissance (`si_count_ge_power`).
* **Module A3 (Filtrage Avancé)** : Moteur de règles flexible utilisant une notation postfixe (Stack) pour filtrer les stations selon plusieurs critères combinés.
* **Module B2 (Résilience & Pannes)** : Gestion d'un mode "dégradé". Simulation d'une panne sectorielle (Power Outage) sans interruption du traitement du flux d'événements.
* **Module C1 (Suivi Véhicules)** : Suivi des dernières stations visitées par un véhicule (MRU - Most Recently Used) via une liste chaînée simple.

## 2. Scénario de Démonstration
L'exécutable `ev_demo` déroule le scénario suivant pour valider les structures :

1.  **Ingestion** : Chargement des stations (CSV/JSON) et construction de l'index AVL.
2.  **État Nominal** : Traitement d'un flux d'événements classique via une File (Queue).
3.  **Simulation d'Incident (B2)** :
    * Injection d'une panne de courant sur un secteur précis (IDs 1101-1150).
    * Le système passe en mode dégradé mais continue d'accepter/rejeter les véhicules correctement.
    * Restauration du secteur (Recovery) et vérification du retour à la normale.
4.  **Fonctions Avancées** :
    * Construction et affichage de la hiérarchie géographique (Pays → Région → Ville).
    * Exécution d'une requête "Top-N" pour trouver les 5 meilleures bornes disponibles.

## 3. Compilation et Lancement

Le projet ne nécessite aucune librairie externe.

**Compiler et executer le projet :**
```bash
make && ./ev_demo
