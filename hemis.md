# Accounts
-----
## Lister les comptes
`<base_url>/hemis/rest//WS_AccountManagement/list`
### Header

```text

Authorization: Bearer <session_token>

```

### Réponse
`200 Authorized`
```json
[
    {
        "id": "MyHemis",
        "name": "MyHemis",
        "type": null,
        "parentId": null,
        "surface": "0"
    }
]
```
-----
## Supprimer un compte
-----
## Informations d'un compte
-----
## Activer / Désactiver un objet
-----
## Lister les objets d'un compte
-----
## Rechercher les nouveaux IO objets
-----
## Rechercher les nouveaux OVP objets
-----
## Synchroniser un compte
-----
## Ajouter un compte
-----
# Agendas
Le **session_token** récupéré via l’appel webservice de la documentation sur la connection sur un Hemis ainsi que la **base_url** de votre Hemis, va vous permettre d'effectuer des requêtes sur votre logement.
## Lister les agendas d'une zone
`<base_url>/hemis/rest/zones`
### Header

```text

Authorization: Bearer <session_token>

```

### Réponse
`200 Authorized`
```json
[
    {
        "id": "MyHemis",
        "name": "MyHemis",
        "type": null,
        "parentId": null,
        "surface": "0"
    }
]
```
-----
## Supprimer un agenda
-----
## Récupérer un agenda
-----
## Ajouter un agenda
-----
## Mettre à jour un agenda
-----
# Ambiances
Le **session_token** récupéré via l’appel webservice de la documentation sur la connection sur un Hemis ainsi que la **base_url** de votre Hemis, va vous permettre d'effectuer des requêtes sur votre logement.
## get /ambiances
`<base_url>/hemis/rest/zones`
### Header

```text

Authorization: Bearer <session_token>

```

### Réponse
`200 Authorized`
```json
[
    {
        "id": "MyHemis",
        "name": "MyHemis",
        "type": null,
        "parentId": null,
        "surface": "0"
    }
]
```
-----
## post /ambiances
-----
# Factors
Le **session_token** récupéré via l’appel webservice de la documentation sur la connection sur un Hemis ainsi que la **base_url** de votre Hemis, va vous permettre d'effectuer des requêtes sur votre logement.
## get
`<base_url>/hemis/rest/zones`
### Header

```text

Authorization: Bearer <session_token>

```

### Réponse
`200 Authorized`
```json
[
    {
        "id": "MyHemis",
        "name": "MyHemis",
        "type": null,
        "parentId": null,
        "surface": "0"
    }
]
```
-----
# Gateways
Le **session_token** récupéré via l’appel webservice de la documentation sur la connection sur un Hemis ainsi que la **base_url** de votre Hemis, va vous permettre d'effectuer des requêtes sur votre logement.
## get
`<base_url>/hemis/rest/zones`
### Header

```text

Authorization: Bearer <session_token>

```

### Réponse
`200 Authorized`
```json
[
    {
        "id": "MyHemis",
        "name": "MyHemis",
        "type": null,
        "parentId": null,
        "surface": "0"
    }
]
```
-----
# Intelligent-things
Le **session_token** récupéré via l’appel webservice de la documentation sur la connection sur un Hemis ainsi que la **base_url** de votre Hemis, va vous permettre d'effectuer des requêtes sur votre logement.
### get
`<base_url>/hemis/rest/zones`
### Header

```text

Authorization: Bearer <session_token>

```

### Réponse
`200 Authorized`
```json
[
    {
        "id": "MyHemis",
        "name": "MyHemis",
        "type": null,
        "parentId": null,
        "surface": "0"
    }
]
```
-----
# Scenario
Le **session_token** récupéré via l’appel webservice de la documentation sur la connection sur un Hemis ainsi que la **base_url** de votre Hemis, va vous permettre d'effectuer des requêtes sur votre logement.
# get
`<base_url>/hemis/rest/zones`
### Header

```text

Authorization: Bearer <session_token>

```

### Réponse
`200 Authorized`
```json
[
    {
        "id": "MyHemis",
        "name": "MyHemis",
        "type": null,
        "parentId": null,
        "surface": "0"
    }
]
```
-----
# Zones
Une zone correspond à une pièce ou un ensemble de pièces de votre logement. Par exemple votre salon est une zone. Vous pouvez alors récupérer l'ensemble des zones de votre Hemis (logement) afin d'ajouter une image à celle-ci ou voir la températeur d'inertie.
## Lister toutes les zones
`<base_url>/hemis/rest/zones`
### Header

```text

Authorization: Bearer <session_token>

```

### Réponse
`200 Authorized`
```json
[
    {
        "id": "MyHemis",
        "name": "MyHemis",
        "type": null,
        "parentId": null,
        "surface": "0"
    }
]
```
-----
## Ajouter une zone
-----
## Supprimer une zone par id
-----
## Retourner une zone par id
-----
## Mettre à jour une zone
-----
## Mettre à jour l'image d'une zone
-----
## Retourner l'image d'une zone
-----
## Retourner la température d'inertie d'une zone
-----
## Mettre à jour la température d'inertie d'une zone
-----