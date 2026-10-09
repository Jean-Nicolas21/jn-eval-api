# Diagnostic

Une section par test en échec : renseignez ses quatre champs.

## testAddingALineToAnUnknownOrderIsNotFound

**Symptôme** : 

**Cause** :

**Règle du module en jeu** :

**Correctif** :

## testAddingALineToAPaidOrderIsAConflict

**Symptôme** :

**Cause** :

**Règle du module en jeu** :

**Correctif** :

## testAddingALineToMyOrder

**Symptôme** :

**Cause** :

**Règle du module en jeu** :

**Correctif** :

## testAddingALineWithAZeroQuantityIsUnprocessable

**Symptôme** :

**Cause** :

**Règle du module en jeu** :

**Correctif** :

## testListingKitchenTicketsReturnsMine

**Symptôme** :

**Cause** :

**Règle du module en jeu** :

**Correctif** :

## testListingKitchenTicketsWithoutTokenIsUnauthorized

**Symptôme** :

**Cause** :

**Règle du module en jeu** :

**Correctif** :

## testOpeningAnOrderIgnoresAnAbandonedOne

**Symptôme** :

**Cause** :

**Règle du module en jeu** :

**Correctif** :

## testPayingMyOrderMarksItPaid

**Symptôme** :

**Cause** :

**Règle du module en jeu** :

**Correctif** :

## testRefreshingTwiceWithTheSameTokenIsUnauthorized

**Symptôme** : Le test renvoit une 200 alors qu'il est attendu une 401.

**Cause** : gesdinet_jwt_refresh_token.yaml:5(single_use).

**Règle du module en jeu** : Il est souhaité d'avoir un refresh token à usage unique pour un soucis de sécurité pour éviter un que quelqu'un ai accès au refresh token de quelqu'un d'autre.

**Correctif** : dans le fichier mentionné dans la cause il faut passer le paramètre single_use à true.

## testRemovingALineFromSomeoneElsesOrderIsForbidden

**Symptôme** :

**Cause** :

**Règle du module en jeu** :

**Correctif** :
