<!-- TITLE: scenario -->
<!-- SUBTITLE: A quick summary of Scenario -->

# SCENARIO
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