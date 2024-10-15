# Test Cases

<span style="color:#ff6600;">**Fraud API Endpoints**</span>

When testing these endpoints, please use the test cases and test data from the Sandbox.

## Travel Exemption

### Travel Exemption v1: Search Exemptions

This operation searches and retrieves any existing travel exemptions created by a cardholder. Two travel exemption lists are possible. To add, update or remove travel exemptions, this search Request must be conducted first to understand what and if any lists exist for a cardholder. The following Request example for the cardholder, with PAN 222297976430017, returns 2 exemption lists with effective start and end dates, and the FI-applied exclusion codes.

#### Request

**HTTP Method:** POST

**Target URL:**  https://card-sandbox.api.fiservapps.com/cs/travel/v1/exemptions/search

```
{
   "client": {
      "id": "84014831",
      "applicationName": "OpenSystems",
      "vendorName": "Mobiliti",
      "auditId": "Mobiliti"
   },
   "cardholder": {
      "pan": "2222979764340017",
      "memberNumber": "0",
      "firstName": "SUMITRA",
      "middleInitial": "S",
      "lastName": "VEER",
      "zip": "20120"
   }
}
```

#### Response

**HTTP Code:** 200 OK

```
{
   "travelExemptions": [
      {
         "exemptionNumber": 1,
         "startDateTime": "2019-07-20T07:00:00Z",
         "endDateTime": "2020-07-31T03:59:00Z",
         "lastUpdatedDateTime": "2019-06-07T07:00:00Z",
         "exemptionCodes": {
            "stateCountryCodes": [
               "AFG"
            ]
         }
      },
      {
         "exemptionNumber": 2,
         "startDateTime": "2019-05-03T21:14:00Z",
         "endDateTime": "2019-05-16T20:16:00Z",
         "lastUpdatedDateTime": "2019-05-16T20:16:00Z",
         "exemptionCodes": {
            "stateCountryCodes": [
               "AL",
               "ARM",
               "AUS",
               "BIH",
               "BRA",
               "BRB",
               "BWA",
               "CA",
               "CT",
               "DE",
               "ID",
               "IL",
               "IOT",
               "GA"
            ]
         }
      }
   ],
   "exclusions": [
      {
         "code": "AGO",
         "type": "C"
      },
      {
         "code": "DZL",
         "type": "C"
      },
      {
         "code": "FL",
         "type": "S"
      },
      {
         "code": "GA",
         "type": "S"
      },
      {
         "code": "USA",
         "type": "C"
      }
   ]
}
```

### Travel Exemption v1: Add Exemptions

Use to add new travel exemption data for the Requested card number or create a new list. Before you begin, retrieve the Travel Exemption List that includes FI exclusions.

Important! A cardholder can have a maximum of two travel plans on a specified card at any given time.

   - If two active travel exemptions exist, an error code results in the statusCode field of the Response. To include the new information, update an existing list, or expire an existing list to add a new list.
   - If FI-specified exclusion codes are included in a new list Request, an error Response occurs.
   - If a cardholder has not created a list, the return displays an empty list, designated as [ ], but the FI-defined travel exclusions is listed.

#### Request

**HTTP Method:** POST

**Target URL:**  https://card-sandbox.api.fiservapps.com/cs/travel/v1/exemptions

```
{
   "client": {
      "id": "84014831",
      "applicationName": "OpenSystem",
      "vendorName": "Mobiliti",
      "auditId": "84014831"
   },
   "cardholder": {
      "pan": "2222979764340017",
      "memberNumber": "0",
      "firstName": "SUMITRA",
      "middleInitial": "",
      "lastName": "VEER",
      "zip": "20120"
   },
   "startDateTime": "2020-07-30T22:15:00Z",
   "endDateTime": "2020-08-11T10:50:00Z",
   "exemptionCodes": {
      "stateCountryCodes": [
         "CAN"
      ]
   }
}
```

#### Response

**HTTP Code:** 200 OK

```
{
   "travelExemptions": [
      {
         "exemptionNumber": 1,
         "startDateTime": "2020-07-30T22:15:00Z",
         "endDateTime": "2020-08-11T10:50:00Z",
         "lastUpdatedDateTime": "2019-11-19T18:12:00Z",
         "exemptionCodes": {
            "stateCountryCodes": [
               "CAN"
            ]
         }
      },
      {
         "exemptionNumber": 2,
         "startDateTime": "2019-06-13T19:27:00Z",
         "endDateTime": "2019-06-14T19:27:00Z",
         "lastUpdatedDateTime": "2019-06-13T19:27:00Z",
         "exemptionCodes": {
            "stateCountryCodes": [
               "AL",
               "ARM",
               "AUS",
               "BIH",
               "BRA",
               "BRB",
               "BWA",
               "CA",
               "CT",
               "DE",
               "ID",
               "IL",
               "IOT",
               "GA"
            ]
         }
      }
   ],
   "exclusions": [
      {
         "code": "AGO",
         "type": "C"
      },
      {
         "code": "DZL",
         "type": "C"
      },
      {
         "code": "FL",
         "type": "S"
      },
      {
         "code": "GA",
         "type": "S"
      },
      {
         "code": "USA",
         "type": "C"
      }
   ]
}
```

### Travel Exemption v1: Update Exemptions

You must first retrieve a travel exemption list for the requested primary account number (PAN). Using this information, you can then make any necessary updates.

#### Request

**HTTP Method:** PUT

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/travel/v1/exemptions

```
{
   "client": {
      "id": "84014831",
      "applicationName": "OpenSystem",
      "vendorName": "Mobiliti",
      "auditId": "84014831"
   },
   "cardholder": {
      "pan": "2222979764340017",
      "memberNumber": "0",
      "firstName": "SUMITRA",
      "middleInitial": "",
      "lastName": "VEER",
      "zip": "20120"
   },
   "exemptionNumber": "1",
   "startDateTime": "2019-11-12T13:15:30Z",
   "endDateTime": "2019-12-15T13:15:30Z",
   "exemptionCodes": {
      "stateCountryCodes": [
         "CAN"
      ]
   }
}
```

#### Response

**HTTP Code:** 200

```
{
   "travelExemptions": [
      {
         "exemptionNumber": 1,
         "startDateTime": "2019-11-12T13:15:00Z",
         "endDateTime": "2019-12-15T13:15:00Z",
         "lastUpdatedDateTime": "2019-11-19T18:12:00Z",
         "exemptionCodes": {
            "stateCountryCodes": [
               "CAN"
            ]
         }
      }
   ],
   "exclusions": [
      {
         "code": "AGO",
         "type": "C"
      },
      {
         "code": "DZL",
         "type": "C"
      },
      {
         "code": "FL",
         "type": "S"
      },
      {
         "code": "GA",
         "type": "S"
      },
      {
         "code": "USA",
         "type": "C"
      }
   ]
}
```

### Travel Exemption v1: Expire Exemptions

Use to expire a travel exemptions plan for the requested PAN. Before you begin, retrieve the specified card Travel Exemption List including FI exclusions.

Important! A cardholder can have a maximum of two travel plans on a specified card at any given time.


   - If two lists already exist, an error code results in the statusCode field of the response. To include the new information, an update request can be made to an existing list, or an existing list must first be expired so the new list can be added.
   - If FI-specified exclusion codes are included in a new list request, an error response occurs.
   - If a cardholder has not created a list, the return displays an empty list, designated as [ ], but the FI-defined travel exclusions is listed.

**HTTP Method:** PUT

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/travel/v1/exemptions/expire

#### Request

```
{
   "client": {
      "id": "84014831",
      "applicationName": "OpenSystems",
      "vendorName": "Mobiliti",
      "auditId": "Mobiliti"
   },
   "cardholder": {
      "pan": "2222979764340017",
      "memberNumber": "0",
      "firstName": "SUMITRA",
      "middleInitial": "S",
      "lastName": "VEER",
      "zip": "20120"
   },
   "exemptionNumber": "1"
}
```

#### Response

**HTTP Code:** 200

```
{
   "travelExemptions": [
      {
         "exemptionNumber": 1,
         "startDateTime": "2019-11-19T18:12:00Z",
         "endDateTime": "2019-11-19T18:12:00Z",
         "lastUpdatedDateTime": "2019-11-19T18:12:00Z",
         "exemptionCodes": {
            "stateCountryCodes": [
               "AFG"
            ]
         }
      },
      {
         "exemptionNumber": 2,
         "startDateTime": "2019-05-03T21:14:00Z",
         "endDateTime": "2019-05-03T21:14:00Z",
         "lastUpdatedDateTime": "2019-05-03T21:14:00Z",
         "exemptionCodes": {
            "stateCountryCodes": [
               "AL",
               "ARM",
               "AUS",
               "BIH",
               "BRA",
               "BRB",
               "BWA",
               "CA",
               "CT",
               "DE",
               "ID",
               "IL",
               "IOT",
               "GA"
            ]
         }
      }
   ],
   "exclusions": [
      {
         "code": "AGO",
         "type": "C"
      },
      {
         "code": "DZL",
         "type": "C"
      },
      {
         "code": "FL",
         "type": "S"
      },
      {
         "code": "GA",
         "type": "S"
      },
      {
         "code": "USA",
         "type": "C"
      }
   ]
}
```
