# Tideman
Programme qui organise une élection Tideman

 la pluralité, qui suivent un algorithme très simple pour déterminer le vainqueur d'une élection : chaque électeur obtient une voix, et le candidat avec le plus de voix l'emporte.

Mais le vote à la pluralité présente certains inconvénients. Que se passe-t-il, par exemple, dans une élection avec trois candidats, et les bulletins ci-dessous sont exprimés ?

Cinq bulletins, égalité entre Alice et Bob

Un vote à la pluralité déclarerait ici une égalité entre Alice et Bob, puisque chacun a deux voix. Mais est-ce le bon résultat ?

Il existe un autre type de système de vote connu sous le nom de système de vote par classement. Dans un système à choix par ordre, les électeurs peuvent voter pour plus d'un candidat. Au lieu de simplement voter pour leur premier choix, ils peuvent classer les candidats par ordre de préférence. Les bulletins de vote résultants pourraient donc ressembler à ce qui suit.

Trois tours de scrutin, avec des préférences classées

Ici, chaque électeur, en plus de préciser son premier candidat de préférence, a également indiqué ses deuxième et troisième choix. Et maintenant, ce qui était auparavant une élection à égalité pourrait maintenant avoir un gagnant. La course était à l'origine à égalité entre Alice et Bob. Mais l'électeur qui a choisi Charlie a préféré Alice à Bob, donc Alice pourrait ici être déclarée gagnante.

Le vote à choix classé peut également résoudre un autre inconvénient potentiel du vote à la pluralité.

Pour gérer cela, l'algorithme de Tideman doit veiller à éviter de créer des cycles dans le graphe candidat. Comment fait-il cela ? L'algorithme verrouille d'abord les bords les plus forts, car ceux-ci sont sans doute les plus importants. En particulier, l'algorithme de Tideman spécifie que les arêtes de correspondance doivent être « verrouillées » sur le graphique un à la fois, en fonction de la « force » de la victoire (plus il y a de personnes qui préfèrent un candidat à leur adversaire, plus la victoire est forte) . Tant que l'arête peut être verrouillée dans le graphique sans créer de cycle, l'arête est ajoutée ; sinon, le bord est ignoré.

voir le lien vers la page wikipedia : https://fr.wikipedia.org/wiki/M%C3%A9thode_Condorcet_avec_rangement_des_paires_par_ordre_d%C3%A9croissant

En termes plus formels, la méthode de vote Tideman se compose de trois parties :

Décompte : Une fois que tous les votants ont indiqué toutes leurs préférences, déterminez, pour chaque paire de candidats, qui est le candidat préféré et par quelle marge ils sont préférés.
Trier : Triez les paires de candidats par ordre décroissant de force de victoire, où la force de victoire est définie comme étant le nombre d'électeurs qui préfèrent le candidat préféré.
Verrouiller : En commençant par la paire la plus forte, parcourez les paires de candidats dans l'ordre et « verrouillez » chaque paire dans le graphe candidat, tant que le verrouillage de cette paire ne crée pas de cycle dans le graphe.
Une fois le graphique terminé, la source du graphique (celle sans arêtes pointant vers elle) est la gagnante !
