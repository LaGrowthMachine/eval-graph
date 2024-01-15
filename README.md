# Welcome to LGM
Une seule chose: Chez Lgm on est sensible à la qualité.

## Quelques règles:
- Tu répondras en typescript
- 1 semaine max de délai à partir du moment où je te l'envoi
- Ton code doit se lire comme un roman -> Pas de commentaire
- Une commande pour build
- Fais ce que tu estimes nécessaire pour montrer tes talents d'artiste
- Tu mets tout sur une repo **PRIVÉE** et tu partages la repo avec @tchangang et @yerowell
- Fais un fichier .ts par question et log dans la console le résultat final.
```javascript
   - question1.ts
   - question2.ts
   - question3.ts
   - question4.ts
...etc...
```
## Exercice 1

Considérons l'objet suivant:
```javascript
const items = {
    'START': {
        type: 'START',
    },
    'b28d87a7-adbd-4316-a2b3-3aa25d1b16c4': {
        type: 'ACTION_TYPE_A',
    },
    '46f2eae9-e2d2-437c-b311-fb2fe97385f6': {
        type: 'ACTION_TYPE_B',
    },
    'd48b3cd1-0c2f-46b1-903f-56c25f2d05d2': {
        type: 'ACTION_TYPE_C',
    },
    'e1ace598-6862-4ceb-830c-593cd6851b2c_condition': {
        type: 'ACTION_TYPE_A',
    },
    'e9da1d0e-a401-4256-91a7-fca5e07ff9e4': {
        type: 'ACTION_TYPE_D',
    },
    'fa37941b-801b-4d58-84a4-f5ed6fd087d9': {
        type: 'ACTION_TYPE_D',
    },
    '49e7569d-94f2-4e92-821d-e0a3ecf99bb3': {
        type: 'ACTION_TYPE_A',
    },
    'b0804228-0cb0-46a0-ae5d-6f81aefbc69c': {
        type: 'ACTION_TYPE_B',
    },
    'a36b0f52-9241-48a5-905e-42cb6d2cedd6_condition': {
        type: 'ACTION_TYPE_A',
    },
    '07e4c446-20e3-416c-85f7-b0e9fcb4e13f_opposite_arrow_0_condition': {
        type: 'ACTION_TYPE_C',
    },
    '6ff64933-e636-4c30-87de-aba3626d1980': {
        type: 'ACTION_TYPE_P',
    },
}
const relations = {
    "START": 
        "b28d87a7-adbd-4316-a2b3-3aa25d1b16c4",
        "46f2eae9-e2d2-437c-b311-fb2fe97385f6"
    ],
    "b28d87a7-adbd-4316-a2b3-3aa25d1b16c4": [
      "d48b3cd1-0c2f-46b1-903f-56c25f2d05d2"
    ],
    "46f2eae9-e2d2-437c-b311-fb2fe97385f6": [
        "6ff64933-e636-4c30-87de-aba3626d1980"
    ],
    "d48b3cd1-0c2f-46b1-903f-56c25f2d05d2": [
        "e1ace598-6862-4ceb-830c-593cd6851b2c_condition"
    ],
    "e1ace598-6862-4ceb-830c-593cd6851b2c_condition": [
        "e9da1d0e-a401-4256-91a7-fca5e07ff9e4"
    ],
    "e9da1d0e-a401-4256-91a7-fca5e07ff9e4": [
        "fa37941b-801b-4d58-84a4-f5ed6fd087d9"
    ],
    "fa37941b-801b-4d58-84a4-f5ed6fd087d9": [
        "49e7569d-94f2-4e92-821d-e0a3ecf99bb3",
        "b0804228-0cb0-46a0-ae5d-6f81aefbc69c"
    ],
    "b0804228-0cb0-46a0-ae5d-6f81aefbc69c": [
        "a36b0f52-9241-48a5-905e-42cb6d2cedd6_condition",
        "07e4c446-20e3-416c-85f7-b0e9fcb4e13f_opposite_arrow_0_condition"
    ],
    "a36b0f52-9241-48a5-905e-42cb6d2cedd6_condition": [],
    "07e4c446-20e3-416c-85f7-b0e9fcb4e13f_opposite_arrow_0_condition": []
};
```
items et relations représentent les différentes élements d'un graph
```javascript
// Ex: START -> b28d87a7-adbd-4316-a2b3-3aa25d1b16c4 -> d48b3cd1-0c2f-46b1-903f-56c25f2d05d2 ->
//           -> 46f2eae9-e2d2-437c-b311-fb2fe97385f6 -> 6ff64933-e636-4c30-87de-aba3626d1980 ->
// items est sous le format: { string: { type: string } }
// relations est sour le format: { string: Array<string> }
```

### Question 1
A partir de l'objet relations, combien y a t'il d'elements distinct (EX: START, b28d87a7-adbd-4316-a2b3-3aa25d1b16c4, 46f2eae9-e2d2-437c-b311-fb2fe97385f6)

### Question 2
Lister l'ensemble des types (ACTION_TYPE_A, ACTION_TYPE_B, ACTION_TYPE_C, etc...)et le nombre au format: { ACTION_TYPE_A: 5, ACTION_TYPE_B: 1, etc...}

### Question 3
Chaque type a un score:
```javascript
  // ACTION_TYPE_A: 5
  // ACTION_TYPE_B: 3
  // ACTION_TYPE_C: 1
  // ACTION_TYPE_D: 0
  // ACTION_TYPE_P: -1
```
Calculer le score total du graphe

### Question 4
Le premier element c'est l'element START
```javascript
// "START": [
//         "b28d87a7-adbd-4316-a2b3-3aa25d1b16c4",
//         "46f2eae9-e2d2-437c-b311-fb2fe97385f6"
//     ],
```
A partir de START, jusqu'où peut-on aller ?

### Question 5

Si vous deviez identifier cette séquence sous la forme d'un string de manière à ce que le résultat ne correspondent qu'à cette séquence, quel format choisirez-vous ?

## Exercice bonus

- Tu dois monter une application de validation de document.
- Tu as X utilisateurs.
- Chaque utilisateur a 3 types (document 1, document 2, document 3) de documents à valider.
- Pour valider un document, il faut faire un call api.
- Une validation dure entre 30 secondes et 1 minute.
- La validation ne peut se dérouler qu'entre 08h et 17h
- Les validations de document sont indépendantes mais pour chaque queue est une FIFO (l'ordre de validation des documents 1 doit préservé, l'ordre 2 doit être préservé, l'ordre 3 préservé).
- On suppose que tous les utilisateurs ont le même nombre de documents 1, documents 2 et documents 3 à valider: 300 documents de chaque type.
- Tu n'as aucune limite sur les technos.

NB: Ta seule contrainte c'est que chaque utilisateur puisse valider 300 documents de chaque type et qu'à chaque instant t, on puisse savoir ce qu'il y a dans chaque queue.
### Question 1
Imagine un système pour gérer 100 utilisateurs.

### Question 2
On est passé à 1000 utilisateurs. Est-ce que ton système tient ? Qu'est-ce que tu changes (rien peut être) ? 

### Question 3
On est passé à 10 000 utilisateurs. Est-ce que ton système tient ? Qu'est-ce que tu changes (rien peut être) ? 

### Question 4
Tu veux monitorer ce que tu as mis en place pour t'assurer que chaque user a la même chance de réaliser 300 jobs (même s'il n'a pas 300 jobs à faire). Quel indicateur proposes-tu ?
