# Compte-rendu du TP

## Question 1.1

insert_into_prio_queue() :
 - userinit()
 - fork()

remove_from_prio_queue() :
 - exit()


## Question 3.4

On a tapé la commande `nice 10 9` où 10 est le PID de la fonction `print D`.

## Question 3.5

Lorsqu'on repasse sur la console 0, on voit qu'aucun D ne s'affiche : l'implémentation de `nice` semble avoir fonctionné.

## Question 4.1

Lorsqu'on lance la commande `mutest`, on obtient les résultats suivants (tronqués) :

```
Fils, tu m'attendras
Fils, tu m'attendras
Fils, tu m'attendras
Fils, tu m'attendras
Oui, père.
Fils, tu m'attendras
Fils, tu m'attendras
Fils, tu m'attendras
```

On observe que le fils arrive à répondre au père avant la fin de l'utilisation du mutex par le père, ce qui ne devrait pas se produire si les mutex étaient correctement implémentés. \
En effet, le fils ne peut réaliser sa tâche qu'une fois la tâche du père terminée.

## Question 4.2

Lorsqu'on lance la commande `mutest2`, on obtient les résultats suivants (tronqués) :

```
$ mutest2
Result = 111
```
On constate que le résultat n'est pas celui attendu `Result = 100` car les deux processus tentent d'incrémenter (respectivement décrémenter) la même variable. Si les mutex étaient bien implémentés, ce problème n'apparaîtrait pas.

## Question 4.6

```
$ mutest
Fils, tu m'attendras
Fils, tu m'attendras
Fils, tu m'attendras
Fils, tu m'attendras
Fils, tu m'attendras
Oui, père.
```

```
$ mutest2
Result = 100
```

On obtient le bon résultat pour les deux tests : notre implémentation des mutex semble correcte.
