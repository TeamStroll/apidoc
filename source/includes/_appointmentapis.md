# Appointment APIs

## retrieveAppointments

```shell
curl 'https://provider-qa.strollhealth.com/api/retrieveAppointments'
-H 'origin: https://provider-qa.strollhealth.com'
-H 'accept-encoding: gzip, deflate, br'
-H 'x-requested-with: XMLHttpRequest'
-H 'accept-language: en-US,en;q=0.8'
-H 'content-type: application/json'
-H 'accept: application/json, text/javascript, */*; q=0.01'
-H 'referer: https://provider-qa.strollhealth.com/radiology_dashboard/schedule'
-H 'authority: provider-qa.strollhealth.com'
--data-binary '{"startTime":1498374000000,"endTime":1500188400000,"facilityEquipmentId":29,"facilityId":10006,"contrast":"WITHOUT"}'
--compressed
```

>Example Response:

```json
{
  "29": [
    {
      "meta": {
        "href": null,
        "mediaType": "application/vnd.sh-v1.0+json"
      },
      "appointmentId": 1825,
      "equipmentId": 29,
      "patientId": 5062,
      "facilityId": 10006,
      "faxRequestId": 1653,
      "startTime": 0,
      "endTime": 0,
      "cptCode": "77055",
      "cost": 94.2,
      "reasonNotYetScheduled": "N/A",
      "stillWantToSchedule": false,
      "orderStatus": "CANCELED",
      "patientDTO": {
        "meta": {
          "href": null,
          "mediaType": "application/vnd.sh-v1.0+json"
        },
        "id": 5062,
        "autopilotContactId": "person_A96A6045-EFD0-43AD-B9F9-FDDF8FB502C5",
        "firstName": "Noosheen",
        "lastName": "Hashemi",
        "birthDate": "1963-03-21 00:00:00.0",
        "gender": "F",
        "email": "jordan@strollhealth.com",
        "zip": "94109",
        "paySpecDTO": {
          "pi": "00039",
          "payerName": "Anthem Blue Cross California",
          "mi": "JQU752A74311"
        },
        "miInvalid": false,
        "rejectReason": null,
        "phoneNumber": "(650) 380-8449",
        "phoneNumberType": "Cell",
        "agreedToTerms": true,
        "termVersion": "1.0",
        "linkId": "408541",
        "middleInitital": null
      }
    }
    ...More...
  ],
  "-1": [
    {
      "meta": {
        "href": null,
        "mediaType": "application/vnd.sh-v1.0+json"
      },
      "appointmentId": 1956,
      "equipmentId": 0,
      "patientId": 4427,
      "facilityId": 10006,
      "faxRequestId": 1784,
      "startTime": 0,
      "endTime": 0,
      "cptCode": "74181",
      "cost": 547.45,
      "reasonNotYetScheduled": "N/A",
      "stillWantToSchedule": false,
      "orderStatus": "CANCELED",
      "patientDTO": {
        "meta": {
          "href": null,
          "mediaType": "application/vnd.sh-v1.0+json"
        },
        "id": 4427,
        "autopilotContactId": "person_A66BBDC8-6884-4453-9FB7-3AB03C2FAC63",
        "firstName": "Matt",
        "lastName": "Maurer",
        "birthDate": "1985-08-21 00:00:00.0",
        "gender": "M",
        "email": "m@gmail.com",
        "zip": "94109",
        "paySpecDTO": {
          "pi": "00361",
          "payerName": "Blue Shield California",
          "mi": "XED900773881"
        },
        "miInvalid": false,
        "rejectReason": null,
        "phoneNumber": "(650) 380-8449",
        "phoneNumberType": "Cell",
        "agreedToTerms": true,
        "termVersion": "1.0",
        "linkId": "436021",
        "middleInitital": null
      }
    },
    ...More...
  ]
}
```

Retrieves appointment information between two dates for a given facility and equipment. Shows appointment information as well as patient information.

### HTTP Request

`POST https://provider.strollhealth.com/api/retrieveAppointments`

### Parameters

Parameter | Type | Description
--------- | ------- | -----------
startDate | Number | Start date in appointments query, in Moment format
endDate | Number | End date in appointments query, in Moment format
facilityId | Number | ID of facility to find appointments
facilityEquipmentId | Number | ID of desired equipment in facility
contrast | String | Whether procedure is with or without contrast. Possible options are "WITH" or "WITHOUT"

## retrieveAllOpenings

```shell
curl 'https://provider-qa.strollhealth.com/api/retrieveAllOpenings'
-H 'origin: https://provider-qa.strollhealth.com'
-H 'accept-encoding: gzip, deflate, br'
-H 'x-requested-with: XMLHttpRequest'
-H 'accept-language: en-US,en;q=0.8'
-H 'authorization: Bearer meowmeowmeow'
-H 'content-type: application/json'
-H 'accept: application/json, text/javascript, */*; q=0.01'
-H 'referer: https://provider-qa.strollhealth.com/radiology_dashboard/schedule'
-H 'authority: provider-qa.strollhealth.com'
--data-binary '{"startDate":1498374000000,"endDate":1500188400000,
"modality":"MRI","facilityId":10006,"contrast":"WITHOUT"}'
--compressed
```

>Example Response:

```json
{
  "meta": {
    "href": null,
    "mediaType": "application/vnd.sh-v1.0+json"
  },
  "facilityEquipmentIds": [
    29
  ],
  "startDate": 1498348800000,
  "endDate": 1500163200000,
  "equipmentTimeSlotsDTOs": {
    "29": {
      "meta": {
        "href": null,
        "mediaType": "application/vnd.sh-v1.0+json"
      },
      "timeTuplesList": [
        {
          "timeSlots": [
            {
              "timeSlot": [
                1498489200000,
                1498496400000
              ]
            },
            {
              "timeSlot": [
                1498498200000,
                1498514400000
              ]
            }
          ]
        },
        {
          "timeSlots": [
            {
              "timeSlot": [
                1498575600000,
                1498590000000
              ]
            },
            {
              "timeSlot": [
                1498593600000,
                1498600800000
              ]
            }
          ]
        },
        {
          "timeSlots": [
            {
              "timeSlot": [
                1498662000000,
                1498687200000
              ]
            }
          ]
        },
        ...More...
      ],
      "facilityEquipmentId": 29
    }
  }
}
```

Retrieve all openings in time tuple form for a specified facility, modality, and contrast, between two dates.

### HTTP Request

`POST https://provider.strollhealth.com/api/retrieveAllOpenings`

### Parameters

Parameter | Type | Description
--------- | ------- | -----------
startDate | Number | Start date in openings query, in Moment format
endDate | Number | End date in openings query, in Moment format
facilityId | Number | ID of facility to find openings for
modality | String | Modality to find openings for
contrast | String | Whether procedure is with or without contrast. Possible options are "WITH" or "WITHOUT"
