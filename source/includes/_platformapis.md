# Platform APIs

## getFaxRequest

```shell
curl 'https://provider-dev.strollhealth.com/api/faxrequests'
-H 'origin: https://provider-dev.strollhealth.com'
-H 'accept-encoding: gzip, deflate, br'
-H 'x-requested-with: XMLHttpRequest'
-H 'accept-language: en-US,en;q=0.8'
-H 'authorization: Bearer AUTH_TOKEN'
-H 'accept: application/json, text/plain, */*'
-H 'referer: https://provider-dev.strollhealth.com/radiology_orders/overview'
-H 'authority: provider-dev.strollhealth.com'
--data-binary '{"startDate":"04-07-2017","endDate":"08-07-2017",
"facilityIds":[456,454],"limit":40,"page":0,"userId":2}'
--compressed

```

>Example Response:

```json
{
  "meta": {
    "href": null,
    "mediaType": "application/vnd.sh-v1.0+json"
  },
  "count": 2,
  "items": [
    {
      "meta": {
        "href": "http://localhost:9090/sh/pendingFaxRequests/3530",
        "mediaType": "application/vnd.sh-v1.0+json"
      },
      "id": 3530,
      "faxRequestId": 3530,
      "appointment": {
        "meta": {
          "href": null,
          "mediaType": "application/vnd.sh-v1.0+json"
        },
        "appointmentId": 2776,
        "equipmentId": 0,
        "patientId": 7444,
        "facilityId": 456,
        "faxRequestId": 3530,
        "startTime": 28800000,
        "endTime": 28800000,
        "cptCode": "76604",
        "cost": 160,
        "reasonNotYetScheduled": "N/A",
        "stillWantToSchedule": true,
        "orderStatus": "PENDING_AUTH",
        "patientDTO": {
          "meta": {
            "href": null,
            "mediaType": "application/vnd.sh-v1.0+json"
          },
          "id": 7444,
          "autopilotContactId": "person_A893B7DC-8D10-4046-B6FD-21884B130C7C",
          "firstName": "And",
          "lastName": "Rew",
          "birthDate": "1996-02-15 00:00:00.0",
          "gender": "M",
          "email": "mvb97097@tqosi.com",
          "zip": "94704",
          "paySpecDTO": {
            "pi": "-1",
            "payerName": "Self",
            "mi": ""
          },
          "miInvalid": false,
          "rejectReason": null,
          "phoneNumber": "(324) 324-2342",
          "phoneNumberType": "Cell",
          "agreedToTerms": true,
          "termVersion": "1.0",
          "linkId": "08061565-e04a-4e38-bd91-4ea0e8d5c271",
          "middleInitital": null
        }
      },
      "patientId": 7444,
      "userId": -1,
      "practiceId": 0,
      "patientLastName": "Rew",
      "patientFirstName": "And",
      "patientEmail": "mvb97097@tqosi.com",
      "patientPhoneNumber": "(324) 324-2342",
      "referringPhysicianName": " ",
      "referringPhysicianId": -1,
      "currentFacilityId": -1,
      "currentFacilityName": null,
      "cptCode": "76604",
      "facilityFaxRequestType": 1,
      "patientFaxRequestType": 0,
      "physicianFaxRequestType": 0,
      "productionPatientPortal": null,
      "sendFaxToFacility": true,
      "sendFaxToPatient": false,
      "sendFaxToPhysician": false,
      "patientFaxStatus": "DELIVERED",
      "physicianFaxStatus": "PENDING",
      "facilityFaxStatus": "DELIVERED",
      "lastUpdateDate": 1498845271000,
      "createDate": 1498845271000,
      "createDateAsString": "06-30-2017",
      "faxDTO": {
        "meta": {
          "href": null,
          "mediaType": "application/vnd.sh-v1.0+json"
        },
        "male_checkbox": true,
        "female_checkbox": false,
        "cell_checkbox": true,
        "office_checkbox": false,
        "home_checkbox": false,
        "physician_portal_checkbox": false,
        "fax_written_report_checkbox": true,
        "fax_STAT_checkbox": false,
        "phone_STAT_checkbox": false,
        "phone_call_report_checkbox": true,
        "send_CD_checkbox": false,
        "send_patient_with_CD_checkbox": false,
        "send_films_checkbox": false,
        "send_patient_with_films_checkbox": false,
        "courier_films_checkbox": false,
        "eligibility_validated_checkbox": false,
        "cash_alert": "Cash Pay",
        "mammogram": null,
        "dob": "1996-02-15",
        "plan": null,
        "referring_physician_NPI": " ",
        "referring_physician_name": " ",
        "insurance_carrier": "Self",
        "estimate_out_of_pocket_cost": "$160.00",
        "cpt_code": "76604",
        "member_ID": "",
        "facility_fax": "(844) 787-6555",
        "referring_physician_fax": "(844) 787-6555",
        "facility_name": "Norcal Imaging Oakland",
        "facility_address_1": "3200 Telegraph Avenue",
        "facility_address_2": "Oakland",
        "facility_address_3": "CA 94609",
        "facility_phone": "(312) 3-",
        "referral_ID": null,
        "patient_name": "And Rew",
        "pregnant_checkbox": false,
        "patient_phone_number": "(324) 324-2342",
        "primary_language": "",
        "verified_eligibility_date": "",
        "received_prior_auth_checkbox": false,
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
        "referring_physician_phone": " ",
        "referring_physician_address": "2150 Shattuck Ave PH, Berkeley, CA 94704",
        "physician_portal_url": "",
        "courier_films_to_name": "",
        "courier_films_to_address": "",
        "procedure_short_description": "Ultrasound Chest",
        "icd10_code": "",
        "comparison_study_checkbox": false,
        "clinical_indication": "patient will bring doctor's referral",
        "special_instructions": "",
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
        "referral_date": "2017-06-30",
        "referring_physician_signature": "no signature"
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
    },
    ...More...
  ],
  "dayTotalCount": 2,
  "dayTotals": [
    {
      "meta": {
        "href": null,
        "mediaType": "application/vnd.sh-v1.0+json"
      },
      "date": "06-22-2017",
      "total": 1
    },
    ...More...
  ]
}
```

Returns fax request and order information for completed order within the time range specified by startTime and endTime, for a radiologist and associated facilities.

### HTTP Request
`POST https://provider.strollhealth.com/api/faxrequest`

### Parameters
Parameter | Type | Description
--------- | ------- | -----------
startDate | String | Date to start viewing fax requests from, in format MM-DD-YYYY
endDate | String | Date to end viewing fax requests from, in format MM-DD-YYYY
facilityIds | Number array| IDs corresponding to the user's associated facilities.
limit | Number | Maximum number of fax requests to return.
page | Number | Which page of fax requests to view, if multiple
userId | Number | Unique ID corresponding to user.


## getFacilities
```shell
curl 'https://provider-qa.strollhealth.com/api/search'
-H 'origin: https://provider-qa.strollhealth.com'
-H 'accept-encoding: gzip, deflate, br'
-H 'x-requested-with: XMLHttpRequest'
-H 'accept-language: en-US,en;q=0.8'
-H 'authorization: Bearer AUTH_TOKEN'
-H 'content-type: application/json'
-H 'accept: application/json, text/javascript, */*; q=0.01'
-H 'referer: https://provider-qa.strollhealth.com/provider_dashboard/results'
-H 'authority: provider-qa.strollhealth.com'
--data-binary '{"patientId":5531,"userId":1,"cptCodeIds":73701,
"pricingException":"undefined","bilateral":1}'
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
            "code": "73701",
            "cost": "N/A",
            "facilityId": "10083",
            "patientId": "5531",
            "fromAddress": null,
            "facility": "PAMF - San Carlos Radiology Center",
            "address": "301 Industrial Rd, Level 1, San Carlos, CA 94070",
            "image": "https://provider-qa.strollhealth.com/sh/images/generic_facility_image.png",
            "distance": "24.8 mi",
            "phone": "548",
            "fax": "824",
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
        {
            "code": "73701",
            "cost": "450.00",
            "facilityId": "526",
            "patientId": "5531",
            "fromAddress": null,
            "facility": "Inview Imaging Fremont",
            "address": "39465 Paseo Padre Parkway, Suite 1000, Fremont, CA 94538",
            "image": "https://provider-qa.strollhealth.com/sh/images/526_Inview%20Imaging%20Center.png",
            "distance": "26.8 mi",
            "phone": "197",
            "fax": "198",
            "lat": 37.549896,
            "lng": -121.97604,
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
        ... more ...
    ],
    "insuranceDTO": null,
    "notes": "Calculated based on patient zip",
    "simpleOpeningsByFacIds": {
        "368": [
            {
                "meta": {
                    "href": null,
                    "mediaType": "application/vnd.sh-v1.0+json"
                },
                "startTime": 1499356800000,
                "endTime": 1499358000000,
                "facilityEquipmentId": 35,
                "facilityId": 0,
                "contrast": "WITHOUT"
            },
            {
                "meta": {
                    "href": null,
                    "mediaType": "application/vnd.sh-v1.0+json"
                },
                "startTime": 1499358000000,
                "endTime": 1499359200000,
                "facilityEquipmentId": 35,
                "facilityId": 0,
                "contrast": "WITHOUT"
            },
            ... more ...
        ]
    }
}
```

This endpoint retrieves facilities corresponding to a user and CPT code.

### HTTP Request
`POST https://provider-qa.strollhealth.com/api/search`
### Parameters

Parameter | Type | Description
--------- | ------- | -----------
patientId | Number | ID corresponding to the patient
userId | Number | ID corresponding to the provider
cptCodeIds | Number | CPT code for the procedure
pricingException | String | Pricing exception code.
bilateral | Number | 1 if the procedure is bilateral, 0 otherwise

## getClinicalIndicationSuggestion

```shell
curl 'https://provider-dev.strollhealth.com/api/getClinicalIndication'
-H 'origin: https://provider-dev.strollhealth.com'
-H 'accept-encoding: gzip, deflate, br'
-H 'x-requested-with: XMLHttpRequest'
-H 'accept-language: en-US,en;q=0.8'
-H 'authorization: Bearer AUTH_TOKEN'
-H 'content-type: application/json'
-H 'accept: application/json, text/javascript, */*; q=0.01'
-H 'referer: https://provider-dev.strollhealth.com/provider_dashboard/finalize_order'
-H 'authority: provider-dev.strollhealth.com'  
--data-binary '{"substring":"bas","limit":5}'
--compressed
```

This endpoint retrieves a list of clinical indications that contain the substring parameter.

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

## getRadiologyFacilities

```shell
curl 'https://provider-dev.strollhealth.com/api/radiology/prices'
-H 'origin: https://provider-dev.strollhealth.com'
-H 'accept-encoding: gzip, deflate, br'
-H 'x-requested-with: XMLHttpRequest'
-H 'accept-language: en-US,en;q=0.8'
-H 'authorization: Bearer AUTH_TOKEN'
-H 'content-type: application/json'
-H 'accept: application/json, text/javascript, */*; q=0.01'
-H 'referer: https://provider-dev.strollhealth.com/radiology_dashboard/results'
-H 'authority: provider-dev.strollhealth.com'
--data-binary '{"patientId":7461,"userId":2,"cptCodeIds":77012,
"pricingException":"undefined","bilateral":"undefined","facilityIds":[456,454]}'
--compressed
```

>Example Response:

```json
{
  "meta": {
    "href": "/prices",
    "mediaType": "application/vnd.sh-v1.0+json"
  },
  "costDTOs": [
    {
      "code": "77012",
      "cost": "N/A",
      "facilityId": "454",
      "patientId": "7461",
      "fromAddress": null,
      "facility": "Northern California Pet Imaging",
      "address": "3195 Folsom Boulevard, Sacramento, CA 95816",
      "image": "https://provider-dev.strollhealth.com/sh/images/454_Northern%20California%20Pet%20Imaging.png.jpg",
      "distance": "74.5 mi",
      "phone": "4864",
      "fax": "9167376203",
      "lat": 38.568726,
      "lng": -121.465225,
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
    {
      "code": "77012",
      "cost": "N/A",
      "facilityId": "456",
      "patientId": "7461",
      "fromAddress": null,
      "facility": "Norcal Imaging Oakland",
      "address": "3200 Telegraph Avenue, Oakland, CA 94609",
      "image": "https://provider-dev.strollhealth.com/sh/images/456_Norcal%20Imaging%20Oakland.png",
      "distance": "8.7 mi",
      "phone": "3123",
      "fax": "5106631951",
      "lat": 37.820885,
      "lng": -122.2664,
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
    }
  ],
  "insuranceDTO": null,
  "notes": null,
  "simpleOpeningsByFacIds": {}
}
```

This returns pricing and facility information for a radiologist's associated facilities, given procedure information , and radiologist userId and associated facilities' IDs.

### HTTP Request
`POST https://provider.strollhealth.com/api/radiology/prices`

### Parameters
Parameter | Type | Description
--------- | ------- | -----------
bilateral | Number | Indicates whether the procedure is bilateral. 1 if True, 0 if False.
cptCodeIds | Number | CPT Code identifying the type of procedure.
facilityIds | Number array | IDs corresponding to the user's associated facilities.
patientId | Number | Unique ID corresponding to patient.
pricingException | String | Pricing exception code.
userId | Number | Unique ID corresponding to user.

## getEquipment

```shell
curl 'https://provider-qa.strollhealth.com/api/getEquipment'
-H 'origin: https://provider-qa.strollhealth.com'
-H 'accept-encoding: gzip, deflate, br'
-H 'x-requested-with: XMLHttpRequest' -H 'accept-language: en-US,en;q=0.8'
-H 'authorization: Bearer AUTH_TOKEN'
-H 'content-type: application/json'
-H 'accept: application/json, text/javascript, */*; q=0.01'
-H 'referer: https://provider-qa.strollhealth.com/radiology_dashboard/schedule'
-H 'authority: provider-qa.strollhealth.com'
--data-binary '{"facilityId":10018}'
--compressed

```

>Example Response:

```json
{
  "meta": {
    "href": null,
    "mediaType": "application/vnd.sh-v1.0+json"
  },
  "facilityEquipmentDTOs": [
    {
      "meta": {
        "href": "/facility/equipment/28",
        "mediaType": "application/vnd.sh-v1.0+json"
      },
      "equipmentDTO": {
        "meta": {
          "href": null,
          "mediaType": "application/vnd.sh-v1.0+json"
        },
        "id": 28,
        "modality": "MRI",
        "manufacturer": "Siemens",
        "model": "S2000",
        "yearMade": 949454130000,
        "channels": 8,
        "magnetStrength": 2.4,
        "additionalInfo": "",
        "type": "Open",
        "tableWeight": 3500,
        "rotationTime": 0.2,
        "slices": 32,
        "name": "S2000"
      },
      "facilityEquipmentId": 28,
      "additionalInfo": "",
      "facilityId": 10018,
      "name": null
    },
    {
      "meta": {
        "href": "/facility/equipment/30",
        "mediaType": "application/vnd.sh-v1.0+json"
      },
      "equipmentDTO": {
        "meta": {
          "href": null,
          "mediaType": "application/vnd.sh-v1.0+json"
        },
        "id": 30,
        "modality": "CT",
        "manufacturer": "Siemens",
        "model": "S2010",
        "yearMade": 949454192000,
        "channels": 8,
        "magnetStrength": 2.4,
        "additionalInfo": "",
        "type": "Open",
        "tableWeight": 2100,
        "rotationTime": 0.2,
        "slices": 32,
        "name": "S2010"
      },
      "facilityEquipmentId": 30,
      "additionalInfo": "",
      "facilityId": 10018,
      "name": null
    },
    ...More...
  ],
  "facilityId": 10018
}
```

This endpoint retrieves comprehensive equipment information about a given facility. Returns a list of objects with information for each imaging equipment, including modality, manufacturer, model, etc.

### HTTP Request
`POST https://provider.strollhealth.com/api/getEquipment`

### Parameters
Parameter | Type | Description
--------- | ------- | -----------
facilityId | Number | ID of facility to find equipment information for

## getSimplePrices

```shell
curl 'http://localhost:9080/api/getSimplePrices'
-H 'Authorization: Basic bXktdHJ1c3RlZC1jbGllbnQxOg=='
-H 'Origin: http://localhost:9080'
-H 'Accept-Encoding: gzip, deflate, br'
-H 'Content-Type: application/json'
-H 'Accept: application/json, text/javascript, */*; q=0.01'
-H 'Referer: http://localhost:9080/results'
-H 'X-Requested-With: XMLHttpRequest'
--data-binary '{"cptCodeIds":"76604","userId":-1,"lat":37.866536,"lng":-122.257996,"zipCode":
"94704","payerId":1,"planId":"","bilateral":"","pricingException":"",
"quantity":null}'
--compressed
```

>Example Response:

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

Gets a list of Radiology facilities

### HTTP Request
`POST https://provider.strollhealth.com/api/getSimplePrices`
### Parameters

Parameter | Type | Description
--------- | ------- | -----------
Bilateral| Number | Indicates if the procedure is bilateral. 1 if true, 0 if false.
CPT Code Id | String | Identifies the type of procedure.
User Id | Number | Id for logged in users.
Lat | Number | User's Latitude position.
Lng | Number | User's Longitude position.
Zip Code | String | User's zip code.
Payer Id | Number | Unique Id corresponding to the payer.
Plan Id | String | Unique Id corresponding to the plan.
Pricing Exception | String | If needed with CPT code, this indicates what possible pricing exceptions are included.
Quantity | Number | Number of procedures.

## orderFax

```shell
curl 'https://provider-qa.strollhealth.com/api/addFaxRequest'
-H 'origin: https://provider-qa.strollhealth.com'
-H 'accept-encoding: gzip, deflate, br'
-H 'x-requested-with: XMLHttpRequest'
-H 'accept-language: en-US,en;q=0.8'
-H 'authorization: Bearer AUTH_TOKEN'
-H 'content-type: application/json'
-H 'accept: application/json, text/plain, */*'
-H 'referer: https://provider-qa.strollhealth.com/provider_dashboard/finalize_order'
-H 'authority: provider-qa.strollhealth.com'
--data-binary'{"sendFaxToFacility":true,"currentFacilityId":0,
"createDateAsString":"2017-07-07","chosenFacilityId":10018,
"patientEmail":"TunjiAli@strollhealth.com","cptCode":"73564",
"facilityFaxRequestType":1,"physicianFaxRequestType":1,"patientFaxRequestType":0,
"patientFirstName":"Tunji","referringPhysicianId":1,"patientId":5533,
"patientLastName":"Ali","patientPhoneNumber":"(000) 000-0000",
"referringPhysicianName":"James Smith, MD","sendFaxToPatient":false,
"sendFaxToPhysician":true,"costsDTO":{},"userId":1,"practiceId":2,
"faxDTO":{"member_ID":"","insurance_carrier":"Self","dob":"1977-02-03",
"facility_name":"Inview Imaging Lafayette","facility_address_1":"970 Dewing Ave",
"facility_address_2":"Suite 100","facility_address_3":"Lafayette, CA 94549",
"facility_phone":"(770) -","facility_fax":"(844) 787-6555","patient_name":"Tunji Ali",
"male_checkbox":false,"female_checkbox":true,"pregnant_checkbox":false,
"patient_phone_number":"(000) 000-0000","cell_checkbox":true,"office_checkbox":false,"home_checkbox":false,
"primary_language":"","estimate_out_of_pocket_cost":"$130.00","referring_physician_NPI":"123456",
"referring_physician_phone":"(320) 583-3421","referring_physician_address":"Shattuck Ave 2150 Berkeley, CA",
"referring_physician_fax":"(844) 787-6555","physician_portal_checkbox":false,"physician_portal_url":"",
"fax_written_report_checkbox":true,"fax_STAT_checkbox":false,"phone_STAT_checkbox":false,
"phone_call_report_checkbox":false,"send_CD_checkbox":true,"send_patient_with_CD_checkbox":true,
"send_films_checkbox":true,"send_patient_with_films_checkbox":true,"courier_films_checkbox":false,
"courier_films_to_name":"","courier_films_to_address":"","procedure_short_description":"X-Ray Knee, Complete",
"cpt_code":"73564","ICD10_code":"Y9333","icd10_code":"Y9333","ICD9_code":"Y9333","icd9_code":"Y9333",
"clinical_indication":"Activity, BASE jumping","comparison_study_checkbox":false,"medication_provided_checkbox":false,
"medication_provided_description":"","procedure_locations":"","special_instructions":"bilateral procedure; ",
"previous_MRIMRA_checkbox":false,"symptom_onset_date":"","claustrophobic_checkbox":false,
"pacemaker_checkbox":false,"pacemaker_description":"","other_implanted_metal_checkbox":false,
"other_implanted_metal_description":"","iv_contrast_allergy_checkbox":false,
"iv_contrast_allergy_description":"","creatinine":"","oral_contrast_allergy_checkbox":false,
"oral_contrast_allergy_description":"","renal_disease_checkbox":false,"diabetes_checkbox":false,
"other_allergies_checkbox":false,"other_allergies_description":"","previous_MRIMRA_date":"",
"creatinine_date":"","taking_metformin_checkbox":false,"referring_physician_name":"James Smith, MD",
"referral_date":"2017-07-07","referring_physician_signature":"iVBORw0KGgoAAAANSUh...MORE...",
"patientLastName":"Ali","patientFirstName":"Tunji","patientEmail":"TunjiAli@strollhealth.com",
"userId":1,"practiceId":2,"cash_alert":"Cash Pay","prior_auth_number":"","received_prior_auth_checkbox":false},"appointment":{}}'
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
        "referring_physician_signature": "iVBORw0KGgoAAAANSUh...MORE...",
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

EXPLANATION

### HTTP Request

`POST https://provider-qa.strollhealth.com/api/addFaxRequest`

### Parameters

Parameter | Type | Description
--------- | ------- | -----------
faxRequestDTO | Object | A data transfer object that holds all the parameters


## getZipCoords

```shell
curl 'https://patient-dev.strollhealth.com/api/getZipCoords'
-H 'origin: https://patient-dev.strollhealth.com'
-H 'accept-encoding: gzip, deflate, br'
-H 'x-requested-with: XMLHttpRequest'
-H 'accept-language: en-US,en;q=0.8'
-H 'authorization: Basic bXktdHJ1c3RlZC1jbGllbnQxOg=='
-H 'content-type: application/json'
-H 'accept: application/json, text/javascript, */*; q=0.01'
-H 'referer: https://patient-dev.strollhealth.com/prescription_search'
-H 'authority: patient-dev.strollhealth.com'
--data-binary '{"zipCode":"94109"}' --compressed
```

>Example Response:

```json
{
  "id": 28425,
  "zip": "94109",
  "lat": 37.795388,
  "lng": -122.422453
}
```


This endpoint returns the geographical coordinates (latitude and longitude) for a given valid zip code.

### HTTP Request
`POST https://findcare.strollhealth.com/api/getZipCoords`

### Parameters
Parameter | Type | Description
--------- | ------- | -----------
zipCode | String | Zip code for desired coordinates

## getSpecialists

```shell
curl 'https://patient-dev.strollhealth.com/api/getSpecialists'
-H 'origin: https://patient-dev.strollhealth.com'
-H 'accept-encoding: gzip, deflate, br'
-H 'x-requested-with: XMLHttpRequest'
-H 'accept-language: en-US,en;q=0.8'
-H 'authorization: Basic bXktdHJ1c3RlZC1jbGllbnQxOg=='
-H 'content-type: application/json'
-H 'accept: application/json, text/javascript, */*; q=0.01'
-H 'referer: https://patient-dev.strollhealth.com/specialists'
-H 'authority: patient-dev.strollhealth.com'
--data-binary
'{"lat":41.409,"lng":-73.24263,"specialty":"cardiopulmonary-physical-therapist"
,"sort":"distance-asc"}'
--compressed
```

>Example Response:

```json
{
  "meta": {
    "data_type": "array",
    "item_type": "Doctor",
    "total": 1,
    "count": 1,
    "skip": 0,
    "limit": 20
  },
  "data": [
    {
      "practices": [
        {
          "location_slug": "ny-southold",
          "within_search_area": false,
          "distance": 61.80050150052108,
          "lat": 41.06765,
          "lon": -72.41696,
          "uid": "6fe99cc60d97bfe6836cf14245d9e8e3",
          "name": "Saundra Perry, PT",
          "accepts_new_patients": true,
          "insurance_uids": [
            "anthem-anthempathwayxindppodirectaccessct",
            "aetna-aetnachoiceposii",
            "cigna-cignaopenaccessplus",
            "cigna-cignahmo",
            "capitaldistrictphysicianshealthplan-cdphpppo",
            "anthem-anthemppocenturypreferredct",
            "empirebcbs-empirepathwayenhancedguidedaccess",
            "cigna-cignappo",
            "aetna-aetnamanagedchoiceposopenaccess",
            "multiplan-multiplanppo",
            ...More...
          ],
          "visit_address": {
            "city": "Southold",
            "lat": 41.06765,
            "lon": -72.41696,
            "state": "NY",
            "state_long": "New York",
            "street": "57190 Route 25",
            "zip": "11971"
          },
          "office_hours": [],
          "phones": [
            {
              "number": "6317653620",
              "type": "business_landline"
            },
            {
              "number": "6317650013",
              "type": "business_fax"
            },
            {
              "number": "6317653620",
              "type": "landline"
            },
            {
              "number": "6317650013",
              "type": "fax"
            }
          ],
          "languages": [
            {
              "name": "English",
              "code": "en"
            }
          ]
        }
      ],
      "educations": [],
      "profile": {
        "first_name": "Saundra",
        "middle_name": "J",
        "last_name": "Perry",
        "slug": "saundra-perry-pt",
        "title": "PT",
        "image_url": "https://asset2.betterdoctor.com/assets/general_doctor_female.png",
        "gender": "female",
        "languages": [
          {
            "name": "English",
            "code": "en"
          }
        ],
        "bio": "Dr. Saundra Perry, PT, specialist in physical therapy, chiropractic rehabilitation, and rehabilitation psychology, currently practices medicine at Southold, New York.\n\nDr. Perry is licensed to practice medicine at New York.\n\nDr. Perry has been found to hold one or more active medical licenses, and successfully passed a malpractice history screening."
      },
      "ratings": [],
      "insurances": [
        {
          "insurance_plan": {
            "uid": "anthem-anthempathwayxindppodirectaccessct",
            "name": "Anthem Pathway X Ind PPO Direct Access CT",
            "category": [
              "medical"
            ]
          },
          "insurance_provider": {
            "uid": "anthem",
            "name": "Anthem"
          }
        },
        {
          "insurance_plan": {
            "uid": "aetna-aetnachoiceposii",
            "name": "Aetna Choice POS II",
            "category": [
              "medical"
            ]
          },
          "insurance_provider": {
            "uid": "aetna",
            "name": "Aetna"
          }
        },
        ...More...
      ],
      "specialties": [
        {
          "uid": "physical-therapist",
          "name": "Physical Therapy",
          "description": "Specializes in physical therapy.",
          "category": "medical",
          "actor": "Physical Therapist",
          "actors": "Physical Therapists"
        },
        {
          "uid": "cardiopulmonary-physical-therapist",
          "name": "Cardiopulmonary Physical Therapy",
          "description": "Specializes in heart and lung related physical therapy.",
          "category": "medical",
          "actor": "Cardiopulmonary Physical Therapist",
          "actors": "Cardiopulmonary Physical Therapists"
        },
        ...More...
      ],
      "claims": [
        {
          "hcpcs": "97110",
          "hcpcs_description": "Therapeutic exercises",
          "service_cnt": 3228,
          "bene_uniq_cnt": 181,
          "avg_allowed_amt": 31.493878563,
          "avg_charge_amt": 37.860003098,
          "avg_payment_amt": 24.928649318
        },
        {
          "hcpcs": "97112",
          "hcpcs_description": "Neuromuscular reeducation",
          "service_cnt": 1878,
          "bene_uniq_cnt": 161,
          "avg_allowed_amt": 35.001794462,
          "avg_charge_amt": 39.681528222,
          "avg_payment_amt": 27.772539936
        },
        ...More...
      ],
      "licenses": [
        {
          "number": "06894",
          "state": "NY"
        }
      ],
      "uid": "9aec02c86a80d69ad7ce10d6bbf2280f",
      "npi": "1417906116"
    }
  ]
}
```

This endpoint is a wrapper for BetterDoctor's Doctor Search API, returning up to 20 profiles of doctors who match the given specialty and location in the request.

### HTTP Request
`POST https://findcare.strollhealth.com/api/getSpecialists`

### Parameters

Parameter | Type | Description
--------- | ------- | -----------
lat | Number | Search location latitude
lng | Number | Search location longitude
sort| String | Sort algorithm
specialty | String | Desired specialty

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

## getDrugInfo

```shell
curl 'https://patient-dev.strollhealth.com/api/getDrugInfo'
-H 'origin: https://patient-dev.strollhealth.com'
-H 'accept-encoding: gzip, deflate, br'
-H 'x-requested-with: XMLHttpRequest'
-H 'accept-language: en-US,en;q=0.8'
-H 'authorization: Basic bXktdHJ1c3RlZC1jbGllbnQxOg=='
-H 'content-type: application/json'
-H 'accept: application/json, text/javascript, */*; q=0.01'
-H 'referer: https://patient-dev.strollhealth.com/prescription_search'
-H 'authority: patient-dev.strollhealth.com'
--data-binary '{"name":"Accupril"}'
--compressed
```

> The above command returns JSON structured like this:

```json
{
    "errors": [],
    "data": {
        "drugs": {
            "tablet": {
                "5mg": "https://www.goodrx.com/accupril?grx_ref=api&strength=5mg&form=tablet&label=Accupril",
                "10mg": "https://www.goodrx.com/accupril?grx_ref=api&strength=10mg&form=tablet&label=Accupril",
                "20mg": "https://www.goodrx.com/accupril?grx_ref=api&strength=20mg&form=tablet&label=Accupril",
                "40mg": "https://www.goodrx.com/accupril?grx_ref=api&strength=40mg&form=tablet&label=Accupril"
            }
        },
        "quantities": {
            "tablet": {
                "5mg": [
                    30
                ],
                "10mg": [
                    30,
                    60,
                    90
                ],
                "20mg": [
                    15,
                    30,
                    60,
                    90,
                    180
                ],
                "40mg": [
                    30,
                    45,
                    60,
                    90,
                    180
                ]
            }
        }
    },
    "success": true
}
```

This serves as a wrapper for GoodRX API and returns quantities and dosages for a given drug.


### HTTP Request

`POST https://patient-dev.strollhealth.com/api/getDrugInfo`

Parameter | Type | Description
--------- | ------- | -----------
name | String | Name of the chosen drug


## fetchPlans

```shell
curl 'https://patient-dev.strollhealth.com/api/getPlans'
-H 'if-none-match: W/"14111-TElwmDr+z6BVi7FGFMo1JX+CXCo"'
-H 'accept-encoding: gzip, deflate, sdch, br'
-H 'x-requested-with: XMLHttpRequest'
-H 'accept-language: en-US,en;q=0.8'
-H 'authorization: Basic bXktdHJ1c3RlZC1jbGllbnQxOg=='
-H 'accept: application/json, text/javascript, */*; q=0.01'
-H 'referer: https://patient-dev.strollhealth.com/procedure_search'
-H 'authority: patient-dev.strollhealth.com'
-H 'contenttype: application/json'
--compressed
```

> The above command returns JSON structured like this:

```json
{
    "6": [
        {
            "meta": null,
            "id": 433,
            "plan": "CDHP",
            "payerId": 6,
            "planType": "PPO",
            "medicare": false
        }
    ],
    "50": [
        {
            "meta": null,
            "id": 186,
            "plan": "BRONZE FULL PPO HSA 3500",
            "payerId": 50,
            "planType": "PPO",
            "medicare": false
        },
        {
            "meta": null,
            "id": 187,
            "plan": "SILVER 73 EPO",
            "payerId": 50,
            "planType": "EPO",
            "medicare": false
        },
        {
            "meta": null,
            "id": 188,
            "plan": "ACCESS+ HMO SAVENET",
            "payerId": 50,
            "planType": "HMO",
            "medicare": false
        }
        ... more ...
    ]
    ... more ...
}
```

This endpoint gets all the insurance plans.
### HTTP Request
`GET https://patient-qa.strollhealth.com/api/getPlans`
