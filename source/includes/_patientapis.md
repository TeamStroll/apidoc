# Patient APIs   

## submitPatientData

```shell
curl 'https://patient-qa.strollhealth.com/api/register'
-H 'origin: https://patient-dev.strollhealth.com'
-H 'accept-encoding: gzip, deflate, br'
-H 'x-requested-with: XMLHttpRequest'
-H 'accept-language: en-US,en;q=0.8'
-H 'authorization: Bearer AUTH_TOKEN'
-H 'content-type: application/json'
-H 'accept: application/json, text/javascript, */*; q=0.01'
-H 'referer: https://patient-dev.strollhealth.com/add_patient'
-H 'authority: patient-dev.strollhealth.com'
--data-binary '{"acceptTerms":true,"firstName":"Allison","gender":"F",
"lastName":"Liao","paymentMethod":"cash","paymentObject":{"pi":1,"mi":"",
"payerName":"Cash-Pay"},"phoneNumber":"(893) 707-4032","zip":"94704",
"email":"mrq50489@tqosi.com","phone":"(893) 707-4032",
"phoneNumberType":"Cell","birthDate":"2011-02-17"}'
--compressed
```

> The above command returns JSON structured like this:

```json
{
    "meta": {
        "href": null,
        "mediaType": "application/vnd.sh-v1.0+json"
    },
    "id": 7465,
    "autopilotContactId": null,
    "firstName": "Allison",
    "lastName": "Liao",
    "birthDate": "Thu Feb 17 00:00:00 PST 2011",
    "gender": "F",
    "email": "mrq50489@tqosi.com",
    "zip": "94704",
    "paySpecDTO": {
        "pi": "-1",
        "payerName": "Self",
        "mi": ""
    },
    "miInvalid": false,
    "rejectReason": null,
    "phoneNumber": "(893) 707-4032",
    "phoneNumberType": "Cell",
    "agreedToTerms": true,
    "termVersion": "1.0",
    "linkId": "e11c7174-428f-4064-bf5e-3f1b75638ceb",
    "middleInitital": null
}
```

This endpoint posts new user info to the database.

### HTTP Request
`POST https://patient-dev.strollhealth.com/api/register`
### Parameters

Parameter | Type | Description
--------- | ------- | -----------
acceptTerms | Boolean | True if patient clicked "accept terms" box, false otherwise
firstName | String | Patient's first name
gender | String | "M" or "F"
lastName | String | Patient's last name
paymentMethod | String | "cash" or "insurance"
paymentObject | Object | Describes the type of payment
phoneNumber | String | Patient's phone number formatted like "(xxx) xxx-xxxx"
zip | String | Patient's zip code
email | String | Patient's email address
phone | String | Patient's phone number formatted like "(xxx) xxx-xxxx"
phoneNumberType | String | "Cell", "Home", or "Work"
birthDate | String | Patient's birth date formatted like "YYYY-MM-DD"

### paymentObject Parameters

paymentObject Parameter | Type | Description
--------- | ------- | -----------
pi | String | Insurance payer's ID
mi | String | Insurance plan name
payerName | String | Insurance payer name
