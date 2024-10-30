# Benchmarking-PoW-PoS
```markdown
# Benchmarking des Algorithmes de Preuve de Travail (PoW) et de Preuve d'Enjeu (PoS)

Ce projet effectue un benchmark de deux algorithmes de consensus : **Preuve de Travail (PoW)** et **Preuve d'Enjeu (PoS)**. Il utilise Python pour simuler et analyser les performances de chaque algorithme selon différents critères, tels que le temps nécessaire pour trouver une solution et la cohérence dans la sélection des validateurs/mineurs.

## Table des Matières
- [Description](#description)
- [Algorithmes](#algorithmes)
  - [Preuve de Travail](#preuve-de-travail)
  - [Preuve d'Enjeu](#preuve-denjeu)
- [Metrics de Benchmarking](#metrics-de-benchmarking)
- [Utilisation](#utilisation)
- [Exemple de Résultat](#exemple-de-résultat)
- [Prérequis](#prérequis)

## Description
Ce projet fournit une simulation des mécanismes de Preuve de Travail et de Preuve d'Enjeu , utilisés couramment dans les consensus de blockchain. La Preuve de Travail oblige les mineurs à résoudre un puzzle computationnel en trouvant un nonce valide, tandis que la Preuve d'Enjeu sélectionne des validateurs proportionnellement à leur enjeu dans le système.

## Algorithmes

### Preuve de Travail
L'algorithme de Preuve de Travail (PoW) utilise un défi computationnel pour garantir qu'une quantité spécifique de travail est réalisée avant qu'une solution soit acceptée. Cette implémentation utilise le hachage SHA-256 et recherche un hachage avec un nombre spécifique de zéros initiaux (difficulté).

### Preuve d'Enjeu
L'algorithme de Preuve d'Enjeu (PoS) sélectionne un validateur en fonction de la quantité d'actifs qu'il a "mis en jeu". Les validateurs avec un enjeu plus élevé ont une plus grande probabilité d'être choisis pour valider un bloc.

## Metrics de Benchmarking
La fonction de benchmarking évalue chaque algorithme selon :
1. **Temps Requis** : Mesure le temps moyen nécessaire pour accomplir le minage (PoW) ou la sélection (PoS).
2. **Cohérence** : Mesure la fréquence à laquelle chaque validateur est choisi dans PoS pour valider des blocs, reflétant l'équité de la sélection en fonction de l'enjeu.
3. **Efficacité en Ressources** : Bien que seulement les metrics de base soient mesurés, cette catégorie montre l'exigence en ressources de PoW (calculs intensifs) par rapport à l'approche moins intensive de PoS.

## Utilisation
1. **Exécuter le Benchmark** :
   - Assurez-vous que toutes les classes sont correctement implémentées (`ProofOfWork`, `ProofOfStake`, `Validator`).
   - Définissez le nombre de tests souhaités et d'autres paramètres dans `benchmark_pow_pos()`.

```python
# Exemple d'utilisation avec 10 essais
pow_difficulty = 4  # Ajuster la difficulté pour PoW
num_trials = 10
pos_stake_distribution = {
    "Alice": 50,
    "Bob": 30,
    "Charlie": 20
}

benchmark_pow_pos(num_trials, pow_difficulty, pos_stake_distribution)
```

## Exemple de Résultat
```plaintext
Benchmarking Proof of Work...
Proof of work found: 00004a99051d8a64793dbded9f3e1955097c580445670a3e69e50858ed3f7837
Nonce: 85650
Time taken: 0.12 seconds
...
Benchmarking Proof of Stake...

Benchmark Results:
Proof of Work - Average Time: 0.0821 seconds
Proof of Stake - Average Time: 0.0000 seconds

Proof of Stake - Validator Selection Counts (Consistency):
Alice: 5 selections
Bob: 3 selections
Charlie: 2 selections
```

Ce résultat montre le temps nécessaire pour chaque essai de Preuve de Travail et un résumé des temps moyens et des metrics de cohérence pour PoW et PoS.

## Prérequis
- Python 3.x
- Bibliothèques : `hashlib`, `time`, `random`

Cette implémentation et le benchmark de PoW et PoS fournissent une simulation simple pour comprendre comment ces algorithmes de consensus fonctionnent et comment leurs performances diffèrent en termes de coûts computationnels et d'équité dans la sélection des validateurs.
```
