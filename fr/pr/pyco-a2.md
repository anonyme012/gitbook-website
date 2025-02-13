---
icon: repeat
---

# Cours de Python - Contrôle du flux & Boucles

## Opérateurs de comparaison

<table><thead><tr><th width="217">Opérateur</th><th>Signification</th></tr></thead><tbody><tr><td><code>==</code></td><td>Égal</td></tr><tr><td><code>!=</code></td><td>Non égal</td></tr><tr><td><code>&#x3C;</code></td><td>Plus petit</td></tr><tr><td><code>></code></td><td>Plus grand</td></tr><tr><td><code>&#x3C;=</code></td><td>Plus petit ou égal</td></tr><tr><td><code>>=</code></td><td>Plus grand ou égal</td></tr></tbody></table>

{% hint style="warning" %}
Ne confondez pas le symbole `=` qui permet d'assigner une variable et l'opérateur `==` qui sert a comparer des valeurs.
{% endhint %}

## Opérateurs booléens

Il existe trois opérateurs booléens : `and`, `or` et `not`. Respectivement, en français, _"et"_, _"ou"_ et _"pas"_.

Voici quelques exemples en y ajoutant les [opérateurs de comparaison](pyco-a2.md#operateurs-de-comparaison) et les [opérateurs mathématiques](pyco-a1.md#operateurs-mathematiques) :

```python
(4 < 5) and (5 < 6)                              # True
(1 == 2) or (2 + 3 == 2)                         # False
2 + 2 == 4 and not 2 + 2 == 5 and 2 * 2 == 2 + 2 # True
(5 > 4 or 3 < 4) and 5 > 5                       # False
```

{% hint style="info" %}
Le mot-clé `or` ne signifie pas _"ou"_ mais _"et / ou"_.
{% endhint %}

## Mots clés `if`, `else` et `elif`

Le mot clé `if` vérifie si l'expression fournie est vraie (condition remplie). Si oui, le code indenté est exécuté. Si ce n'est pas le cas, les instructions indentées après `else` sont exécutées. Pour finir, `elif` peut être placé entre les deux pour faire office de _"sinon si"_. Il peut y en avoir plusieurs.

<pre class="language-python"><code class="lang-python"># On demande à l'utilisateur de créer un nom.
username = input("Créer votre nom d'utilisateur.")

<strong># On vérifie si il n'est pas incorrect. Dans ce cas, on lui en donne la raison.
</strong><strong>if username == "admin" or username == "administrator" :
</strong>    print("Ce nom d'utilisateur n'est pas autorisé.")
    print("C'est une usurpation d'identité envers le propriétaire du logiciel.")
elif username == "moi" :
    print("Vous n'avez pas le droit de vous nommer comme cela.")
    print("Ça pourrait porter à confusion.")
elif username = "" :
    print("Veuiller entrer du texte : votre nom ne peut pas être vide.")

# Sinon, on lui affiche un message de bienvenue.
else :
    print("Bienvenue,", username, "!")
</code></pre>

{% hint style="info" %}
Comprenez bien que la 1ère instruction `elif` ne s'exécutera que si `if` évalue l'instruction comme fausse, le 2ème `elif` n'évaluera la véracité de son expression que si les deux précédentes ont évaluées la leur comme fausse. Évidemment, le code indenté après `else` sera exécuté seulement si toutes les expressions des `if` et `elif` sont fausses.
{% endhint %}

## Opérateur ternaire

L'opérateur ternaire est un manière de compacter un _"if else"_ en une seule ligne. Il retourne une valeur qui peut être affichée ou assignée à une variable par exemple. Il a une construction légèrement différente que l'on va voir à l'aide de cet extrait de code.

```python
age = input("Entrez votre âge : ")

if age < 18 :
    print("enfant")
else :
    print("adulte")

# equivaut à

print("enfant" if age < 18 else "adulte")
```

Il ne supporte pas nativement le `elif` même si on peut l'utiliser en enchaînant plusieurs opérateurs ternaires.

```python
age = input("Entrez votre âge : ")

if age < 13 :
    categorie = "enfant"
elif age < 18 :
    categorie = "adolescent"
else :
    categorie = "adulte"

# equivaut à

categorie = 'enfant' if age < 13 else 'adolescent' if age < 18 else 'adulte'
```

## Mots clés `match` et `case`

Le contrôle de flux _"switch-case"_ sert à faire une action selon la valeur d'une variable de manière rapide et efficace.

Prenons l'exemple des codes de statut du protocole HTTP.

```python
match response_code : # Cet extrait de code affiche la signification du code
    case 200 :        # de statut contenu dans la variable response_code.
        print("OK")
    case 201 :
         print("Crée avec Succès")
    case 300 :
        print("Redirection à Choix Multiple")
    case 307 :
        print("Redirection Temporaire")
    case 404 :
        print("Page Introuvable")
    case 500 :
        print("Erreur Interne du Serveur")
    case 502 :
        print("Mauvais Port")
```

{% hint style="warning" %}
Gardez à l'esprit que dès qu'une condition est satisfaite, on saute tout le code indenté qui suit `match`.
{% endhint %}

On peut modifier cet extrait en utilisant deux fonctionnalités :

* Le `or` qui permet d'exécuter le même code pour plusieurs cas. Il peut aussi s'écrire `|`.
* Le cas `_` est un cas par défaut si aucun des autres ne correspond.

```python
match response_code:
    case 200 | 201 :
        print("OK")
    case 300 | 307 :
        print("Redirection")
    case 404 :
        print("Mauvaise Requête")
    case 500 | 502 :
        print("Erreur Interne du Serveur")
    case _ :
        print("Code Invalide")
```

{% hint style="info" %}
Il est un bonne pratique et même parfois essentiel de placer le cas par défaut (`case _`) en dernier.
{% endhint %}

## Boucle `while`

Un boucle de type sert a exécuter du code en boucle tant que la condition est remplie.

```python
compteur = 0
while spam < 5 :
    print("Bonjour")
    compteur += 1 # On incrémente la variable
# Ce code affichera "Bonjour" 5 fois
```

On peut aussi faire des boucles sans fin.

```python
notes = ""
while True :
    nouvelle_note = input("Tapez une nouvelle note.") # input() permet au système
                                                      # de ne pas exécuter du code
                                                      # au maximum de ses capacités.
    notes += nouvelle_note + " ; "
    print(notes)
```

{% hint style="danger" %}
Utiliser des boucles sans fin peut se révéler problématique. En effet, dans un code comme celui ci-dessous, "_Bonjour_" sera affiché autant de fois que possible ce qui pompera toutes les ressources de l'ordinateur et peut même le faire planter.

```python
while True :
    print("Bonjour")
# Ce code est dangereux et peut planter.
```

C'est pour cela qu'il faut utiliser de telles boucles uniquement avec des fonctions d'attente à l'intérieur comme `input()` ou `time.sleep()` (que l'on verra plus tard).
{% endhint %}

## Boucle `for`

Une boucle `for` permet de traiter ou d'utiliser chaque élément d'une objet composé. Le seul que l'on a appris pour l'instant est `str`. Sachez que chaque caractère est un élément à part entière.

Voici un programme qui enlève tous les espaces dans un texte. Il devra donc traiter les caractères un par un.

```python
texte = "Bonjour, je suis un développeur en Python." # On définit les
resultat = ""                                        # valeurs d'entrée

for c in texte : # Met à chaque répétition le caractère suivant dans la variable "c"
    if c != " " : # Vérifie que ce caractère n'est pas un espace
        resultat += c # Dans ce cas, on l'ajoute au résultat

print(resultat) # A la fin de la boucle, on affiche le résultat

# Donnera "Bonjour,jesuisundéveloppeurenPython."
```

## Mots clés `break` et `continue`

### `break`

Imaginez une boucle sans fin de laquelle vous voudriez sortir. L'instruction `break` permet de sortir immédiatement de la boucle sans même terminer le cycle.

<pre class="language-python"><code class="lang-python">while True :
    entree = input("Tapez exit pour sortir de la boucle : ")
    if  entree == "exit" :
        break
print("Bravo, vous avez réussi à sortir de la boucle !") # cette ligne ne sera pas
<strong>                                                         # exécutée tant que break
</strong><strong>                                                         # n'est pas appellé
</strong></code></pre>

### `continue`

Le mot-clé `continue` retourne immédiatement au début d'un nouveau cycle de boucle. Comme exemple, nous allons prendre ce système d'authentification.

```python
while True :
    nom = input("Qui êtes vous ? ")
    if name != "Bob":
        continue # Ici, inutile d'afficher l'invite de mot de passe
    password = input("Mot de passe : ")
    if password == "1234": # On sort de la boucle pour afficher le message
        break              # d'accès autorisé si le mot de passe est correct
print("Accès autorisé.")
```

{% hint style="info" %}
Sachez que les mots-clés `break` et `continue` sont utilisables à la fois sur des boucles `for` et `while`.
{% endhint %}
