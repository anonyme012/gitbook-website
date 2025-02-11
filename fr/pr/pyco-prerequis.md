# Prérequis

## Installer Python 3

En 2008, s'est opéré un changement dans l'histoire du Python et de la programmation : Python 3.0.0 est publié.

Sachez qu'à cette version, beaucoup de choses ont été modifiées, ce qui signifie qu'un programme pour Python 2 assez conséquent nécessite des modifications pour le faire fonctionner sous Python 3 et que certaines bibliothèques ne seront pas disponibles sur l'un des deux.

Téléchargez la dernière version (pas la version de développement) adaptée à votre système d'exploitation sur le site officiel : [https://www.python.org/downloads/](https://www.python.org/downloads/).

Ensuite, suivez les instructions de l'installeur ou du site web.

Pour vérifier que Python 3 est bien installée, ouvrez le terminal (voir [#ouvrir-un-terminal](pyco-prerequis.md#ouvrir-un-terminal "mention")) puis tapez la commande :

```bash
python3 --version
```

Cela devrait afficher votre version actuelle.

## Installer un éditeur de code

Un éditeur de code est un éditeur de texte qui affiche en une police à taille fixe et qui fournit la coloration syntaxique.

L'un des plus populaires est Visual Studio Code. Il dispose de nombreuses fonctionnalités, d'une interface conviviale et de nombreuses extensions adaptées à vos besoins. Il est disponible sur Windows, MacOS et Linux.

Vous pouvez le télécharger sur le site officiel : [https://code.visualstudio.com/download](https://code.visualstudio.com/download)

Vous avez aussi d'autres options comme :

* Notepad++ (uniquement sur Windows et plus simple) : [https://notepad-plus-plus.org/downloads/](https://notepad-plus-plus.org/downloads/)
* Phoenix Code (multiplateforme avec une interface épurée) : [https://phcode.io/#/home](https://phcode.io/#/home)

## Configurer un `venv`

Un `venv` est un environnement virtuel léger avec son propre dossier. Chaque environnement virtuel a son propre binaire Python et peut avoir sa propre liste de paquets Python installés.

C'est utile quand on veut isoler nos programmes pour ne pas interférer avec le système et pour une meilleure compatibilité.

Pour en créer un, suivez les instructions de la documentation Python : [Créer des `venv`](https://docs.python.org/fr/3.8/library/venv.html#creating-virtual-environments).

## Ouvrir un terminal

Le terminal (aussi appelé ligne de commande) est un logiciel permettant d'interagir directement avec le système d'exploitation ou les applications via des commandes textuelles.

{% tabs %}
{% tab title="Windows" %}
1. Cliquez sur le bouton Windows pour ouvrir la barre de recherche.
2. Tapez `cmd.exe` puis appuyez sur la touche Entrée.
3. Cliquez sur `cmd.exe` (probablement le premier résultat).
{% endtab %}

{% tab title="MacOS" %}
Ouvrez le Launchpad ou allez dans le dossier Applications. Ensuite, cherchez puis ouvrez le Terminal.
{% endtab %}

{% tab title="Linux" %}
Vous pouvez essayer Ctrl + Alt + T qui devrait fonctionner pour vous. Sinon, utilisez le moyen habituel d'ouvrir un application puis ouvrez le terminal (peut s'appeler différemment selon votre distribution).
{% endtab %}
{% endtabs %}

## Exécuter un programme Python

Pour exécuter du code en Python, il existe de nombreux moyens. Je vais en présenter 4 avec leurs avantages, leurs inconvénients et bien sûr comment les appliquer.

### CLI intégrée de Python

Ouvrez un terminal puis entrez la commande suivante :

```bash
python3
```

Ensuite, vous pourrez taper du code Python qui s'exécutera au fur et à mesure que vous taperez des lignes.

Cela vous permettra d'expérimenter rapidement des commandes et comprendre certains concepts mais sachez que, de cette manière, vous ne pourrez pas enregistrer vos programmes et certaines fonctionnalités vous resteront inaccessibles.

### Python dans le terminal

Premièrement, vous enregistrez votre programme dans un fichier comme `script.py`.

Ensuite, vous ouvrirez le terminal et entrerez la commande suivante en remplaçant avec votre nom de fichier :

```bash
python3 /chemin/du/dossier/script.py
```

Votre programme s'exécutera alors dans le terminal sauf si il est conçu pour avoir une GUI (interface graphique) et dans ce cas là, un fenêtre s'ouvrira.

C'est la méthode la plus utilisée pendant le développement.

### Via l'éditeur de code

Si vous utiliser un éditeur de code comme IDLE ou VS Code, vous avez peut-être une fonctionnalité qui vous permet d'exécuter le script directement, probablement accessible via un raccourci clavier ou un clic droit. A vous de voir.

### Ouvrir un exécutable crée avec PyInstaller

Souvent, pour distribuer un programme Python destiné à un public peu initié à l'informatique, on le package en exécutable. Un des outils les plus célèbres permettant cela est [PyInstaller](https://pyinstaller.org/en/stable/).

Je n'expliquerais pas ici comment créer un exécutable à partir de scripts Python (vous pouvez trouvez des informations sur cela dans leur [documentation](https://pyinstaller.org/en/stable/)).

Une fois que l'exécutable est prêt, vous avez simplement à l'ouvrir comme toute autre application sur le système d'exploitation adapté.

## Utiliser `pip`

`pip` est l'installeur de packages de Python. Ces packages peuvent contenir des bibliothèques de fonctions et autres données.

Il devrait normalement avoir été installé sur votre ordinateur si vous avez procédé à une installation standard de Python. Pour vérifier cela, entrez dans le terminal :

```bash
pip --version
```

Cela devrait vous retourner un numéro de version. Si ce n'est pas le cas, effectuez un réinstallation de Python ([#installer-python-3](pyco-prerequis.md#installer-python-3 "mention")).

Maintenant, vous devriez être en mesure d'installer des modules depuis `pip`. Essayez en entrant la commande suivante :

```bash
pip install markdown
```

Pour mettre à jour pip, exécutez la commande :

```bash
pip install --upgrade pip
```

Pour apprendre des commandes supplémentaires utiles, entrez :

```bash
pip -h
```

Vous devriez obtenir un liste organisée.
