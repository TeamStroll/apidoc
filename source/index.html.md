---
title: Stroll Api

language_tabs:
  - shell

toc_footers:
  - <a href='https://github.com/tripit/slate'>Documentation Powered by Slate</a>

includes:
  - appointmentapis
  - patientapis
  - platformapis
  - faxrequests
  - dtos
  - errors

search: true
---

# Introduction

Welcome to the Stroll Health API!


# Authentication
> To authorize, use this code:

```shell
curl 'https://provider.strollhealth.com/oauth/token'
-H 'origin: https://provider.strollhealth.com'
-H 'accept-encoding: gzip, deflate, br'
-H 'x-requested-with: XMLHttpRequest'
-H 'accept-language: en-US,en;q=0.8'
-H 'authorization: Basic bXktdHJ1c3RlZC1jbGllbnQxOg=='
-H 'content-type: application/x-www-form-urlencoded'
-H 'accept: application/json, text/javascript, */*; q=0.01'
-H 'referer: https://provider.strollhealth.com/'
-H 'authority: provider.strollhealth.com'
--data 'grant_type=password&username=sh:jamessmith@strollhealth.com&password=Strollh3alth!' --compressed
```

> The above command returns JSON structured like this:

```json
{
    "access_token": "AUTH_TOKEN",
    "token_type": "bearer",
    "refresh_token": "AUTH_TOKEN",
    "expires_in": 86399,
    "scope": "read write trust",
    "jti": "6d5f9a5e-e6ef-4200-af38-eafd7f513718"
}
```

Stroll uses OAuth2 to allow access to the API.
Stroll expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: bearer AUTH_TOKEN`

<aside class="notice">
You must replace <code>AUTH_TOKEN</code> with a user's authorization token.
</aside>

# User Microservice

## Get Current User

```shell
curl --include \
     --header "Authorization: Bearer AUTH_TOKEN" \
  'http://provider.strollhealth.com/user/current'
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

`GET http://provider.strollhealth.com/user/current`

<aside class="success">
Remember — a happy user is an authenticated user!
</aside>

## Get Current User's Sites

```shell
curl --include \
     --header "Authorization: Bearer AUTH_TOKEN" \
  'http://provider.strollhealth.com/user/sites'
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

### HTTP Request

`GET http://provider.strollhealth.com/user/sites`

## Get Tenants by Email

```shell
curl --include \
     --header "Authorization: Bearer AUTH_TOKEN" \
  'http://provider.strollhealth.com/user/tenants?email=jamessmith@strollhealth.com'
```

> The above command returns JSON structured like this:

```json
[
  "sh"
]
```

This endpoint retrieves tenants corresponding to an email.


### HTTP Request

`GET http://provider.strollhealth.com/user/tenants?email={some_email}`

### Parameters

Parameter | Type | Description
--------- | ------- | -----------
email | String | An user email


## Get User's Signature

```shell
curl --include \
     --header "Authorization: Bearer AUTH_TOKEN" \
  'http://provider.strollhealth.com/user/24/profile/signature'
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

`GET http://provider.strollhealth.com/user/{userId}/profile/signature`

### Parameters

Parameter | Type | Description
--------- | ------- | -----------
userId | String | A user id for which you want to retrieve the signature


## Get Facility's Users

```shell
curl --include \
     --header "Authorization: Bearer AUTH_TOKEN" \
  'http://provider.strollhealth.com/user/facility/some_facility/users'
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

`GET http://provider.strollhealth.com/user/facility/{facility_name}/users`

### Parameters

Parameter | Type | Description
--------- | ------- | -----------
facility_name | String | Name of the facility for which you wish to retrieve users


## Update User's Signature

```shell
curl --include \
     --header "Authorization: Bearer AUTH_TOKEN" \
  'http://provider.strollhealth.com/user/tenants?email=jamessmith@strollhealth.com'
```

> The above command returns JSON structured like this:

```json
[
  "sh"
]
```

This endpoint retrieves tenants corresponding to an email.


### HTTP Request

`GET http://provider.strollhealth.com/user/tenants?email={some_email}`

### Parameters

Parameter | Type | Description
--------- | ------- | -----------
email | String | An user email
