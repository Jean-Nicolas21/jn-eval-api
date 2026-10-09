# Diagnostic

Une section par test en échec : renseignez ses quatre champs.

## testAddingALineToAnUnknownOrderIsNotFound

**Symptôme** : 

**Cause** :

**Règle du module en jeu** :

**Correctif** :

## testAddingALineToAPaidOrderIsAConflict

**Symptôme** : Il est attendu une 409 conflit sur un order déjà payé si on tente d'y rajouter une ligne. Or le test reçoit bien une 201, ce qui suppose qu'on arrive à ajouter une ligne à un order.

**Cause** : OrderService:115(méthode addLine)

**Règle du module en jeu** : La méthode ne vérifie pas en premier le statut de l'order avant d'effectuer une quelconque opération/traitement dessus.

**Correctif** : On vérifie le statut de l'order pour voir s'il est déjà payé, auquel cas on throw(OrderAlreadyPaidException qui renvoit une 409 conflict) une exception pour sortir directement de la méthode.

## testAddingALineToMyOrder

**Symptôme** :

**Cause** :

**Règle du module en jeu** :

**Correctif** :

## testAddingALineWithAZeroQuantityIsUnprocessable

**Symptôme** : Attendu une 422 mais l'api renvoie une 201 ce qui suppose que l'on arréusi à add a line avec zero quantity.

**Cause** : OrderAddLineInput:$quantity

**Règle du module en jeu** : L'idée est de mettre un Assert pour tapper dans la validation de surface.

**Correctif** : Mettre un assert Positive.

## testListingKitchenTicketsReturnsMine

**Symptôme** : 

**Cause** : 

**Règle du module en jeu** : 

**Correctif** :

## testListingKitchenTicketsWithoutTokenIsUnauthorized

**Symptôme** : Le test attend une 401 sur l'accès aux tickets de cuisine mais l'api fournit une 200, ce qui suppose que l'api permet d'accéder aux tickets sans avoir de jeton.

**Cause** : KitchenTicket:15(ApiOperation)

**Règle du module en jeu** : Il n'y pas de security définit dans l'entity KitchenTicket, or cette route n'est accessible que l'on si on est connecté donc que si nous avons présenté un jeton.

**Correctif** : Il faut ajouter un parametre security dans l'opération avec comme spécification que l'on oblige à avoir un USER autorisé, donc avec jeton.

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
