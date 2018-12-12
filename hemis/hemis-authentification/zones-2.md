<!-- TITLE: intelligent-things -->
<!-- SUBTITLE: Une zone correspond à une pièce ou un ensemble de pièces de votre logement. Par exemple votre salon est une zone. Vous pouvez alors récupérer l'ensemble des zones de votre Hemis (logement) afin d'ajouter une image à celle-ci ou voir la températeur d'inertie.-->

# INTELLIGENT-THINGS
Le **session_token** récupéré via l’appel webservice de la documentation sur la connection sur un Hemis ainsi que la **base_url** de votre Hemis, va vous permettre d'effectuer des requêtes sur votre logement.
### GET
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