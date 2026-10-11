# Mathematic Clock

Horloge analogique interactive dont les douze repères horaires sont remplacés par des expressions mathématiques exactes. Chaque expression vaut exactement l'entier de sa position sur le cadran.

## Démonstration

`index.html` est autonome : à ouvrir directement dans un navigateur moderne, sans serveur, framework ni dépendance.

Exemples :

- `∫₀¹ 3 dx = 3`
- `Γ(6) / Γ(5) = 5`
- `18ζ(2) / π² = 3`
- `limₓ→₀ sin(x) / x = 1`

## Fonctionnalités

- **Temps réel** : aiguilles calculées depuis l'heure locale du navigateur, plus un affichage numérique.
- **Rotation des expressions** : trois ensembles, changés toutes les 300 secondes (5 minutes), indépendamment des aiguilles.
- **Pause / reprise** : suspend l'animation des aiguilles, pas la rotation des expressions.
- **Mobile** : dimensions CSS relatives et règles `@media`.

## Mathématiques utilisées

- Intégrales : `∫₀¹ n dx = n`
- Gamma : `Γ(n+1) = nΓ(n)`, donc `Γ(6)/Γ(5) = 5`
- Zêta : `ζ(2) = π²/6`, donc `18ζ(2)/π² = 3`, `30ζ(2)/π² = 5`, `60ζ(2)/π² = 10`, `66ζ(2)/π² = 11`
- Eta : `η(2) = π²/12`, donc `12η(2)/π² = 1`, `108η(2)/π² = 9`
- Limite : `limₓ→₀ sin(x)/x = 1`

Le navigateur n'effectue aucun calcul symbolique : les égalités sont établies à la conception. C'est une démonstration visuelle, pas un moteur de calcul formel.

## Architecture

HTML, CSS, JavaScript natif (`Date`, `requestAnimationFrame`, DOM). Aucun framework, aucune bibliothèque.

```text
Mathematic-Clock/
├── index.html
├── README.md
├── .gitignore
└── LICENSE
```

## Exécution locale

Ouvrir `index.html`, ou servir le dossier :

```bash
python3 -m http.server 8000
```

puis ouvrir `http://localhost:8000/`.

## Pistes d'évolution

- Nouvelles familles d'expressions (séries, produits infinis, intégrales impropres, déterminants, etc.), avec la même contrainte : valeur exacte égale à la position.
- Mode pédagogique : clic sur une expression pour afficher son résultat et l'identité utilisée.
- Génération de candidats, ne conservant que les égalités démontrées.

## Licence

MIT, voir le fichier `LICENSE`.

## Auteur

Projet personnel de valorisa.
