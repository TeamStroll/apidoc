---
title: Stroll Api

language_tabs:
  - shell

toc_footers:
  - <a href='https://github.com/tripit/slate'>Documentation Powered by Slate</a>

includes:
  - dtos
  - appointmentapis
  - patientapis
  - platformapis
  - faxrequests
  - errors

search: true
---

# Introduction

Welcome to the Stroll Health API!


# Authentication

> To authorize, use this code:

```shell
require 'stroll'

api = Stroll::APIClient.authorize!('meowmeowmeow')
```



> Make sure to replace `meowmeowmeow` with your API key.

Stroll uses OAuth2 to allow access to the API.

Stroll expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: meowmeowmeow`

<aside class="notice">
You must replace <code>meowmeowmeow</code> with a user's authorization token.
</aside>

# Platform Microservice

## getSimplePrices

Gets a list of Radiology facilities

```shell
curl 'http://localhost:9080/api/getSimplePrices'
-H 'Authorization: Basic bXktdHJ1c3RlZC1jbGllbnQxOg=='
-H 'Origin: http://localhost:9080'
-H 'Accept-Encoding: gzip, deflate, br'
-H 'Content-Type: application/json'
-H 'Accept: application/json, text/javascript, */*; q=0.01'
-H 'Referer: http://localhost:9080/results'
-H 'X-Requested-With: XMLHttpRequest'
--data-binary '{"cptCodeIds":"76604","userId":-1,"lat":37.866536,"lng":-122.257996,"zipCode":"94704","payerId":1,"planId":"","bilateral":"","pricingException":"","quantity":null}'
--compressed
```

> The above command returns JSON structured like this:

```json
{
    "meta": {
        "href": "/prices",
        "mediaType": "application/vnd.sh-v1.0+json"
    },
    "costDTOs": [
        {
            "code": "76604",
            "cost": "N/A",
            "facilityId": "10083",
            "patientId": "-1",
            "fromAddress": null,
            "facility": "Pamf - San Carlos Radiology Center",
            "address": "301 Industrial Rd, Level 1, San Carlos, CA 94070",
            "image": "https://provider-dev.strollhealth.com/sh/images/generic_facility_image.png",
            "distance": "24.8 mi",
            "phone": "5426",
            "fax": "6505517039",
            "lat": 37.50716,
            "lng": -122.26052,
            "color": "3A",
            "frontColor": "green",
            "index": 0,
            "selected": false,
            "openingsDTO": null,
            "quality": 3,
            "languages": [],
            "hasFreeParking": false,
            "hasShuttleService": false,
            "hasWifi": false,
            "hasCoffee": false,
            "adaaccessible": false
        },
        "...More"
    ],
    "insuranceDTO": {
        "patientId": null,
        "serviceType": "Diagnostic Medical",
        "deductDate": null,
        "plan": "Medicare Part B",
        "payerId": null,
        "payer": null,
        "inIndividDeductTotal": 147,
        "outIndividDeductTotal": 0,
        "inIndividDeductRemain": 147,
        "outIndividDeductRemain": 0,
        "inFamilyDeductTotal": -1,
        "outFamilyDeductTotal": -1,
        "inFamilyDeductRemain": -1,
        "outFamilyDeductRemain": -1,
        "inIndividMaxTotal": -1,
        "outIndividMaxTotal": -1,
        "inIndividMaxRemain": -1,
        "outIndividMaxRemain": -1,
        "inFamilyMaxTotal": -1,
        "outFamilyMaxTotal": -1,
        "inFamilyMaxRemain": -1,
        "outFamilyMaxRemain": -1,
        "incopay": -1,
        "incopayOutpatient": 0,
        "outcopay": -1,
        "incoinsurance": 0.2,
        "outcoinsurance": -1,
        "tier1Deduct": 0,
        "tier1FamilyDeduct": 0,
        "tier1Remain": 0,
        "tier1FamilyRemain": 0,
        "tier1MaxDeduct": 0,
        "tier1FamilyMaxDeduct": 0,
        "tier1MaxRemain": 0,
        "tier1FamilyMaxRemain": 0,
        "tier1Copay": 0,
        "tier1Coinsurance": 0
    },
    "notes": null,
    "simpleOpeningsByFacIds": {}
}
```

### HTTP Request

`POST https://provider.strollhealth.com/api/getSimplePrices`

### Parameters

Parameter | Type | Description
--------- | ------- | -----------
Results Request DTO| Object | A data transfer object holds all the parameters in a single object.

#### Results Request DTO

Parameter | Type | Description
--------- | ------- | -----------
Bilateral| Boolean | Indicates if the procedure is bilateral.
CPT Code Id | String | Identifies the type of procedure.
User Id | Number | Id for logged in users.
Lat | Number | User's Latitude position.
Lng | Number | User's Longitude position.
Zip Code | String | User's zip code.
Payer Id | Number | Unique Id corresponding to the payer.
Plan Id | String | Unique Id corresponding to the plan.
Pricing Exception | String | If needed with CPT code, this indicates what possible pricing exceptions are included.
Quantity | Number | ??


## Get Clinical Indication Suggestion

This endpoint retrieves a list of clinical indications that contain the substring parameter.

```shell
curl 'https://provider-dev.strollhealth.com/api/getClinicalIndication'
-H 'origin: https://provider-dev.strollhealth.com'
-H 'accept-encoding: gzip, deflate, br'
-H 'x-requested-with: XMLHttpRequest'
-H 'accept-language: en-US,en;q=0.8'
-H 'authorization: Bearer meowmeowmeow'
-H 'content-type: application/json'
-H 'accept: application/json, text/javascript, */*; q=0.01'
-H 'referer: https://provider-dev.strollhealth.com/provider_dashboard/finalize_order'
-H 'authority: provider-dev.strollhealth.com'  
--data-binary '{"substring":"bas","limit":5}'
--compressed
```

> The above command returns JSON structured like this:

```json
{
    "meta": {
        "href": null,
        "mediaType": "application/vnd.sh-v1.0+json"
    },
    "icd10DTOs": [
        {
            "meta": {
                "href": null,
                "mediaType": "application/vnd.sh-v1.0+json"
            },
            "code": "Y9333",
            "description": "Activity, BASE jumping"
        },
        {
            "meta": {
                "href": null,
                "mediaType": "application/vnd.sh-v1.0+json"
            },
            "code": "Y9364",
            "description": "Activity, baseball"
        },
        {
            "meta": {
                "href": null,
                "mediaType": "application/vnd.sh-v1.0+json"
            },
            "code": "Y9367",
            "description": "Activity, basketball"
        },
        {
            "meta": {
                "href": null,
                "mediaType": "application/vnd.sh-v1.0+json"
            },
            "code": "Y0802XA",
            "description": "Assault by strike by baseball bat, initial encounter"
        },
        {
            "meta": {
                "href": null,
                "mediaType": "application/vnd.sh-v1.0+json"
            },
            "code": "Y0802XS",
            "description": "Assault by strike by baseball bat, sequela"
        }
    ]
}
```

### HTTP Request

`POST https://provider-dev.strollhealth.com/api/getClinicalIndication`

### Parameters

Parameter | Type | Description
--------- | ------- | -----------
Substring | String | Desired string each indication contains in the results.
Limit | Number | The number of results shown.


## orderFax

EXPLANATION

```shell
curl 'https://provider-qa.strollhealth.com/api/addFaxRequest'
-H 'origin: https://provider-qa.strollhealth.com'
-H 'accept-encoding: gzip, deflate, br'
-H 'x-requested-with: XMLHttpRequest'
-H 'accept-language: en-US,en;q=0.8'
-H 'authorization: Bearer meowmeowmeow'
-H 'content-type: application/json'
-H 'accept: application/json, text/plain, */*'
-H 'referer: https://provider-qa.strollhealth.com/provider_dashboard/finalize_order'
-H 'authority: provider-qa.strollhealth.com'
--data-binary '{"sendFaxToFacility":true,"currentFacilityId":0,"createDateAsString":"2017-07-07","chosenFacilityId":10018,"patientEmail":"TunjiAli@strollhealth.com","cptCode":"73564","facilityFaxRequestType":1,"physicianFaxRequestType":1,"patientFaxRequestType":0,"patientFirstName":"Tunji","referringPhysicianId":1,"patientId":5533,"patientLastName":"Ali","patientPhoneNumber":"(000) 000-0000","referringPhysicianName":"James Smith, MD","sendFaxToPatient":false,"sendFaxToPhysician":true,"costsDTO":{},"userId":1,"practiceId":2,"faxDTO":{"member_ID":"","insurance_carrier":"Self","dob":"1977-02-03","facility_name":"Inview Imaging Lafayette","facility_address_1":"970 Dewing Ave","facility_address_2":"Suite 100","facility_address_3":"Lafayette, CA 94549","facility_phone":"(770) -","facility_fax":"(844) 787-6555","patient_name":"Tunji Ali","male_checkbox":false,"female_checkbox":true,"pregnant_checkbox":false,"patient_phone_number":"(000) 000-0000","cell_checkbox":true,"office_checkbox":false,"home_checkbox":false,"primary_language":"","estimate_out_of_pocket_cost":"$130.00","referring_physician_NPI":"123456","referring_physician_phone":"(320) 583-3421","referring_physician_address":"Shattuck Ave 2150 Berkeley, CA","referring_physician_fax":"(844) 787-6555","physician_portal_checkbox":false,"physician_portal_url":"","fax_written_report_checkbox":true,"fax_STAT_checkbox":false,"phone_STAT_checkbox":false,"phone_call_report_checkbox":false,"send_CD_checkbox":true,"send_patient_with_CD_checkbox":true,"send_films_checkbox":true,"send_patient_with_films_checkbox":true,"courier_films_checkbox":false,"courier_films_to_name":"","courier_films_to_address":"","procedure_short_description":"X-Ray Knee, Complete","cpt_code":"73564","ICD10_code":"Y9333","icd10_code":"Y9333","ICD9_code":"Y9333","icd9_code":"Y9333","clinical_indication":"Activity, BASE jumping","comparison_study_checkbox":false,"medication_provided_checkbox":false,"medication_provided_description":"","procedure_locations":"","special_instructions":"bilateral procedure; ","previous_MRIMRA_checkbox":false,"symptom_onset_date":"","claustrophobic_checkbox":false,"pacemaker_checkbox":false,"pacemaker_description":"","other_implanted_metal_checkbox":false,"other_implanted_metal_description":"","iv_contrast_allergy_checkbox":false,"iv_contrast_allergy_description":"","creatinine":"","oral_contrast_allergy_checkbox":false,"oral_contrast_allergy_description":"","renal_disease_checkbox":false,"diabetes_checkbox":false,"other_allergies_checkbox":false,"other_allergies_description":"","previous_MRIMRA_date":"","creatinine_date":"","taking_metformin_checkbox":false,"referring_physician_name":"James Smith, MD","referral_date":"2017-07-07","referring_physician_signature":"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","patientLastName":"Ali","patientFirstName":"Tunji","patientEmail":"TunjiAli@strollhealth.com","userId":1,"practiceId":2,"cash_alert":"Cash Pay","prior_auth_number":"","received_prior_auth_checkbox":false},"appointment":{}}'
--compressed
```

> The above command returns JSON structured like this:

```json
{
    "meta": {
        "href": "/pendingFaxRequests/2023",
        "mediaType": "application/vnd.sh-v1.0+json"
    },
    "id": 2023,
    "faxRequestId": 2023,
    "appointment": {
        "meta": {
            "href": null,
            "mediaType": "application/vnd.sh-v1.0+json"
        },
        "appointmentId": 2195,
        "equipmentId": 0,
        "patientId": 5533,
        "facilityId": 10018,
        "faxRequestId": 2023,
        "startTime": 28800000,
        "endTime": 28800000,
        "cptCode": "73564",
        "cost": 130,
        "reasonNotYetScheduled": "N/A",
        "stillWantToSchedule": true,
        "orderStatus": "PENDING_AUTH",
        "patientDTO": {
            "meta": {
                "href": null,
                "mediaType": "application/vnd.sh-v1.0+json"
            },
            "id": 5533,
            "autopilotContactId": "person_564BB54C-672D-4ECE-BA4D-128D86BA9819",
            "firstName": "Tunji",
            "lastName": "Ali",
            "birthDate": "1977-02-03 00:00:00.0",
            "gender": "",
            "email": "TunjiAli@strollhealth.com",
            "zip": "94109",
            "paySpecDTO": {
                "pi": "-1",
                "payerName": "Self",
                "mi": ""
            },
            "miInvalid": false,
            "rejectReason": null,
            "phoneNumber": "(000) 000-0000",
            "phoneNumberType": "Cell",
            "agreedToTerms": true,
            "termVersion": "1.0",
            "linkId": "a11596f2-4b65-4be0-9e5a-e8643d320ae3",
            "middleInitital": null
        }
    },
    "patientId": 5533,
    "userId": 1,
    "practiceId": 0,
    "patientLastName": "Ali",
    "patientFirstName": "Tunji",
    "patientEmail": "TunjiAli@strollhealth.com",
    "patientPhoneNumber": "(000) 000-0000",
    "referringPhysicianName": "James Smith, MD",
    "referringPhysicianId": -1,
    "currentFacilityId": -1,
    "currentFacilityName": null,
    "cptCode": "73564",
    "facilityFaxRequestType": 1,
    "patientFaxRequestType": 0,
    "physicianFaxRequestType": 1,
    "productionPatientPortal": null,
    "sendFaxToFacility": true,
    "sendFaxToPatient": false,
    "sendFaxToPhysician": true,
    "patientFaxStatus": "PENDING",
    "physicianFaxStatus": "PENDING",
    "facilityFaxStatus": "PENDING",
    "lastUpdateDate": 1499452540131,
    "createDate": 1499452540131,
    "createDateAsString": "07-07-2017",
    "faxDTO": {
        "meta": {
            "href": null,
            "mediaType": "application/vnd.sh-v1.0+json"
        },
        "male_checkbox": false,
        "female_checkbox": true,
        "cell_checkbox": true,
        "office_checkbox": false,
        "home_checkbox": false,
        "physician_portal_checkbox": false,
        "fax_written_report_checkbox": true,
        "fax_STAT_checkbox": false,
        "phone_STAT_checkbox": false,
        "phone_call_report_checkbox": false,
        "send_CD_checkbox": true,
        "send_patient_with_CD_checkbox": true,
        "send_films_checkbox": true,
        "send_patient_with_films_checkbox": true,
        "courier_films_checkbox": false,
        "eligibility_validated_checkbox": false,
        "cash_alert": "Cash Pay",
        "mammogram": null,
        "referring_physician_NPI": "123456",
        "referring_physician_name": "James Smith, MD",
        "plan": null,
        "insurance_carrier": "Self",
        "estimate_out_of_pocket_cost": "$130.00",
        "cpt_code": "73564",
        "dob": "1977-02-03",
        "facility_fax": "(844) 787-6555",
        "referring_physician_fax": "(844) 787-6555",
        "prior_auth_number": "",
        "good_until_date": "",
        "service_type": null,
        "in_network_copay": "",
        "in_network_coinsurance": "",
        "in_network_single_maximum_total": "",
        "in_network_single_maximum_remaining": "",
        "in_network_single_deductible_total": "",
        "in_network_single_deductible_remaining": "",
        "in_network_family_maximum_total": "",
        "in_network_family_maximum_remaining": "",
        "in_network_family_deductible_total": "",
        "in_network_family_deductible_remaining": "",
        "out_network_copay": "",
        "out_network_coinsurance": "",
        "out_network_single_maximum_remaining": "",
        "out_network_single_deductible_remaining": "",
        "out_network_single_deductible_total": "",
        "out_network_single_maximum_total": "",
        "out_network_family_maximum_total": "",
        "out_network_family_maximum_remaining": "",
        "out_network_family_deductible_total": "",
        "out_network_family_deductible_remaining": "",
        "referring_physician_phone": "(320) 583-3421",
        "referring_physician_address": "Shattuck Ave 2150 Berkeley, CA",
        "physician_portal_url": "",
        "courier_films_to_name": "",
        "courier_films_to_address": "",
        "procedure_short_description": "X-Ray Knee, Complete",
        "icd10_code": "Y9333",
        "comparison_study_checkbox": false,
        "clinical_indication": "Activity, BASE jumping",
        "special_instructions": "bilateral procedure; ",
        "medication_provided_checkbox": false,
        "medication_provided_description": "",
        "procedure_locations": "",
        "previous_MRIMRA_checkbox": false,
        "symptom_onset_date": "",
        "claustrophobic_checkbox": false,
        "pacemaker_checkbox": false,
        "pacemaker_description": "",
        "other_implanted_metal_checkbox": false,
        "other_implanted_metal_description": "",
        "iv_contrast_allergy_checkbox": false,
        "creatinine": "",
        "iv_contrast_allergy_description": "",
        "oral_contrast_allergy_checkbox": false,
        "oral_contrast_allergy_description": "",
        "renal_disease_checkbox": false,
        "diabetes_checkbox": false,
        "other_allergies_checkbox": false,
        "other_allergies_description": "",
        "previous_MRIMRA_date": "",
        "creatinine_date": "",
        "taking_metformin_checkbox": false,
        "referral_date": "2017-07-07",
        "referring_physician_signature": "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",
        "facility_name": "Inview Imaging Lafayette",
        "facility_address_1": "970 Dewing Ave",
        "facility_address_2": "Suite 100",
        "facility_address_3": "Lafayette, CA 94549",
        "facility_phone": "(770) -",
        "referral_ID": null,
        "patient_name": "Tunji Ali",
        "pregnant_checkbox": false,
        "patient_phone_number": "(000) 000-0000",
        "primary_language": "",
        "member_ID": "",
        "verified_eligibility_date": "",
        "received_prior_auth_checkbox": false
    },
    "costsDTO": {
        "meta": {
            "href": null,
            "mediaType": "application/vnd.sh-v1.0+json"
        },
        "costDTOs": [],
        "insuranceDTO": {
            "patientId": null,
            "serviceType": null,
            "deductDate": null,
            "plan": null,
            "payerId": null,
            "payer": null,
            "inIndividDeductTotal": 0,
            "outIndividDeductTotal": 0,
            "inIndividDeductRemain": 0,
            "outIndividDeductRemain": 0,
            "inFamilyDeductTotal": 0,
            "outFamilyDeductTotal": 0,
            "inFamilyDeductRemain": 0,
            "outFamilyDeductRemain": 0,
            "inIndividMaxTotal": 0,
            "outIndividMaxTotal": 0,
            "inIndividMaxRemain": 0,
            "outIndividMaxRemain": 0,
            "inFamilyMaxTotal": 0,
            "outFamilyMaxTotal": 0,
            "inFamilyMaxRemain": 0,
            "outFamilyMaxRemain": 0,
            "incopay": 0,
            "incopayOutpatient": 0,
            "outcopay": 0,
            "incoinsurance": 0,
            "outcoinsurance": 0,
            "tier1Deduct": 0,
            "tier1FamilyDeduct": 0,
            "tier1Remain": 0,
            "tier1FamilyRemain": 0,
            "tier1MaxDeduct": 0,
            "tier1FamilyMaxDeduct": 0,
            "tier1MaxRemain": 0,
            "tier1FamilyMaxRemain": 0,
            "tier1Copay": 0,
            "tier1Coinsurance": 0
        },
        "notes": null,
        "simpleOpeningsByFacIds": null
    },
    "rfaPhysicianFaxRequestType": "0",
    "pr2PhysicianFaxRequestType": "0",
    "pr2FaxDTO": null,
    "rfaFaxDTO": null,
    "imageDTO": null,
    "partner": null,
    "chosenFacilityId": null,
    "appointmentStart": null,
    "appointmentEnd": null,
    "cancelReasons": null,
    "cancelNotes": null,
    "sendFaxToClaimsAdministrator": false,
    "sendFaxToClaimsAdministratorCompany": false
}
```

### HTTP Request

`POST https://provider-qa.strollhealth.com/api/addFaxRequest`

### Parameters

Parameter | Type | Description
--------- | ------- | -----------
faxRequestDTO | Object | A data transfer object that holds all the parameters

#### faxRequestDTO

faxRequestDTO Parameter | Type | Description
--------- | ------- | -----------
appointment | Object | A data transfer object containing appointment information
chosenFacilityId | Number | The Id that corresponds to an imaging facility.
costDTO | Object | A data transfer object containing cost information
cptCode | String | The CPT code that corresponds to the selected procedure.
createDateAsString | String | The current date formatted YYYY-MM-DD.
currentFacilityId | Number | The Id that corresponds with
facilityFaxRequestType | Number | 0 = FaxToPatient, 1 = FaxToPhysician, 2 = FaxToFacility, 3 = FaxToClaimAdministratorCompany, 4 = FaxToClaimAdministrator, 5 = FaxToSpecialist
faxDTO | Object | A data transfer object containing fax information
patientEmail | String | The patient's emails.
patientFaxRequestType | Number |
patientFirstName | String | The patient's first name.
patientId | Number | the Id that corresponds to the patient
patientLastName | String | The patient's last name.
patientPhoneNumber | String | The patient's phone number
physicianFaxRequestType | Number |
practiceId | Number | Id corresponding to the practice.
referringPhysicianId | Number | Id corresponding to the referring physician
referringPhysicianName | String | The name of the referring physician.
sendFaxToFacility | Boolean | Indicates if the fax is sent to the facility.
sendFaxToPatient | Boolean | Indicates if the fax is sent to the patient.
sendFaxToPhysician | Boolean | Indicates if the fax is sent to the physician.
userId | Number | Id corresponding to the user

#### appointment DTO

appointment Parameter | Type | Description
--------- | ------- | -----------

#### costDTO

costDTO Parameter | Type | Description
--------- | ------- | -----------

#### faxDTO

faxDTO Parameter | Type | Description
--------- | ------- | -----------
ICD9_code | String |
ICD10_code | String |
cash_alert | String | Indicates if the patient is paying with cash
cell_checkbox | Boolean |
claustrophobic_checkbox | Boolean |
clinical_indication | String |
comparison_study_checkbox | Boolean |
courier_films_checkbox | Boolean |
courier_films_to_address | String |
courier_films_to_name | String |
cpt_code | String |
creatinine | String |
creatinine_date | String |
diabetes_checkbox | Boolean |
dob | String |
estimate_out_of_pocket_cost | String |
facility_address_1 | String |
facility_address_2 | String |
facility_address_3 | String |
facility_fax | String |
facility_name | String |
facility_phone | String |
fax_STAT_checkbox | Boolean |
fax_written_report_checkbox | Boolean |
female_checkbox | Boolean |
home_checkbox | Boolean |
icd9_code | String |
icd10_code | String |
insurance_carrier | String |
iv_contrast_allergy_checkbox | Boolean |
iv_contrast_allergy_description | String |
male_checkbox | Boolean |
medication_provided_checkbox | Boolean |
medication_provided_description | String |
member_ID | String |
office_checkbox | Boolean |
oral_contrast_allergy_checkbox | Boolean |
oral_contrast_allergy_description | String |
other_allergies_checkbox | Boolean |
other_allergies_description | String |
other_implanted_metal_checkbox | Boolean |
other_implanted_metal_description | String |
pacemaker_checkbox | Boolean |
pacemaker_description | String |
patientEmail | String |
patientFirstName | String |
patientLastName | String |
patient_name | String |
patient_phone_number | String |
phone_STAT_checkbox | Boolean |
phone_call_report_checkbox | Boolean |
physician_portal_checkbox | Boolean |
physician_portal_url | String |
practiceId | Number |
pregnant_checkbox | Boolean |
previous_MRIMRA_checkbox | Boolean |
previous_MRIMRA_date | String |
primary_language | String |
prior_auth_number | String |
procedure_locations | String |
procedure_short_description | String |
received_prior_auth_checkbox | Boolean |
referral_date | String |
referring_physician_NPI | String |
referring_physician_fax | String |
referring_physician_name | String |
referring_physician_phone | String |
referring_physician_signature | String |
renal_disease_checkbox | Boolean |
send_CD_checkbox | Boolean |
send_films_checkbox | Boolean |
send_patient_with_CD_checkbox | Boolean |
send_patient_with_films_checkbox | Boolean |
special_instructions | String |
symptom_onset_date | String |
taking_metformin_checkbox | Boolean |
userId | Number |

# Appointment Microservice

## Get Openings

```shell
curl --inlcude \
     --header "Authorization: Bearer meowmeowmeow" \
     'http://patient-dev.strollhealth.com/api/getOpenings'
```

> The above command returns JSON structured like this:

```json
```

This endpoint retrieves tenants corresponding to an email.


### HTTP Request

`POST http://patient-dev.strollhealth.com/api/getOpenings`

### Parameters

Parameter | Type | Description
--------- | ------- | -----------
email | String | An user email

# User Microservice

## Get Current User

```shell
curl --include \
     --header "Authorization: Bearer meowmeowmeow" \
  'http://localhost:9008/user/current'
```

> The above command returns JSON structured like this:

```json
{
  "meta": {
    "href": null
  },
  "userId": 24,
  "tenantUUID": null,
  "firstName": "James",
  "lastName": "Smith",
  "email": "JamesSmith@strollhealth.com",
  "roles": [
    "Physician"
  ],
  "facilities": [
    {
      "meta": {
        "href": null
      },
      "site": {
        "id": 3,
        "tenantUUID": "sh",
        "name": "some_facility",
        "type": "Facility",
        "address": {
          "streetNumber": "551",
          "streetPreDir": null,
          "streetName": "Casey Drive",
          "streetType": null,
          "streetPostDir": null,
          "city": "Berkeley",
          "state": null,
          "zip": "94032",
          "zip4": null,
          "county": "",
          "country": "US",
          "lat": 123,
          "lng": 456
        },
        "fax": null,
        "phone": null,
        "lastUpdateDate": 1436552466000,
        "createDate": 1430720466000,
        "new": false
      }
    }
  ],
  "practices": [
    {
      "meta": {
        "href": null
      },
      "site": {
        "id": 4,
        "tenantUUID": "sh",
        "name": "some_practice",
        "type": "Practice",
        "address": {
          "streetNumber": "551",
          "streetPreDir": null,
          "streetName": "Casey Drive",
          "streetType": null,
          "streetPostDir": null,
          "city": "Berkeley",
          "state": null,
          "zip": "94932",
          "zip4": null,
          "county": null,
          "country": "US",
          "lat": 123,
          "lng": 456
        },
        "fax": null,
        "phone": null,
        "lastUpdateDate": 1438577683000,
        "createDate": 1430720641000,
        "new": false
      }
    }
  ],
  "profile": {
    "meta": {
      "href": null
    },
    "hasSignuature": false,
    "npi": "N/A"
  }
}
```

### HTTP Request

`POST http://provider.strollhealth/api/addFaxRequest`

<aside class="success">
Remember — a happy user is an authenticated user!
</aside>

## Get Current User's Sites

```shell
curl --include \
     --header "Authorization: Bearer meowmeowmeow" \
  'http://localhost:9008/user/sites'
```

> The above command returns JSON structured like this:

```json
{
  "meta": {
    "href": null
  },
  "facilities": [
    {
      "meta": {
        "href": null
      },
      "site": {
        "id": 3,
        "tenantUUID": "sh",
        "name": "some_facility",
        "type": "Facility",
        "address": {
          "streetNumber": "551",
          "streetPreDir": null,
          "streetName": "Casey Drive",
          "streetType": null,
          "streetPostDir": null,
          "city": "Berkeley",
          "state": null,
          "zip": "94032",
          "zip4": null,
          "county": "",
          "country": "US",
          "lat": 123,
          "lng": 456
        },
        "fax": null,
        "phone": null,
        "lastUpdateDate": 1436552466000,
        "createDate": 1430720466000,
        "new": false
      },
      "users": [
        {
          "meta": {
            "href": null
          },
          "userId": 24,
          "tenantUUID": null,
          "firstName": "James",
          "lastName": "Smith",
          "email": "JamesSmith@strollhealth.com",
          "roles": [
            "Physician"
          ],
          "facilities": [
            {
              "meta": {
                "href": null
              },
              "site": {
                "id": 3,
                "tenantUUID": "sh",
                "name": "some_facility",
                "type": "Facility",
                "address": {
                  "streetNumber": "551",
                  "streetPreDir": null,
                  "streetName": "Casey Drive",
                  "streetType": null,
                  "streetPostDir": null,
                  "city": "Berkeley",
                  "state": null,
                  "zip": "94032",
                  "zip4": null,
                  "county": "",
                  "country": "US",
                  "lat": 123,
                  "lng": 456
                },
                "fax": null,
                "phone": null,
                "lastUpdateDate": 1436552466000,
                "createDate": 1430720466000,
                "new": false
              }
            }
          ],
          "practices": [
            {
              "meta": {
                "href": null
              },
              "site": {
                "id": 4,
                "tenantUUID": "sh",
                "name": "some_practice",
                "type": "Practice",
                "address": {
                  "streetNumber": "551",
                  "streetPreDir": null,
                  "streetName": "Casey Drive",
                  "streetType": null,
                  "streetPostDir": null,
                  "city": "Berkeley",
                  "state": null,
                  "zip": "94932",
                  "zip4": null,
                  "county": null,
                  "country": "US",
                  "lat": 123,
                  "lng": 456
                },
                "fax": null,
                "phone": null,
                "lastUpdateDate": 1438577683000,
                "createDate": 1430720641000,
                "new": false
              }
            }
          ],
          "profile": {
            "meta": {
              "href": null
            },
            "hasSignuature": false,
            "npi": "N/A"
          }
        }
      ]
    }
  ],
  "practices": [
    {
      "meta": {
        "href": null
      },
      "site": {
        "id": 4,
        "tenantUUID": "sh",
        "name": "some_practice",
        "type": "Practice",
        "address": {
          "streetNumber": "551",
          "streetPreDir": null,
          "streetName": "Casey Drive",
          "streetType": null,
          "streetPostDir": null,
          "city": "Berkeley",
          "state": null,
          "zip": "94932",
          "zip4": null,
          "county": null,
          "country": "US",
          "lat": 123,
          "lng": 456
        },
        "fax": null,
        "phone": null,
        "lastUpdateDate": 1438577683000,
        "createDate": 1430720641000,
        "new": false
      },
      "users": [
        {
          "meta": {
            "href": null
          },
          "userId": 24,
          "tenantUUID": null,
          "firstName": "James",
          "lastName": "Smith",
          "email": "JamesSmith@strollhealth.com",
          "roles": [
            "Physician"
          ],
          "facilities": [
            {
              "meta": {
                "href": null
              },
              "site": {
                "id": 3,
                "tenantUUID": "sh",
                "name": "some_facility",
                "type": "Facility",
                "address": {
                  "streetNumber": "551",
                  "streetPreDir": null,
                  "streetName": "Casey Drive",
                  "streetType": null,
                  "streetPostDir": null,
                  "city": "Berkeley",
                  "state": null,
                  "zip": "94032",
                  "zip4": null,
                  "county": "",
                  "country": "US",
                  "lat": 123,
                  "lng": 456
                },
                "fax": null,
                "phone": null,
                "lastUpdateDate": 1436552466000,
                "createDate": 1430720466000,
                "new": false
              }
            }
          ],
          "practices": [
            {
              "meta": {
                "href": null
              },
              "site": {
                "id": 4,
                "tenantUUID": "sh",
                "name": "some_practice",
                "type": "Practice",
                "address": {
                  "streetNumber": "551",
                  "streetPreDir": null,
                  "streetName": "Casey Drive",
                  "streetType": null,
                  "streetPostDir": null,
                  "city": "Berkeley",
                  "state": null,
                  "zip": "94932",
                  "zip4": null,
                  "county": null,
                  "country": "US",
                  "lat": 123,
                  "lng": 456
                },
                "fax": null,
                "phone": null,
                "lastUpdateDate": 1438577683000,
                "createDate": 1430720641000,
                "new": false
              }
            }
          ],
          "profile": {
            "meta": {
              "href": null
            },
            "hasSignuature": false,
            "npi": "N/A"
          }
        }
      ]
    }
  ]
}
```

This endpoint retrieves all sites belonging to the current user.

<aside class="warning">Inside HTML code blocks like this one, you can't use Markdown, so use <code>&lt;code&gt;</code> blocks to denote code.</aside>

### HTTP Request

`GET http://localhost:9008/user/sites`

## Get Tenants by Email

```shell
curl --include \
     --header "Authorization: Bearer meowmeowmeow" \
  'http://localhost:9008/user/tenants?email=jamessmith@strollhealth.com'
```

> The above command returns JSON structured like this:

```json
[
  "sh"
]
```

This endpoint retrieves tenants corresponding to an email.


### HTTP Request

`GET http://localhost:9008/user/tenants?email={some_email}`

### Parameters

Parameter | Type | Description
--------- | ------- | -----------
email | String | An user email


## Get User's Signature

```shell
curl --include \
     --header "Authorization: Bearer meowmeowmeow" \
  'http://localhost:9008/user/24/profile/signature'
```

> The above command returns JSON structured like this:

```json
{
  "encodedSignature": "/9j/4AAQSkZJRgABAQEASABIAAD/4QBYRXhpZgAATU0AKgAAAAgAAgESAAMAAAAB\r\nAAEAAIdpAAQAAAABAAAAJgAAAAAAA6ABAAMAAAABAAEAAKACAAQAAAABAAADp6AD\r\nAAQAAAABAAABLAAAAAD/7QA4UGhvdG9zaG9wIDMuMAA4QklNBAQAAAAAAAA4QklN\r\nBCUAAAAAABDUHYzZjwCyBOmACZjs+EJ+/8AAEQgBLAOnAwEiAAIRAQMRAf/EAB8A\r\nAAEFAQEBAQEBAAAAAAAAAAABAgMEBQYHCAkKC//EALUQAAIBAwMCBAMFBQQ//Z......",
  "width": 0,
  "length": 0
}
```

This endpoint retrieves the an user's signature.


### HTTP Request

`GET http://localhost:9008/user/{userId}/profile/signature`

### Parameters

Parameter | Type | Description
--------- | ------- | -----------
userId | String | A user id for which you want to retrieve the signature


## Get Facility's Users

```shell
curl --include \
     --header "Authorization: Bearer meowmeowmeow" \
  'http://localhost:9008/user/facility/some_facility/users'
```


> The above command returns JSON structured like this:

```json
{
  "meta": {
    "href": null
  },
  "count": 1,
  "items": [
    {
      "meta": {
        "href": null
      },
      "userId": 24,
      "tenantUUID": null,
      "firstName": "James",
      "lastName": "Smith",
      "email": "jamessmith@strollhealth.com",
      "roles": [
        "Physician"
      ],
      "facilities": [
        {
          "meta": {
            "href": null
          },
          "site": {
            "id": 3,
            "tenantUUID": "sh",
            "name": "some_facility",
            "type": "Facility",
            "address": {
              "streetNumber": "551",
              "streetPreDir": null,
              "streetName": "Casey Drive",
              "streetType": null,
              "streetPostDir": null,
              "city": "Berkeley",
              "state": null,
              "zip": "94032",
              "zip4": null,
              "county": "",
              "country": "US",
              "lat": 123,
              "lng": 456
            },
            "fax": null,
            "phone": null,
            "lastUpdateDate": 1436552466000,
            "createDate": 1430720466000,
            "new": false
          }
        }
      ],
      "practices": [
        {
          "meta": {
            "href": null
          },
          "site": {
            "id": 4,
            "tenantUUID": "sh",
            "name": "some_practice",
            "type": "Practice",
            "address": {
              "streetNumber": "551",
              "streetPreDir": null,
              "streetName": "Casey Drive",
              "streetType": null,
              "streetPostDir": null,
              "city": "Berkeley",
              "state": null,
              "zip": "94932",
              "zip4": null,
              "county": null,
              "country": "US",
              "lat": 123,
              "lng": 456
            },
            "fax": null,
            "phone": null,
            "lastUpdateDate": 1438577683000,
            "createDate": 1430720641000,
            "new": false
          }
        }
      ],
      "profile": {
        "meta": {
          "href": null
        },
        "hasSignuature": true,
        "npi": "1659400984"
      }
    }
  ]
}
```

This endpoint retrieves all users corresponding to a facility.


### HTTP Request

`GET http://localhost:9008/user/facility/{facility_name}/users`

### Parameters

Parameter | Type | Description
--------- | ------- | -----------
facility_name | String | Name of the facility for which you wish to retrieve users


## Update User's Signature

```shell
curl --include \
     --header "Authorization: Bearer meowmeowmeow" \
  'http://localhost:9008/user/tenants?email=jamessmith@strollhealth.com'
```

> The above command returns JSON structured like this:

```json
[
  "sh"
]
```

This endpoint retrieves tenants corresponding to an email.


### HTTP Request

`GET http://localhost:9008/user/tenants?email={some_email}`

### Parameters

Parameter | Type | Description
--------- | ------- | -----------
email | String | An user email
