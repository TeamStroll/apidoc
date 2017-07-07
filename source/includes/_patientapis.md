# Patient APIs   

## getDrugList

```shell
curl 'https://patient-dev.strollhealth.com/api/getDrugList'
-H 'if-none-match: W/"1c095-VIDumywPrjdPlLwFZJSAr3BPbx8"'
-H 'accept-encoding: gzip, deflate, sdch, br'
-H 'x-requested-with: XMLHttpRequest'
-H 'accept-language: en-US,en;q=0.8'
-H 'authorization: Basic bXktdHJ1c3RlZC1jbGllbnQxOg=='
-H 'content-type: application/json'
-H 'accept: application/json, text/javascript, */*; q=0.01'
-H 'referer: https://patient-dev.strollhealth.com/'
-H 'authority: patient-dev.strollhealth.com' --compressed
```

> Example Response (First 3 entries)

```json
[
  {
    "genericName": "Aripiprazole",
    "brandName": "Abilify",
    "comboName": "Abilify (Aripiprazole)"
  },
  {
    "genericName": "acamprosate",
    "brandName": "Campral",
    "comboName": "Campral (acamprosate)"
  },
  {
    "genericName": "zafirlukast",
    "brandName": "Accolate",
    "comboName": "Accolate (zafirlukast)"
  }
]
```

This endpoint fetches the list of all drugs supported in Stroll's prescription portal, also corresponding to the list of drugs supported by Iodine.

### HTTP Request
`GET https://findcare.strollhealth.com/api/getDrugList`
