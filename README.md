# Simulation d'une colonie de fourmis

Ce projet propose une simulation visuelle du comportement collectif d'une colonie de fourmis. Les fourmis explorent une grille à la recherche de nourriture, déposent des phéromones lorsqu'elles la trouvent, puis renforcent progressivement les chemins efficaces entre le nid et la nourriture.

La simulation illustre quatre concepts complémentaires :

- **Modélisation agent-based (ABM)** : chaque fourmi est un agent autonome possédant son propre état et son historique de déplacement.
- **Stigmergie** : les fourmis communiquent indirectement en modifiant leur environnement grâce aux phéromones.
- **Choix probabiliste** : les déplacements dépendent de l'intensité des phéromones et de la proximité de la nourriture.
- **Ant Colony Optimization (ACO)** : l'évaporation et le dépôt de phéromones favorisent l'émergence d'un chemin efficace.

## Démonstration

- [Voir la vidéo de la simulation](./Ant%20colony%20simulation.mp4)
- [Ouvrir le notebook](./simulation%20colonie%20de%20fourmis.ipynb)
- [Consulter le document de modélisation](./Mod%C3%A9lisation_d_une_colonie_de_fourmis.pdf)

## Fonctionnement

La simulation se déroule sur une grille de `50 × 50` cases :

- le nid est situé en `(5, 5)` ;
- la nourriture est située en `(45, 45)` ;
- 50 fourmis partent du nid et se déplacent dans les huit directions possibles ;
- les fourmis utilisent les phéromones et la distance à la nourriture pour choisir leur prochaine case ;
- les phéromones s'évaporent progressivement afin d'éviter de conserver les chemins inefficaces ;
- lorsqu'une fourmi trouve la nourriture, elle revient vers le nid en renforçant son chemin.

La probabilité de sélection d'une case voisine est basée sur l'influence des phéromones (`ALPHA`) et de la visibilité liée à la distance (`BETA`).

## Paramètres principaux

| Paramètre | Valeur | Description |
|---|---:|---|
| `GRID_SIZE` | `50` | Taille de la grille |
| `N_ANTS` | `50` | Nombre de fourmis |
| `N_ITERATIONS` | `10000` | Nombre d'itérations |
| `ALPHA` | `1` | Influence des phéromones |
| `BETA` | `2` | Influence de la visibilité |
| `RHO` | `0.1` | Taux d'évaporation |
| `Q` | `100` | Quantité de phéromones déposée |

## Installation

Python 3 et Jupyter sont nécessaires. Installez les dépendances avec :

```bash
pip install numpy matplotlib notebook
```

## Exécution

1. Clonez le dépôt :

   ```bash
   git clone https://github.com/aymaneousmane/Simulation_colonie_de_fourmis.git
   cd Simulation_colonie_de_fourmis
   ```

2. Lancez Jupyter Notebook :

   ```bash
   jupyter notebook
   ```

3. Ouvrez `simulation colonie de fourmis.ipynb` et exécutez les cellules dans l'ordre.

La visualisation affiche la carte des phéromones, la position des fourmis et l'évolution du chemin émergent. L'exécution complète peut prendre du temps en raison des 10 000 itérations et de l'animation matplotlib.

## Résultats attendus

À mesure que la simulation progresse, les phéromones se concentrent sur les trajets les plus efficaces. Le chemin entre le nid et la nourriture devient ainsi progressivement plus visible et plus fréquemment utilisé par les fourmis.

## Technologies utilisées

- Python 3
- NumPy
- Matplotlib
- Jupyter Notebook

## Auteur

Projet réalisé par [aymaneousmane](https://github.com/aymaneousmane).
