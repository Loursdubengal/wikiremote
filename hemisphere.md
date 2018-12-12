# Authentification sur Hemisphere


-----
## I. Login sur Hemisphere


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






