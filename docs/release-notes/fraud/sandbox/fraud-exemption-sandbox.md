# Test Cases

<span style="color:#ff6600;">**Fraud API Endpoints**</span>

When testing these endpoints, please use the test cases and test data from the Sandbox.

## Fraud Exemption

### Fraud Exemption v1: Retrieve travel exemption using filter- COUNTRY

Retrieve Countries list for Fraud Travel Exemptions. locationFilter value will be COUNTRY for fetching the Countries list.

#### Request

**HTTP Method:** GET

**Target URL:**  https://card-sandbox.api.fiservapps.com/cs/fraud/v1/exemptions/travel/locations?locationFilter=COUNTRY

#### Response

**HTTP Code:** 200 OK

```
{
    "locations": [
        {
            "code": "AFG",
            "name": "AFGHANISTAN"
        },
        {
            "code": "ALA",
            "name": "ALAND ISLANDS"
        },
        {
            "code": "ALB",
            "name": "ALBANIA"
        },
        {
            "code": "DZA",
            "name": "ALGERIA"
        }
    ]
}
```

### Fraud Exemption v1: Retrieve travel exemption using filter- STATE

Retrieve States list for Fraud Travel Exemptions. locationFilter value will be STATE for fetching the States list.

#### Request

**HTTP Method:** GET

**Target URL:**  https://card-sandbox.api.fiservapps.com/cs/fraud/v1/exemptions/travel/locations?locationFilter=STATE

#### Response

**HTTP Code:** 200 OK

```
{
    "locations": [
        {
            "code": "AL",
            "name": "ALABAMA"
        },
        {
            "code": "AK",
            "name": "ALASKA"
        },
        {
            "code": "AZ",
            "name": "ARIZONA"
        },
        {
            "code": "AR",
            "name": "ARKANSAS"
        }
    ]
}
```

### Fraud Exemption v1: Retrieve travel exemption using no filter

Bad Request Response for locations for Fraud Travel Exemptions without locationFilter parameter

#### Request

**HTTP Method:** GET

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/fraud/v1/exemptions/travel/locations

#### Response

**HTTP Code:** 400 Bad Request

```
{
    "status": "400",
    "path": "/api/fraud/v1/exemptions/locations",
   "instance": "/cs/fraud/v1/exemptions/travel/locations",
    "type": "https://card.developer.fiserv.com/fraud/error#invalid-request",
    "title": "Invalid Request"

}
```
