# Table of contents / Table de matières :
1. [ Description (English). ](#en)
    - Repository Organization
    - Makefile
    - Part 1 - Householder transformations
    - Part 2 - Bidiagonal formatting
    - Part 3 - QR and SVD transformations
    - Part 4 - Applying SVD to image compression
2. [ Description (Français). ](#fr)
    - Organisation du dépôt
    - Makefile
    - Partie 1 - Transformations de Householder
    - Partie 2 - Mise sous forme bidiagonale
    - Partie 3 - Transformations QR et SVD
    - Partie 4 - Application de la SVD à la compression d'image


<a name="en"></a>
# Description [English]

The aim of this project is to program an algorithm for image compression using matrix techniques based on SVD factorization. This type of algorithm is related to lossy compression algorithms, the best known of which is certainly the JPEG compression algorithm, itself usually based on the Discrete Cosine Transform (DCT), a transformation similar to the discrete Fourier transform.

## Repository organization

The project code is located in the **src** directory. For each part, there is a corresponding code named after its part number.
For example, the code for part 1 can be found in the file `part1.py`.
It also contains the various test files corresponding to the different parts.
For example, the tests for part 1 are in the `test1.py` file. 

In the **sections** directory, you can find the various latex files corresponding to the different parts included in the `report.tex` file.

## Makefile
The **Makefile** has several targets, and by executing the `make test` command, you can run tests on all the parts. 
The `make` command generates the report, and to obtain details on the compilation of the report, run the `make verbose` command.

## Part 1 - Householder transformations
By running `src/part1.py`, we can compare the execution time of our functions with that of conventional matrix products.

The `src/test1.py` file verifies that these functions give results close to those expected, with an adjustable `eps` deviation.

## Part 2 - Bidiagonal formatting
The `src/part2.py` file contains functions only, and acts as a module in relation to the following parts.

For testing purposes, in the `src/test2.py` file, we test our bidiagonalization function on various matrices, checking that the result is indeed a bidiagonal matrix, and that the product of the returned matrices is close to the starting matrix, with a `eps` deviation that we can modify.

## Part 3 - QR and SVD transformations
Running `src/part3.py` generates a figure showing the convergence speed of the matrix diagonalization method starting from a bidiagonal matrix.

Running `src/test3.py`, we perform checks on this diagonalization method, as well as our QR decomposition and SVD function. In each case, we check that the matrices returned have the expected characteristics (orthogonal matrix, upper triangular, diagonal, etc.).

## Part 4 - Applying SVD to image compression
This part uses the `res/part-4.png` file, which we consider to be the _original_ image. Running this file first generates two examples of image compression using the SVD method, in comparison with the original image.
Next, a figure shows the distances to the original image, on a logarithmic scale.
Finally, the last figure shows the file size in number of values, relative to the compression rank.

As far as tests are concerned, the `src/test-4.py` file verifies that the post-compression images are indeed close to the compressed images supplied.


<a name="fr"></a>
# Description [Français]

Le but de ce projet consiste à programmer un algorithme permettant de faire de la compression d’images en utilisant des techniques matricielles basée sur la factorisation SVD. Ce type d’algorithme est à relier aux algorithmes de compression avec pertes, dont le plus connu est certainement l’algorithme de compression JPEG, lui-même basé usuellement sur la Discrete Cosine Transform (DCT), une transformation voisine de la transformée de Fourier discrète.

## Organisation du dépôt

Le code du projet se trouve dans le répertoire **src**. Pour chaque partie, il y a un code correspondant nommé au numéro de sa partie.
Par exemple, le code de la partie 1 se trouve dans le fichier `part1.py`.
On y trouve aussi les différents fichiers de tests qui correspondent aux différentes parties.
Par exemple, les tests pour la partie 1 sont dans le fichier `test1.py`. 

Dans le répertoire **sections**, on peut trouver les différents fichiers latex correspondant aux différentes parties incluses dans le fichier `rapport.tex`.

## Makefile
Le **Makefile** dispose de plusieurs cibles, et permet en exécutant la commande `make test` de lancer des tests sur toutes les parties. 
La commande `make` permet de générer le rapport, et pour obtenir des détails sur la compilation du rapport, il faut lancer la commande `make verbose`.

## Partie 1 - Transformations de Householder
En exécutant `src/part1.py`, on effectue une comparaison du temps d'exécution de nos fonctions par rapport à des produits classiques de matrices classiques.

Le fichier `src/test1.py` vérifie que ces fonctions donnent des résultats proches de ceux attendus, avec un écart `eps` réglable.

## Partie 2 - Mise sous forme bidiagonale
Le fichier `src/part2.py` dispose seulement de fonctions, et agit comme un module par rapport aux parties suivantes.

Pour les tests, sur le fichier `src/test2.py`, on teste notre fonction de bidiagonalisation sur des matrices variées, en vérifiant que le résultat est bien une matrice bidiagonale, et que le produit des matrices renvoyées est proche à la matrice de départ, avec un écart `eps` que l'on peut modifier.

## Partie 3 - Transformations QR et SVD
L'exécution du fichier `src/part3.py` entraîne la génération d'une figure montrant la vitesse de convergence de la méthode de diagonalisation de matrice à partir d'une matrice bidiagonale.

En exécutant `src/test3.py`, on effectue des vérifications sur cette méthode de diagonalisation, ainsi que notre décomposition QR et notre fonction de SVD. Pour chacun des cas, on vérifie que les matrices renvoyées ont bien les caractéristiques attendues (matrice orthogonale, triangulaire supérieure, diagonale, ...).

## Partie 4 - Application de la SVD à la compression d'image
Cette partie utilise le fichier `res/part-4.png`, que l'on considère comme l'image _originale_. Exécuter ce fichier génère d'abord deux exemples de compression d'image utilisant la méthode SVD, en comparaison avec l'image originale.
Ensuite, une figure montre les distances à l'image originale, avec une échelle logarithmique.
Enfin, la dernière figure montre la taille du fichier en nombre de valeurs, par rapport au rang de la compression.

En ce qui concerne les tests, le fichier `src/test-4.py` vérifie que les images après compression sont bien proches des images compressées fournies.
