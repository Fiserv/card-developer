# Test Cases

<span style="color:#ff6600;">**Dispute API Endpoints**</span> 

## Dispute Update

### Dispute Update v1: Cancel a caseid

Cancels dispute case.

#### Request

**HTTP METHOD:** DELETE

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/dispute/v1/cases/99999999

#### Response

**HTTP Code:** 204 No Content

```
Successful.
```

### Dispute Update v1: Cancel a caseitemId for single caseitemId

Should delete the caseItems associated to caseId for DisputeCase

#### Request

**HTTP METHOD:** DELETE

**Target URL:** https://card-sandbox.api.fiservapps.com/api/dispute/v1/cases/999999999/caseItems?caseItemId=999999999

#### Response

**HTTP Code:** 204 No Content

### Dispute Update v1: Cancel a caseitemId for multi caseitemId

Should delete the caseItems associated to caseId for DisputeCase

#### Request

**HTTP METHOD:** DELETE

**Target URL:** https://card-sandbox.api.fiservapps.com/api/dispute/v1/cases/999999999/caseItems?caseItemId=999999999&caseItemId=999999998

#### Response

**HTTP Code:** 204 No Content

### Dispute Update v1: Cancel a caseitemId for partial scenario

Should delete the caseItems associated to caseId for DisputeCase for Partial success

#### Request

**HTTP METHOD:** DELETE

**Target URL:** https://card-sandbox.api.fiservapps.com/api/dispute/v1/cases/999999999/caseItems?caseItemId=999999999&caseItemId=999999998&caseItemId=999999997

 
#### Response

**HTTP Code:** 206 Partial Success Response

```
{
  "warningInfo": {
    "message": "caseItem(s) either are not in draft state to be able to be canceled or do not belong to the given caseId: [999999997].",
    "spanId": "c5ac93abafad5ccc",
    "traceId": "df35221b6ee5f9b5",
    "warningDetails": [
      {
        "code": "321",
        "detail": "caseItem(s) either are not in draft state to be able to be canceled or do not belong to the given caseId: [999999997].",
        "spanId": "c5ac93abafad5ccc",
        "timestamp": "2023-01-09T13:40:43.087958"
      }
    ]
  }
}
```

### Dispute Update v1: Update a note in caseitemId

Update dispute case with notes

#### Request

**HTTP METHOD:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/dispute/v1/cases/999999999/caseItems/999999999/note

```
{
   "notes": "string of notes"
}
```

#### Response

**HTTP Code:** 204 No Content
```
Successful.
```
 
### Dispute Update v1: Upload document in caseitemId

Allows to attach a document to a dispute case. 'caseId' is a unique value, regardless of number of transactions involved in a given case. 'caseItemId' is a unique value to a single transaction in a given case.

#### Request

**HTTP METHOD:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/dispute/v1/cases/999999999/caseItems/999999999/document

```
MULTIPART/FORM-DATA

 document: Select a file that needs to be uploaded. Maximum size supported is 5 MB.
  fileName: Name of file with correct extension. Files supported are pdf, tiff, jpeg, png. For example, If a pdf is being uploaded then make sure to provide an extension as pdf only.
```
 
#### Response

**HTTP Code:** 204 No Content
