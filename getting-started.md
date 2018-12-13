# Getting-started
## Bienvenue
-----

Bienvenue sur la documentation des APIS d'Ubiant.
Si ce sont vos premiers pas avec Ubiant, vous êtes au bon endroit.
Vous disposez déjà d'un compte?
Si oui, vous pouvez directement aller à l'étape [Vos premiers pas avec Ubiant](http://192.168.203.128/getting-started#Vos-premiers-pas-avec-Ubiant)
Si non, commencer par l'étape **L'application** afin de télécharger celle-ci et de vous créer un compte.

## L'Application

-----

Il est possible que vous n'ayez pas encore téléchargé notre application.
Dans ce cas, elle est disponnible:
Ici pour Android: [Google play](https://play.google.com/store/apps/details?id=com.ubiant.flexom&hl=fr)
Ici pour Ios:  [Apple store](https://itunes.apple.com/fr/app/flexom-2-0/id1126876479?mt=8)

-----

## Vos premiers pas avec Ubiant
Nous considérons que vous avez passé l'étape d'authentification qui vous permettra de récupérer vos identifiants d'accès.
Si non, référez vous à la documentation ci-dessous
[Authentification](/authentification)

-----



L’architecture serveur Hemis est une architecture distribuée. Les logements sont gérés par des processus séparés répartis sur différents serveurs. Afin de se connecter sur un logement il faut donc se connecter en premier sur le serveur hemisphere. Le serveur hemisphere est un serveur qui recense les utilisateurs, les logements et permet de récupérer les informations nécessaires à la connexion sur un Hemis (logement).


## Login sur Hemisphere


-----


La première étape consiste à s'identifier sur Hemisphere afin de récupérer votre **user_token** d'identification.
### POST
`https://hemisphere-aws.ubiant.com/users/signin`
### Header

```text
Content-Type: application/json
```

### Body
```json
{

"email": "email",

"password": "mot de passe"

}
```
En remplacant les champs par son email et son mot de passe.
### Réponse
`200 Authorized`
```json
{

"id": "id",

"first_name": " first_name ",

"last_name": " last_name ",

"username": " username ",

"email": " email ",

"locale": "fr",

"token": "user_token",

"activated": true,

"last_login": 1469192079156,

"role": "BASIC",

"nb_max_hemis": 5,

"tags": []

}
```
Avec vos informations personnelles.
### Réponse erreur
`401 Unauthorized`
```json
{
    "message": "Votre email ou votre votre mot de passe est incorrect.",
    "error_id": "UNAUTHORIZED"
}
```
Dans ce cas, vérifiez que:
* La requête est de type POST
* Le header est mentionné
* Le body contient vos bonnes informations
* L'url de la requête contient bien le **s** de http(**s**)
* Que vous possédez bien un compte

`415 Unsupported Media Type`

```json

```

## Récupération de mon Hemis


-----



Le **user_token** récupéré via l’appel webservice de l'étape précédente, va vous permettre de récupérer la liste des logements en le placant dans le header de la requête.
Cette deuxième étape consiste à récupérer les informations d'un Hemis. C'est à dire l'**authorization_token**,  l'**hemis_base_url** et le **kernel_slot**.
### GET 
`https://hemisphere-aws.ubiant.com/buildings/mine/infos`
### Header

```text
Content-Type: application/json

Authorization: Bearer <user_token>
```


### Réponse
`200 Authorized`
```json
[

{

"authorizationToken": "authorization_token",

"buildingId": "id",

"address": {

"id": "id",

"address": "",

"latitude": 0 ,

"longitude": 0 ,

"city": "Paris",

"county": "Paris",

"region": "",

"street_name": "",

"formatted_address": "",

"p": "",

"c": "",

"sn": ""

},

"hemis_base_url": "hemis_base_url",

"kernel_slot": "kernel_slot"

}

]
```
Il est possible que cette réponse soit vide si vous n'avez pas encore de logement.

```json
[]
```

### Réponse erreur
`401 Unauthorized`
```json
{
    "message": "Vous n'êtes pas autorisé à effectuer cette requête",
    "error_id": "DISCONNECTED"
}
```
Dans ce cas, vérifiez que:
* La requête est de type GET cette fois-ci
* Le header est mentionné avec le champs **Authorization:** et le contenu **Bearer <user_token>** ou dans l'onglet Authorization de Postman plutôt que le header si vous préferez en choisissant le Type "Bearer Token".
* Vous avez bien mis un et un seul espace après le mot Bearer du contenu du champs d'Authorization.
* L'url de la requête contient bien le **s** de http(**s**)
* Dans le cas où vous n'avez pas d'erreurs 401 mais bien une réponse 200, peut être que vous n'avez actuellement pas encore de logement et que la réponse est donc vide.

## Connection sur mon Hemis 


-----


L'**authorization_token**,  l'**hemis_base_url** et le **kernel_slot** récupérés via l’appel webservice de l'étape précédente, va vous permettre de vous connecter sur un logement spécifique en le placant dans le header de la requête.
Cette étape est effectuée afin de récupérer votre **session_token** d'identification sur votre Hemis (logement).
### POST 
`<hemis_base_url>/WS_UserManagement/login`
### Header

```text
Content-Type: x-www-form-urlencoded
```

### Body
```text
email: <email>

password: <authorization_token>

kernelId: <kernel_slot>
```
### Réponse
`200 Authorized`
```json
{
    "token": "session_token",
    "role": "OWNER",
    "hemisVersion": "1.9.1.0-SNAPSHOT.2018",
    "timeZone": "Europe/Paris",
    "offset": 3600000,
    "permissions": []
}
```
### Réponse erreur
`415 Unsupported Media Type`

```json
{
    "message": "RESTEASY003065: Cannot consume content type",
    "cause": null,
    "errors": null,
    "error_id": "UNSUPPORTED_MEDIA_TYPE",
    "target": null
}
```
Dans ce cas, vérifiez que:
* Vous avez bien mis  "x-www-form-urlencoded".

`401 Unauthorized`

```json
{
    "message": "Failed to log user.",
    "cause": null,
    "errors": null,
    "error_id": "UNAUTHORIZED",
    "target": null
}
```

Dans ce cas, vérifiez que:
* L'**authorization_token**,  l'**hemis_base_url** et le **kernel_slot** placés dans le body.
* L'url de la requête contient bien le **s** de http(**s**)

## Accès à l’API d’un Hemis


-----



Vous avez alors récupérer le **session_token** de l'Hemis (logement) sur lequel vous voulez vous connecter.

-----

