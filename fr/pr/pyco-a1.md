---
icon: circle-play
---

# Cours de Python - Bases

## Opérateurs mathématiques

Car elles sont la base de l'informatique, nous allons commencer par un peu de mathématiques.

Voici par ordre de **priorité décroissante**, les opérateurs arithmétiques en Python :

<table><thead><tr><th width="129">Opérateur</th><th width="242">Opération</th><th>Exemple</th></tr></thead><tbody><tr><td><code>**</code></td><td>Exposant</td><td><code>3 ** 5 = 243</code></td></tr><tr><td><code>%</code></td><td>Modulo (reste)</td><td><code>52 % 20 = 12</code></td></tr><tr><td><code>//</code></td><td>Division entière (euclidienne)</td><td><code>52 // 20 = 2</code></td></tr><tr><td><code>/</code></td><td>Division</td><td><code>52 / 20 = 2.6</code></td></tr><tr><td><code>*</code></td><td>Multiplication</td><td><code>5 * 7.5 = 37.5</code></td></tr><tr><td><code>-</code></td><td>Soustraction</td><td><code>21 - 6 = 15</code></td></tr><tr><td><code>+</code></td><td>Addition</td><td><code>7 + 2 = 9</code></td></tr></tbody></table>

Les parenthèses restent prioritaires comme en mathématiques et il faut garder à l'esprit que le séparateur décimal des nombres en programmation est le point (comme dans les standards anglophones sur lesquels sont basés les langages de programmation) :&#x20;

```python
3.5 + 2 * 4   # 11.5

(3.5 + 2) * 4 # 22

6,2 + 8       # Donnera (6, 10) car l'interpréteur détéctera un
              # tuple (un type d'objet que l'on découvrira plus tard) 
              # ce qui donnera un résultat innatendu.
```

## Types de données&#x20;

L'informatique consiste à traiter des données de types divers. Les développeurs de Python ont donc prévu différents types d'objets.

Un chapitre de ce cours est consacré à ça. Vous pouvez le retrouver ici : [pyco-a3.md](pyco-a3.md "mention")

En attendant on va voir les plus simples et les plus utilisés :&#x20;

<table><thead><tr><th width="104">Nom</th><th width="405">Description</th><th>Exemple</th></tr></thead><tbody><tr><td><code>str</code></td><td>Chaîne de caractères (Unicode)</td><td><code>"Bonjour"</code> ou <code>'Au revoir'</code></td></tr><tr><td><code>int</code></td><td>Nombre entier signé (+ ou -)</td><td><code>38</code></td></tr><tr><td><code>float</code></td><td>Nombre décimal signé</td><td><code>4.49529</code></td></tr><tr><td><code>bool</code></td><td>Valeur booléenne (ne peut prendre que 2 valeurs : vrai ou faux)</td><td><code>True</code> ou <code>False</code></td></tr></tbody></table>

## Variables

Maintenant, passons aux variables. Elles servent à stocker des données dans la RAM pendant la durée d'exécution du programme. Cela signifie que dès que le programme est fermé, les données sont supprimées.&#x20;

Elles peuvent servir à stocker un nombre d'un étape intermédiaire d'un processus, une donnée sur l'utilisateur, une constante ou quoi que ce soit d'autre d'utile (ou pas).

Voici des exemples de déclaration de variables :&#x20;

```python
nom_de_la_variable = valeur

nom_utilisateur = "Bob"

ageUtilisateur = 21

modeSombre = True
```

Les noms de variables obéissent à des normes bien précises :

* Ils ne peuvent contenir que des lettres, des chiffres et l'underscore (`_`)
* Ils ne peuvent pas commencer par un chiffre
* Ils sont sensibles à la casse (différence entre les majuscules et les minuscules)
* Attention : les caractères accentuées (é, à, ù, ï, etc.) ne sont pas considérés comme des lettres

#### Conventions d'écriture

Il y a aussi 2 principales conventions de nommages : la "camel case" et la "snake case". Voici leurs différences :

```python
ceciEstUneVariableEnCamelCase # Plus court mais moins lisible
et_celle_ci_en_snake_case     # Plus long mais plus lisible
```

A vous de choisir celle qui vous convient le mieux.

#### Constantes

Même si Python n'a pas de fonctionnalité intégrée pour définir une constante (une variable qui ne change jamais), on dit par convention qu'on les représente avec la "snake case" tout en majuscules :

```python
PI = 3.14159265589793
ZERO_ABSOLU = -273.15
```

## Les fonctions `print()` et `input()`

L'utilisateur et le programme informatique doivent pouvoir communiquer entre eux. Ces deux fonctions serviront à ça : `print()` affiche du texte et `input()` permet à l'utilisateur de taper du texte.

Pour en savoir plus sur ce qu'est une fonction, suivez ce lien : [pyco-a4.md](pyco-a4.md "mention")

#### `print()`

Cette fonction peut accueillir plusieurs arguments de tous les types (pas que `str`). Les virgules, qui séparent les arguments, insèrent des espaces.

```python
print("Bonjour") # Bonjour
a = 12.36
b = False
print("Au revoir", a, b) # Au revoir 12.36 False
```

#### `input()`

Cette fonction prend l'entrée de l'utilisateur et la retourne sous forme de chaîne de caractères.

```python
age_utilisateur = input("Quel âge avez-vous ? ") # Stockera l'entrée dans la
                                                 # variable "age_utilisateur"
```

#### Exemple

```python
prenom = input("Tapez votre prénom : ") # Cela affichera "Tapez votre prénom : "
                                        # (sans les guillemets) et permettera à
                                        # l'utlisateur de taper du texte qui sera
                                        # ensuite mis dans la variable "prenom"

print("Bonjour,", prenom, "!") # Affichera la chaîne de caractères 
                               # passée en argument

# Si j'ai tapé "anonyme012", alors le programme écrira "Bonjour, anonyme012 !"
```

## Commentaires

Les commentaires n'ont pas d'utilité réelle pour un ordinateur. Ils servent à expliquer le fonctionnement d'un morceau de code complexe, expliquer l'utilité d'un variable ou indiquer l'auteur du script.

C'est une très bonne pratique à adopter des vos premiers programmes. Pensez à un autre développeur ou même à vous, en train de vous interroger sur le fonctionnement d'un extrait de code problématique à modifier. Bien que c'est légèrement chronophage à l'écriture initiale, ça vous fera économiser des heures de maintenance.

#### Commentaire de ligne

```python
# Bonjour. Ceci est un commentaire
```

#### Commentaire multiligne

```python
# Et celui-là 
# est
# multiligne.
```

#### Commentaire avec du code

```python
age_utilisateur = 2025 - date_de_naissance # Cette ligne calcule l'âge de l'utilisateur
```

## Concaténation & réplication de chaînes de caractères

Nous allons voir les méthodes de manipulation de chaînes de caractères les plus simples : la concaténation et la réplication. Pour cela, on utilise simplement les opérateurs mathématiques `+` et `*`. Ça fonctionne aussi avec des variables.

```python
formule_1 = "Bonjour"

phrase = formule_1 + "et tout" # donnera "Bonjouret tout"

texte_d_au_revoir = "Bye ! " * 5 # donnera "Bye ! Bye ! Bye ! Bye ! Bye ! "
```

## Opérateurs d'assignement

En plus du signe `=`, il existe différents opérateurs d'assignement de variables.

#### Opérateurs d'assignation mathématiques

<table><thead><tr><th width="222">Opérateur</th><th>Équivalent</th></tr></thead><tbody><tr><td><code>var += 1</code></td><td><code>var = var + 1</code></td></tr><tr><td><code>var -= 1</code></td><td><code>var = var - 1</code></td></tr><tr><td><code>var *= 1</code></td><td><code>var = var * 1</code></td></tr><tr><td><code>var /= 1</code></td><td><code>var = var / 1</code></td></tr><tr><td><code>var //= 1</code></td><td><code>var = var // 1</code></td></tr><tr><td><code>var %= 1</code></td><td><code>var = var % 1</code></td></tr><tr><td><code>var **= 1</code></td><td><code>var = var ** 1</code></td></tr></tbody></table>

#### Opérateur de Walrus

Cet opérateur assigne une valeur tout en la renvoyant.

```python
print(texte := "Salut !") # affiche "Salut !"

print(texte) # affiche encore "Salut !" ce qui montre
             # que la variable a bien été assignée

print(msg = "Voici mon message") # Cela retournera soit une erreur, soit une 
                                 # valeur booléenne si la variable existe déjà
```
