**Note: si vous utilisez gedit 2 ou gedit 3.0 à 3.6, veuillez vous référer à la [documentation de gedit-markdown v1](https://github.com/jpfleury/gedit-markdown/tree/v1#readme). Ce qui suit est la documentation de la version 2 pour gedit 3.8 et 3.10.**

## Aperçu

gedit-markdown est un ensemble de fichiers ajoutant le support du langage [Markdown] (ou de la version spéciale [Markdown Extra]) dans gedit, l'éditeur de texte par défaut de Gnome.

Plus précisément, gedit-markdown ajoute:

- la coloration syntaxique des fichiers Markdown ainsi que des extraits de code pour accélérer la rédaction;

- le greffon *Aperçu Markdown*, affichant dans le panneau latéral ou inférieur de gedit un aperçu en HTML de la sélection ou du document en cours d'édition (ce greffon peut également être utilisé comme navigateur Web; voir la section *Utilisation*);

- un outil externe permettant d'exporter le code HTML de la sélection ou du document en cours d'édition;

- un jeu de couleurs, optionnel, colorant le code Markdown d'une manière plus ressemblante au rendu HTML.

[Markdown]: http://michelf.com/projets/php-markdown/concepts/
[Markdown Extra]: http://michelf.com/projets/php-markdown/extra/

<img src="https://raw.githubusercontent.com/jpfleury/gedit-markdown/master/doc/exemple1.png" width="684" height="779" alt="Coloration syntaxique par défaut du Markdown dans gedit." />

## Dépendances

- gedit-markdown v2 supporte gedit 3.8 et 3.10. Il est livré avec un installateur pour GNU/Linux.

- Le greffon «Aperçu Markdown» dépend du paquet `python3-markdown`.

- Pour les utilisateurs d'Ubuntu (et peut-être d'autres distributions également) 11.10 ou une version plus récente, le paquet `gir1.2-webkit-3.0` doit être installé pour que le greffon «Aperçu Markdown» fonctionne.

## Installation (ou mise à jour)

- [Télécharger l'archive de gedit-markdown v2.](https://github.com/jpfleury/gedit-markdown/archive/master.zip)

- Extraire l'archive.

- Ouvrir une console dans le dossier extrait.

- Lancer le script d'installation dans la console:

		./gedit-markdown.sh install

Le support de Markdown sera ajouté à l'utilisateur courant (l'installation se fait donc sans les droits d'administration). Le dossier créé par l'extraction de l'archive peut être supprimé après l'installation.

## Désinstallation

- Ouvrir une console dans le dossier extrait.

- Lancer le script de désinstallation dans la console, ce qui donne:

		./gedit-markdown.sh uninstall

## Utilisation

Avant toute chose, redémarrer gedit s'il est ouvert.

### Coloration syntaxique

La coloration syntaxique devrait s'activer automatiquement pour les fichiers reconnus comme étant des fichiers Markdown (extensions `.markdown`, `.md` ou `.mkd`), sinon choisir la coloration en allant dans *Affichage > Mode de coloration > Balisage* et cocher *Markdown*.

### Greffon *Aperçu Markdown*

Pour activer le greffon, aller dans *Édition > Préférences > Greffons* et sélectionner *Aperçu Markdown*.

Deux éléments sont ajoutés dans le menu *Outils* de gedit:

- *Actualiser l'aperçu Markdown*: permet d'afficher dans le panneau latéral ou inférieur l'aperçu en HTML du document courant ou de la sélection.

	Note: il y a deux autres façons d'actualiser l'aperçu:
	
	  - par le raccourci-clavier *Ctrl+Alt+m* (peut être modifié dans le fichier de configuration);
	
	  - en cliquant droit dans la zone d'aperçu (panneau latéral ou inférieur) et en sélectionnant l'élément *Actualiser l'aperçu*.

- *Afficher ou cacher l'aperçu Markdown*: permet d'afficher ou de cacher l'onglet d'aperçu dans le panneau de gedit.

	Note: le raccourci-clavier *Ctrl+Alt+v* (peut être modifié dans le fichier de configuration) peut être utilisé pour effectuer la même action.

En cliquant droit dans la zone d'aperçu, un menu contextuel apparaît et offre plusieurs options. Outre celles par défaut (page suivante, page précédente, copie, etc.), on trouve:

- *Copier l'URL courante*: permet de copier dans le presse-papiers l'adresse du document ou de la page dont le contenu est actuellement affiché dans l'onglet d'aperçu. S'il s'agit d'un document qui n'a pas encore été sauvegardé sur le disque, cet élément de menu est désactivé.

- *Aller à une autre URL*: permet de spécifier manuellement une URL locale ou distante d'un document ou d'une page à visiter dans l'onglet d'aperçu.

- Une des deux options suivantes, selon la valeur du paramètre `externalBrowser` du fichier de configuration:

	- *Ouvrir dans un navigateur externe*: permet d'ouvrir le lien cliqué dans un navigateur externe.

	- *Ouvrir dans le navigateur intégré*: permet d'ouvrir le lien cliqué directement dans le panneau de gedit.

- *Actualiser l'aperçu*: permet d'actualiser l'aperçu avec le contenu du document courant ou de la sélection.

- *Effacer l'aperçu*: efface le contenu de la zone d'aperçu.

Voici une capture d'écran du greffon lorsqu'il est situé dans le panneau inférieur:

<img src="https://raw.githubusercontent.com/jpfleury/gedit-markdown/master/doc/exemple3.png" width="684" height="886" alt="Aperçu en HTML d'un document Markdown dans le panneau inférieur de gedit." />

Voici maintenant le même greffon situé dans le panneau latéral (cliquer pour voir l'image au format original):

<a href="https://raw.githubusercontent.com/jpfleury/gedit-markdown/master/doc/exemple4-grand.png"><img src="https://raw.githubusercontent.com/jpfleury/gedit-markdown/master/doc/exemple4-petit.png" width="684" height="445" alt="Aperçu en HTML d'un document Markdown dans le panneau latéral de gedit." /></a>

À noter que lorsque le curseur passe au-dessus d'un lien dans la zone d'aperçu, une infobulle affiche l'URL:

<img src="https://raw.githubusercontent.com/jpfleury/gedit-markdown/master/doc/exemple5.png" width="684" height="128" alt="Infobulle affichant l'URL lorsque le curseur passe au-dessus d'un lien." />

### Extraits de code

Pour utiliser les extraits de code de Markdown, il faut activer le greffon *Extraits de code* dans le menu *Édition > Préférences > Greffons* de gedit. Ensuite, aller dans *Outils > Gérer les extraits de code...* pour consulter les différentes possibilités.

### Outil externe *Exporter en HTML*

Pour utiliser l'outil externe, il faut activer le greffon *Outils externes* dans le menu *Édition > Préférences > Greffons* de gedit. L'outil est accessible par le menu *Outils > Outils externes > Exporter en HTML* ou par le raccourci-clavier *Ctrl+Alt+h*. Le code Markdown du document en cours d'édition ou de la sélection sera converti en HTML, et le résultat sera inséré dans un nouveau document.

Pour modifier l'outil, aller dans *Outils > Gérer les outils externes...*.

### Jeu de couleurs optionnel

Un jeu de couleurs optionnel est installé automatiquement par gedit-markdown. Pour l'utiliser, aller dans le menu *Édition > Préférences > Police et couleurs > Jeu de couleurs* de gedit et sélectionner *Classic Markdown*. Cette coloration se rapproche d'un rendu HTML, par exemple les emphases fortes et les titres sont en gras et de couleur noire, les liens sont bleus et soulignés, etc. Ce jeu de couleurs resemble à ceci:

<img src="https://raw.githubusercontent.com/jpfleury/gedit-markdown/master/doc/exemple2.png" width="684" height="779" alt="Jeu de couleurs optionnel pour la coloration syntaxique du Markdown dans gedit." />

### Fichier de configuration

Le fichier de configuration de gedit-markdown est le suivant:

	$XDG_CONFIG_HOME/gedit/gedit-markdown.ini

ce qui correspond la plupart du temps à:

	$HOME/.config/gedit/gedit-markdown.ini

La section `markdown-preview` contient plusieurs paramètres:

- `externalBrowser`: ouverture des liens dans un navigateur externe par défaut. Valeurs possibles: `0` (ne pas ouvrir les liens dans un navigateur externe par défaut; valeur par défaut) ou `1` (ouvrir les liens dans un navigateur externe par défaut).

	Si `externalBrowser` vaut `0`, alors le menu contextuel apparaissant lors d'un clic droit sur un lien contiendra une option pour ouvrir le lien dans un navigateur externe. Si `externalBrowser` vaut `1`, alors le menu contextuel contiendra une option pour ouvrir le lien dans le navigateur interne.

- `panel`: emplacement de l'aperçu Markdown. Valeurs possibles: `bottom` (panneau inférieur; valeur par défaut) ou `side` (panneau latéral).

- `shortcut`: raccourci-clavier pour générer l'aperçu en HTML du document courant. La valeur par défaut est `<Control><Alt>m`.

- `version`: la version du langage Markdown à utiliser pour générer l'aperçu et exporter en HTML. Valeurs possibles: `extra` (valeur par défaut) ou `standard`.

- `visibility`: visibilité de l'onglet d'aperçu dans le panneau lors de l'ouverture de gedit. Valeurs possibles: `0` (caché) ou `1` (affiché; valeur par défaut).

- `visibilityShortcut`: raccourci-clavier pour afficher ou cacher l'onglet d'aperçu dans le panneau de gedit. La valeur par défaut est `<Control><Alt>v`.

## Précisions ou limitations

- La coloration syntaxique ainsi que les extraits de code pour Markdown (version standard) ont été ajoutés officiellement à GtkSourceView et gedit > 3.1.1. Dans l'installateur de gedit-markdown, si la version choisie est Markdown standard, une vérification sera effectuée pour ne pas copier des fichiers qui existent déjà (aucune vérification ne sera effectuée pour l'installation de Markdown Extra puisqu'il ne s'agit pas de la version livrée par défaut avec GtkSourceView et gedit > 3.1.1).

- D'anciennes versions de gedit-markdown ajoutaient également un type MIME pour les fichiers Markdown ainsi que la reconnaissance d'une extension supplémentaire (`.mdtxt`). Depuis que le support des fichiers Markdown a été ajouté directement dans la base de données partagée MIME `shared-mime-info` ([consulter le rapport de bogue][bogue27441]), gedit-markdown n'ajoute plus son propre fichier de type MIME pour Markdown. Aussi, dans un but de conformité avec la spécification, l'extension `.mdtxt` n'est plus supportée.

- Puisqu'il est possible d'ajouter du code HTML directement dans un texte écrit en Markdown, j'ai également ajouté la coloration syntaxique du HTML, ce qui a entre autres comme conséquence que le code Markdown dans du HTML est coloré syntaxiquement. Il faut cependant avoir en tête que selon la syntaxe officielle, du code Markdown dans un environnement HTML n'est pas transformé, il est affiché tel quel, et que selon la syntaxe du Markdown Extra, seul le code Markdown dans un bloc possédant un attribut `markdown` dont la valeur est de 1 (par exemple `<div markdown="1">`) est transformé.

- Markdown permet d'écrire du code dans un paragraphe. Pour ce faire, le code doit être entouré d'un accent grave (\`), ou de plusieurs, pourvu que le nombre soit identique de part et d'autre, et qu'il n'y ait pas dans le code un nombre identique d'accents qui se suivent. Exemples:

		`lorem lorem lorem lorem`
		
		`lorem lorem `` lorem lorem`
		
		`lorem lorem ````` lorem lorem`
		
		``lorem lorem lorem lorem``
		
		``lorem lorem ` lorem lorem``
		
		``lorem lorem ````` lorem lorem``

	Prendre note que gedit-markdown supporte la coloration jusqu'à 2 accents de part et d'autre du code.

- Un bloc de citation peut contenir des éléments Markdown de niveaux bloc ou texte, mais gedit-markdown supporte seulement la coloration des éléments de niveau texte (emphase, lien, etc.).

- Il n'est pas possible de savoir dans quel contexte une ligne se trouve, entre autres parce que le retour à la ligne ne peut pas être utilisé dans les expressions rationnelles de la coloration syntaxique. En voici des conséquences:

	- Selon la syntaxe du Markdown, pour écrire plusieurs paragraphes dans un item de liste, il faut indenter chaque paragraphe. Exemple:

			- Item A (paragraphe 1).

				Item A (paragraphe 2).

				Item A (paragraphe 3).

			- Item B.

		Il y a donc conflit au plan de la coloration syntaxique entre un paragraphe indenté à l'intérieur d'une liste (quatre espaces ou une tabulation) et une ligne de code indentée en dehors d'une liste (également quatre espaces ou une tabulation). Le choix a été fait de colorer une ligne de code seulement à partir de deux niveaux d'indentation.

	- Seul le soulignement d'un titre de style Setext est analysé et coloré. Il n'y a donc pas de garanti qu'il s'agit bien d'un soulignement de titre.

	- Avec Markdown Extra, quelques éléments sont analysés et colorés sans certitude qu'ils sont bien dans le bon contexte: l'attribut `id` pour un titre de style Setext, le deux-points séparateur dans une liste de définition et la ligne de séparation d'un tableau.

[bogue27441]: https://bugs.freedesktop.org/show_bug.cgi?id=27441

## Traduction

Le greffon *Aperçu Markdown* peut être traduit. Le fichier contenant les phrases à traduire est `plugins/markdown-preview/locale/markdown-preview.pot`.

## Développement

Le logiciel Git est utilisé pour la gestion de versions. [Le dépôt peut être consulté en ligne ou récupéré en local.](https://github.com/jpfleury/gedit-markdown)

## Licence

Auteur: Jean-Philippe Fleury (<http://www.jpfleury.net/contact.php>)  
Copyright © Jean-Philippe Fleury, 2009.

Ce programme est un logiciel libre; vous pouvez le redistribuer ou le
modifier suivant les termes de la GNU General Public License telle que
publiée par la Free Software Foundation: soit la version 3 de cette
licence, soit (à votre gré) toute version ultérieure.

Ce programme est distribué dans l'espoir qu'il vous sera utile, mais SANS
AUCUNE GARANTIE: sans même la garantie implicite de COMMERCIALISABILITÉ
ni d'ADÉQUATION À UN OBJECTIF PARTICULIER. Consultez la Licence publique
générale GNU pour plus de détails.

Vous devriez avoir reçu une copie de la Licence publique générale GNU avec
ce programme; si ce n'est pas le cas, consultez
<http://www.gnu.org/licenses/>.

### Matériel tiers

Le greffon d'aperçu Markdown est un fork de [Markdown Preview](https://wiki.gnome.org/Apps/Gedit/MarkdownSupport), sous licence GPL version 2 ou toute version ultérieure.
