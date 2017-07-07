# Platform APIs

## getSimplePrices

>Example Request:

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

```shell
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
Results Request DTO| Object | A data transfer object holds all the parameters in a single object.


ResultsRequestDTO Parameter | Type | Description
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

## getZipCoords

>Example Request:

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

```shell
{
  "id": 28425,
  "zip": "94109",
  "lat": 37.795388,
  "lng": -122.422453
}
```


This endpoint returns the geographical coordinates (latitude and longitude) for a given valid zip code.

### HTTP Request
`POST /api/getZipCoords`

### Parameters
Parameter | Type | Description
--------- | ------- | -----------
zipCode | String | Zip code for desired coordinates

## getSpecialists

>Example Request:

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
,"sort":"distance-asc"}' --compressed
```

>Example Response:

```shell
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
            "bcbsbluecard-bcbsbluecardppo",
            "empirebcbs-empireprismepobluepriority",
            "aetna-aetnahmo",
            "harvardpilgrim-harvardpilgrimppo",
            "aetna-aetnaelectchoiceepo",
            "multiplan-phcsppo",
            "empirebcbs-empireppo",
            "magnacare-magnacareppo",
            "empirebcbs-empirehmo",
            "aetna-aetnasignatureadministratorsppo",
            "gwhcigna-greatwestppo",
            "unitedhealthcare-uhcchoicepluspos",
            "unitedhealthcare-uhcnavigatehmo",
            "unitedhealthcare-uhcnavigatepos",
            "unitedhealthcare-uhcoptionsppo",
            "mvphealthplan-mvppreferredppo"
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
        {
          "insurance_plan": {
            "uid": "cigna-cignaopenaccessplus",
            "name": "CIGNA Open Access Plus",
            "category": [
              "medical"
            ]
          },
          "insurance_provider": {
            "uid": "cigna",
            "name": "Cigna"
          }
        },
        {
          "insurance_plan": {
            "uid": "cigna-cignahmo",
            "name": "CIGNA HMO",
            "category": [
              "medical"
            ]
          },
          "insurance_provider": {
            "uid": "cigna",
            "name": "Cigna"
          }
        },
        {
          "insurance_plan": {
            "uid": "capitaldistrictphysicianshealthplan-cdphpppo",
            "name": "CDPHP PPO",
            "category": [
              "medical"
            ]
          },
          "insurance_provider": {
            "uid": "capitaldistrictphysicianshealthplan",
            "name": "Capital District Physicians Health Plan"
          }
        },
        {
          "insurance_plan": {
            "uid": "anthem-anthemppocenturypreferredct",
            "name": "Anthem PPO Century Preferred - CT",
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
            "uid": "empirebcbs-empirepathwayenhancedguidedaccess",
            "name": "Empire Pathway Enhanced Guided Access",
            "category": [
              "medical"
            ]
          },
          "insurance_provider": {
            "uid": "empirebcbs",
            "name": "Empire BCBS"
          }
        },
        {
          "insurance_plan": {
            "uid": "cigna-cignappo",
            "name": "CIGNA PPO",
            "category": [
              "medical"
            ]
          },
          "insurance_provider": {
            "uid": "cigna",
            "name": "Cigna"
          }
        },
        {
          "insurance_plan": {
            "uid": "aetna-aetnamanagedchoiceposopenaccess",
            "name": "Aetna Managed Choice POS Open Access",
            "category": [
              "medical"
            ]
          },
          "insurance_provider": {
            "uid": "aetna",
            "name": "Aetna"
          }
        },
        {
          "insurance_plan": {
            "uid": "multiplan-multiplanppo",
            "name": "Multiplan PPO",
            "category": [
              "medical"
            ]
          },
          "insurance_provider": {
            "uid": "multiplan",
            "name": "Multiplan"
          }
        },
        {
          "insurance_plan": {
            "uid": "bcbsbluecard-bcbsbluecardppo",
            "name": "BCBS Blue Card PPO",
            "category": [
              "medical"
            ]
          },
          "insurance_provider": {
            "uid": "bcbsbluecard",
            "name": "BCBS Blue Card"
          }
        },
        {
          "insurance_plan": {
            "uid": "empirebcbs-empireprismepobluepriority",
            "name": "Empire Prism EPO - Blue Priority",
            "category": [
              "medical"
            ]
          },
          "insurance_provider": {
            "uid": "empirebcbs",
            "name": "Empire BCBS"
          }
        },
        {
          "insurance_plan": {
            "uid": "aetna-aetnahmo",
            "name": "Aetna HMO",
            "category": [
              "medical"
            ]
          },
          "insurance_provider": {
            "uid": "aetna",
            "name": "Aetna"
          }
        },
        {
          "insurance_plan": {
            "uid": "harvardpilgrim-harvardpilgrimppo",
            "name": "Harvard Pilgrim PPO",
            "category": [
              "medical"
            ]
          },
          "insurance_provider": {
            "uid": "harvardpilgrim",
            "name": "Harvard Pilgrim"
          }
        },
        {
          "insurance_plan": {
            "uid": "aetna-aetnaelectchoiceepo",
            "name": "Aetna Elect Choice EPO",
            "category": [
              "medical"
            ]
          },
          "insurance_provider": {
            "uid": "aetna",
            "name": "Aetna"
          }
        },
        {
          "insurance_plan": {
            "uid": "multiplan-phcsppo",
            "name": "PHCS PPO",
            "category": [
              "medical"
            ]
          },
          "insurance_provider": {
            "uid": "multiplan",
            "name": "Multiplan"
          }
        },
        {
          "insurance_plan": {
            "uid": "empirebcbs-empireppo",
            "name": "Empire PPO",
            "category": [
              "medical"
            ]
          },
          "insurance_provider": {
            "uid": "empirebcbs",
            "name": "Empire BCBS"
          }
        },
        {
          "insurance_plan": {
            "uid": "magnacare-magnacareppo",
            "name": "MagnaCare PPO",
            "category": [
              "medical"
            ]
          },
          "insurance_provider": {
            "uid": "magnacare",
            "name": "MagnaCare"
          }
        },
        {
          "insurance_plan": {
            "uid": "empirebcbs-empirehmo",
            "name": "Empire HMO",
            "category": [
              "medical"
            ]
          },
          "insurance_provider": {
            "uid": "empirebcbs",
            "name": "Empire BCBS"
          }
        },
        {
          "insurance_plan": {
            "uid": "aetna-aetnasignatureadministratorsppo",
            "name": "Aetna Signature Administrators PPO",
            "category": [
              "medical"
            ]
          },
          "insurance_provider": {
            "uid": "aetna",
            "name": "Aetna"
          }
        },
        {
          "insurance_plan": {
            "uid": "gwhcigna-greatwestppo",
            "name": "Great West PPO",
            "category": [
              "medical"
            ]
          },
          "insurance_provider": {
            "uid": "gwhcigna",
            "name": "GWH-Cigna"
          }
        },
        {
          "insurance_plan": {
            "uid": "unitedhealthcare-uhcchoicepluspos",
            "name": "UHC Choice Plus POS",
            "category": [
              "medical"
            ]
          },
          "insurance_provider": {
            "uid": "unitedhealthcare",
            "name": "United Healthcare"
          }
        },
        {
          "insurance_plan": {
            "uid": "unitedhealthcare-uhcnavigatehmo",
            "name": "UHC Navigate HMO",
            "category": [
              "medical"
            ]
          },
          "insurance_provider": {
            "uid": "unitedhealthcare",
            "name": "United Healthcare"
          }
        },
        {
          "insurance_plan": {
            "uid": "unitedhealthcare-uhcnavigatepos",
            "name": "UHC Navigate POS",
            "category": [
              "medical"
            ]
          },
          "insurance_provider": {
            "uid": "unitedhealthcare",
            "name": "United Healthcare"
          }
        },
        {
          "insurance_plan": {
            "uid": "unitedhealthcare-uhcoptionsppo",
            "name": "UHC Options PPO",
            "category": [
              "medical"
            ]
          },
          "insurance_provider": {
            "uid": "unitedhealthcare",
            "name": "United Healthcare"
          }
        },
        {
          "insurance_plan": {
            "uid": "mvphealthplan-mvppreferredppo",
            "name": "MVP Preferred PPO",
            "category": [
              "medical"
            ]
          },
          "insurance_provider": {
            "uid": "mvphealthplan",
            "name": "MVP Health Plan"
          }
        }
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
        {
          "uid": "geriatric-physical-therapist",
          "name": "Geriatrics Physical Therapy",
          "description": "Specializes in physical therapy for the elderly.",
          "category": "medical",
          "actor": "Geriatric Physical Therapist",
          "actors": "Geriatric Physical Therapists"
        },
        {
          "uid": "neurology-physical-therapist",
          "name": "Neurology Physical Therapy",
          "description": "Specializes in nervous system physical therapy.",
          "category": "medical",
          "actor": "Neurology Physical Therapist",
          "actors": "Neurology Physical Therapists"
        },
        {
          "uid": "pediatric-physical-therapist",
          "name": "Pediatric Physical Therapy",
          "description": "Specializes in children's physical therapy.",
          "category": "medical",
          "actor": "Pediatrics Physical Therapist",
          "actors": "Pediatrics Physical Therapists"
        },
        {
          "uid": "orthopedic-physical-therapist",
          "name": "Orthopedic Physical Therapy",
          "description": "Specializes in physical therapy of joints and muscles.",
          "category": "medical",
          "actor": "Orthopedic Physical Therapist",
          "actors": "Orthopedic Physical Therapists"
        }
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
        {
          "hcpcs": "97140",
          "hcpcs_description": "Manual therapy",
          "service_cnt": 1738,
          "bene_uniq_cnt": 157,
          "avg_allowed_amt": 29.096403913,
          "avg_charge_amt": 35.276104718,
          "avg_payment_amt": 23.138365938
        },
        {
          "hcpcs": "G0283",
          "hcpcs_description": "Electrical stimulation (unattended), one or more areas, not wound care, as part of a therapy",
          "service_cnt": 723,
          "bene_uniq_cnt": 92,
          "avg_allowed_amt": 13.523969571,
          "avg_charge_amt": 16.551120332,
          "avg_payment_amt": 10.793236515
        },
        {
          "hcpcs": "97035",
          "hcpcs_description": "Ultrasound therapy",
          "service_cnt": 487,
          "bene_uniq_cnt": 68,
          "avg_allowed_amt": 12.61,
          "avg_charge_amt": 15.03,
          "avg_payment_amt": 10.048562628
        },
        {
          "hcpcs": "97535",
          "hcpcs_description": "Self care management training",
          "service_cnt": 249,
          "bene_uniq_cnt": 140,
          "avg_allowed_amt": 35.595823293,
          "avg_charge_amt": 41.427429719,
          "avg_payment_amt": 27.617791165
        },
        {
          "hcpcs": "97001",
          "hcpcs_description": "Physical therapy evaluation",
          "service_cnt": 177,
          "bene_uniq_cnt": 154,
          "avg_allowed_amt": 82.525988701,
          "avg_charge_amt": 90.46920904,
          "avg_payment_amt": 60.537062147
        },
        {
          "hcpcs": "97530",
          "hcpcs_description": "Therapeutic activities",
          "service_cnt": 65,
          "bene_uniq_cnt": 14,
          "avg_allowed_amt": 35.460923077,
          "avg_charge_amt": 42.04,
          "avg_payment_amt": 28.368923077
        },
        {
          "hcpcs": "97002",
          "hcpcs_description": "Physical therapy re-evaluation",
          "service_cnt": 16,
          "bene_uniq_cnt": 15,
          "avg_allowed_amt": 46.41,
          "avg_charge_amt": 50.7,
          "avg_payment_amt": 34.809375
        }
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
`POST /api/getSpecialists`

### Parameters

Parameter | Type | Description
--------- | ------- | -----------
lat | Number | Search location latitude
lng | Number | Search location longitude
sort| String | Sort algorithm
specialty | String | Desired specialty
