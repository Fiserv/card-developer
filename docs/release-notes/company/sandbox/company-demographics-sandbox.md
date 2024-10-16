# Test Cases

<span style="color:#ff6600;">**Company API Endpoints**</span>

## Company Demographics

Tests must use only requests given here.

### Company Demographics v1: Search demographic details

This API will return demographic details of the associated parties of the company.

#### Request

**HTTP METHOD:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/companies/v1/demographics/search

```
{
   "companyIdentifier": "TEST0002",
   "systemIdentifier": "3771",
   "principalIdentifier": "0050",
   "agentIdentifier": "0000"
}
```

#### Response

**HTTP Code:** 200 OK

```
{
   "primaryAddresses": {
      "sequenceNumber": "00001",
      "name": "JESSE DOE",
      "workPhone": "9871625141",
      "address": {
         "addressLine1": "123 ANY STREET",
         "addressLine2": "APT 100",
         "country": "USA",
         "state": "NJ",
         "zipCode": "07054",
         "city": "PARSIPPANY"
      }
   },
   "previousAddresses": {
      "sequenceNumber": "00002",
      "address": {
         "addressLine1": "23 ANY STREET",
         "addressLine2": "APT 101",
         "country": "USA",
         "state": "NJ",
         "zipCode": "07054",
         "city": "PARSIPPANY"
      }
   },
   "secondaryAddresses": {
      "sequenceNumber": "00003",
      "workPhone": "9877665542",
      "address": {
         "addressLine1": "12 ANY STREET",
         "addressLine2": "APT 10",
         "country": "USA",
         "state": "NJ",
         "zipCode": "07054",
         "city": "PARSIPPANY"
      }
   },
   "individualGuarantors": [
      {
         "sequenceNumber": "00004",
         "firstName": "JESSE",
         "lastName": "DOE",
         "middleInitial": "M",
         "federalTaxFormTaxTypeCode": "SOCIAL_SECURITY",
         "federalTaxIdentifier": "123456789",
         "workPhone": "7406520178",
         "alternativePhone": "9789120123",
         "emailAddress": "JESSEDOE@EXAMPLE.COM",
         "address": {
            "addressLine1": "201 ANY STREET",
            "addressLine2": "APT 20",
            "country": "USA",
            "state": "NJ",
            "zipCode": "07054",
            "city": "PARSIPPANY"
         }
      }
   ],
   "companyGuarantors": [
      {
         "sequenceNumber": "00005",
         "name": "JESSE",
         "federalTaxFormTaxTypeCode": "SOCIAL_SECURITY",
         "federalTaxIdentifier": "129956789",
         "workPhone": "7406520178",
         "alternativePhone": "9789120123",
         "address": {
            "addressLine1": "13 ANY STREET",
            "addressLine2": "APT 19",
            "country": "USA",
            "state": "NJ",
            "zipCode": "07054",
            "city": "PARSIPPANY"
         }
      }
   ],
   "individualOwners": [
      {
         "sequenceNumber": "00006",
         "firstName": "JOHN",
         "lastName": "DOE",
         "middleInitial": "M",
         "federalTaxFormTaxTypeCode": "SOCIAL_SECURITY",
         "federalTaxIdentifier": "223456789",
         "workPhone": "7406520178",
         "emailAddress": "JESSEDOE@EXAMPLE.COM",
         "address": {
            "addressLine1": "12 ANY STREET",
            "addressLine2": "APT 10",
            "country": "USA",
            "state": "NJ",
            "zipCode": "07054",
            "city": "PARSIPPANY"
         }
      }
   ],
   "companyOwners": [
      {
         "sequenceNumber": "00007",
         "name": "DAVID",
         "federalTaxFormTaxTypeCode": "SOCIAL_SECURITY",
         "federalTaxIdentifier": "323456789",
         "workPhone": "7406520178",
         "address": {
            "addressLine1": "123 ANY STREET",
            "addressLine2": "APT 100",
            "country": "USA",
            "state": "NJ",
            "zipCode": "07054",
            "city": "PARSIPPANY"
         }
      }
   ]
}
```

### Company Demographics v1: Add company demographics details

This API will add demographic details for the parties associated with the company.

#### Request

**HTTP METHOD:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/companies/v1/demographics

```

{
   "companyIdentifier": "TEST0002",
   "systemIdentifier": "3771",
   "principalIdentifier": "0050",
   "agentIdentifier": "0000",
   "primaryAddress": {
      "name": "Jesse Doe",
      "workPhone": "7406520178",
      "address": {
         "addressLine1": "123 Any Street",
         "addressLine2": "Apt 100",
         "country": "USA",
         "state": "NJ",
         "zipCode": "07054",
         "city": "Parsippany"
      }
   },
   "previousAddress": {
      "address": {
         "addressLine1": "23 Any Street",
         "addressLine2": "Apt 101",
         "country": "USA",
         "state": "NJ",
         "zipCode": "07054",
         "city": "Parsippany"
      }
   },
   "secondaryAddress": {
      "workPhone": "6789120123",
      "address": {
         "addressLine1": "12 Any Street",
         "addressLine2": "Apt 10",
         "country": "USA",
         "state": "NJ",
         "zipCode": "07054",
         "city": "Parsippany"
      }
   },
   "individualGuarantor": {
      "firstName": "Jesse",
      "lastName": "Doe",
      "middleInitial": "M",
      "federalTaxFormTaxTypeCode": "SOCIAL_SECURITY",
      "federalTaxIdentifier": "123456789",
      "workPhone": "7406520178",
      "alternativePhone": "9789120123",
      "emailAddress": "jessedoe@example.com",
      "address": {
         "addressLine1": "201 Any Street",
         "addressLine2": "Apt 20",
         "country": "USA",
         "state": "NJ",
         "zipCode": "07054",
         "city": "Parsippany"
      }
   },
   "companyGuarantor": {
      "name": "Jesse",
      "federalTaxFormTaxTypeCode": "SOCIAL_SECURITY",
      "federalTaxIdentifier": "129956789",
      "workPhone": "7406520178",
      "alternativePhone": "9789120123",
      "address": {
         "addressLine1": "13 Any Street",
         "addressLine2": "Apt 19",
         "country": "USA",
         "state": "NJ",
         "zipCode": "07054",
         "city": "Parsippany"
      }
   },
   "individualOwner": {
      "firstName": "John",
      "lastName": "Doe",
      "middleInitial": "M",
      "federalTaxFormTaxTypeCode": "SOCIAL_SECURITY",
      "federalTaxIdentifier": "223456789",
      "workPhone": "7406520178",
      "emailAddress": "jessedoe@example.com",
      "address": {
         "addressLine1": "12 Any Street",
         "addressLine2": "Apt 10",
         "country": "USA",
         "state": "NJ",
         "zipCode": "07054",
         "city": "Parsippany"
      }
   },
   "companyOwner": {
      "name": "David",
      "federalTaxFormTaxTypeCode": "SOCIAL_SECURITY",
      "federalTaxIdentifier": "323456789",
      "workPhone": "7406520178",
      "address": {
         "addressLine1": "123 Any Street",
         "addressLine2": "Apt 100",
         "country": "USA",
         "state": "NJ",
         "zipCode": "07054",
         "city": "Parsippany"
      }
   }
}

```

#### Response

**HTTP Code:** 201 Created

```
{
   "companyIdentifier": "TEST0002",
   "systemIdentifier": "3771",
   "principalIdentifier": "0050",
   "agentIdentifier": "0000",
   "primaryAddress": {
      "sequenceNumber": "00001"
   },
   "previousAddress": {
      "sequenceNumber": "00002"
   },
   "secondaryAddress": {
      "sequenceNumber": "00003"
   },
   "individualGuaranter": {
      "sequenceNumber": "00004"
   },
   "companyGuaranter": {
      "sequenceNumber": "00005"
   },
   "individualOwner": {
      "sequenceNumber": "00006"
   },
   "companyOwner": {
      "sequenceNumber": "00007"
   }
}
```

### Company Demographics v1: Update company demographics details

This API will update demographic details of the associated parties of the company.

#### Request

**HTTP METHOD:** PATCH

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/companies/v1/demographics

```
{
    "companyIdentifier": "TEST0002",
    "systemIdentifier": "3771",
    "principalIdentifier": "0050",
    "agentIdentifier": "0000",
	 "demographics": {
        "companyName": "FISERV",
        "companyContactName": "DAVID",
        "creditScoreCode": "800",
        "numberOfEmployees": "101",
        "businessType": "PARTNERSHIP",
        "companyContactTelephoneNumber": "9898989898",
        "federalTaxFormTaxTypeCode": "TAX_ID",
        "federalTaxIdentifier": "9812312560",
        "reportLanguageCode": "ENGLISH",
        "miscellaneousField1Text": "A",
        "miscellaneousField2Text": "B",
        "miscellaneousField3Text": "C",
        "miscellaneousField4Text": "D",
        "address": {
            "addressLine1": "123 Any Street",
            "addressLine2": "Apt 100",
            "country": "USA",
            "state": "NJ",
            "zipCode": "07054",
            "city": "Parsippany"
        }
    },
    "primaryAddress": {
	    "sequenceNumber": "00001"
        "name": "Jesse, Doe",
        "workPhone": "9871625141",
        "address": {
            "addressLine1": "123 Any Street",
            "addressLine2": "Apt 100",
            "country": "USA",
            "state": "NJ",
            "zipCode": "07054",
            "city": "Parsippany"
        }
    },
    "previousAddress": {
       "sequenceNumber": "00002",
        "address": {
            "addressLine1": "23 Any Street",
            "addressLine2": "Apt 101",
            "country": "USA",
            "state": "NJ",
            "zipCode": "07054",
            "city": "Parsippany"
        }
    },
    "secondaryAddress": {
       "sequenceNumber": "00003",
        "workPhone": "9877665542",
        "address": {
            "addressLine1": "12 Any Street",
            "addressLine2": "Apt 10",
            "country": "USA",
            "state": "NJ",
            "zipCode": "07054",
            "city": "Parsippany"
        }
    },
    "individualGuarantor": {
        "sequenceNumber": "00004",
        "firstName": "Jesse",
        "lastName": "Doe",
        "middleInitial": "M",
        "federalTaxFormTaxTypeCode": "SOCIAL_SECURITY",
        "federalTaxIdentifier": "123456789",
        "workPhone": "7406520178",
        "alternativePhone": "9789120123",
        "emailAddress": "jessedoe@example.com",
        "address": {
            "addressLine1": "201 Any Street",
            "addressLine2": "Apt 20",
            "country": "USA",
            "state": "NJ",
            "zipCode": "07054",
            "city": "Parsippany"
        }
    },
    "companyGuarantor": {
        "sequenceNumber": "00005",
        "name": "Jesse",
        "federalTaxFormTaxTypeCode": "SOCIAL_SECURITY",
        "federalTaxIdentifier": "129956789",
        "workPhone": "7406520178",
        "alternativePhone": "9789120123",
        "address": {
            "addressLine1": "13 Any Street",
            "addressLine2": "Apt 19",
            "country": "USA",
            "state": "NJ",
            "zipCode": "07054",
            "city": "Parsippany"
        }
    },
    "individualOwner": {
        "sequenceNumber": "00006",
        "firstName": "John",
        "lastName": "Doe",
        "middleInitial": "M",
        "federalTaxFormTaxTypeCode": "SOCIAL_SECURITY",
        "federalTaxIdentifier": "223456789",
        "workPhone": "7406520178",
        "emailAddress": "jessedoe@example.com",
        "address": {
            "addressLine1": "12 Any Street",
            "addressLine2": "Apt 10",
            "country": "USA",
            "state": "NJ",
            "zipCode": "07054",
            "city": "Parsippany"
        }
    },
    "companyOwner": {
       "sequenceNumber": "00007",
        "name": "David",
        "federalTaxFormTaxTypeCode": "SOCIAL_SECURITY",
        "federalTaxIdentifier": "323456789",
        "workPhone": "7406520178",
        "address": {
            "addressLine1": "123 Any Street",
            "addressLine2": "Apt 100",
            "country": "USA",
            "state": "NJ",
            "zipCode": "07054",
            "city": "Parsippany"
        }
    }
}
```

#### Response

**HTTP Code:** 204 No Content

### Company Demographics v1: Delete company demographics details

This API is used to delete demographic details associated to the company.

#### Request

**HTTP METHOD:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/companies/v1/demographics

```
{
    "op": "DELETE_ASSOCIATION",
    "sequenceNumber": "00001",
    "companyIdentifier": "TEST0002",
    "systemIdentifier": "3771",
    "principalIdentifier": "0050",
    "agentIdentifier": "0000",
    "addressType": "INDIVIDUAL_GUARANTOR"
}
```

#### Response

**HTTP Code:** 204 No Content
