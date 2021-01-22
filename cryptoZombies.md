# Crypto Zombies

Tutorial utilisation du language Solidity en créant une application sur la blockchain ethereum

## Les règles de bases

La blockchain est une __base de donnée__ éternelle décentralisé.

- Il toujours définir la version du compilateur par un `pragma solidity ^0.4.19`.
- Dans un fichier qui à pour extension `Contarct.sol`.
- *Les variables d'états* sont stocker définitivement dans la blockchain.

## Les types de données

- __uint__: unsigned int c'est à dire un entier non signé.
- __struct__: pour les données plus complexe.
- __string__: chaîne de caractère UTF-8.
- __fixedArray__: les tableaux fixes          // uint[2] fixedArray;
- __dynamicArray__: les tableaux dynamiques   // uint[]  dynamicArray;

On peut créer aussi un tableau de plusieurs structures.

On peut déclarer un tableau comme *public* et Solidity créera automatiquement une méthode *d'accès*.
La syntaxe est la suivante:

```
Person[] public people;
```

Pour déclarer une fonction, on utilise la syntaxe qui suit:

```
function eatHamburgers(string _name, uint _amount) {
// code here
}
```
Puis on appel la fonction comme ceci:

```
eatHamburgers("ujju16", 100);
```

__Remarque__: Par convention (mais ce n'est pas obligatoire), les noms des paramètres des fonctions commencent avec un trait de soulignement (_) afin de les différencier des variables globales. Nous utiliserons cette convention tout au long de notre tutoriel.

En Solidity, les fonctions sont __publiques par défaut__. Cela signifie que n'importe qui (ou n'importe quel contrat) peut appeler la fonction de votre contrat et exécuter son code.

Évidemment, ce n'est pas toujours ce que l'on veut, cela pourrait rendre votre contrat vulnérable aux attaques. Il est donc recommandé de marquer vos fonctions comme __private__ (privées) par défaut, puis de ne rendre __public__ (publiques) seulement les fonctions que vous voulez exposer à tout le monde.

Voici comment déclarer une fonction privée :

```
uint[] numbers;

function _addToArray(uint _number) private {
    numbers.push(_number);
}
```