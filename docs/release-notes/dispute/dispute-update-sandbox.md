# Test Cases

<span style="color:#ff6600;">**Dispute API Endpoints**</span> 

## Dispute update
Updates dispute cases by canceling, finalizing, deleting, etc.

### Cancel a case
Cancels an open dispute case.

#### Request
**HTTP METHOD:** DELETE

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/dispute/v1/cases/99999999

#### Response
**HTTP Code:** 204 No Content

```
Successful.
```

### Delete caseItems associated with caseId: Single caseItemId
Deletes the caseItems associated with the caseId for a DisputeCase.

#### Request
**HTTP METHOD:** DELETE

**Target URL:** https://card-sandbox.api.fiservapps.com/api/dispute/v1/cases/999999999/caseItems?caseItemId=999999999

 
#### Response
**HTTP Code:** 204 No Content

### Delete caseItems associated with caseId: Partial scenario
Deletes the caseItems associated with the caseId for a partial success DisputeCase.

#### Request
**HTTP METHOD:** DELETE

**Target URL:** https://card-sandbox.api.fiservapps.com/api/dispute/v1/cases/999999999/caseItems?caseItemId=999999999&amp;caseItemId=999999998&amp;caseItemId=999999997


#### Response
**HTTP Code:** 206 Partial Success
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


### Delete caseItems associated with caseId: Multi case itemID
Deletes the caseItems associated with a caseId for a multi-case DisputeCase 

#### Request
**HTTP METHOD:** DELETE

**Target URL:** https://card-sandbox.api.fiservapps.com/api/dispute/v1/cases/999999999/caseItems?caseItemId=999999999&amp;caseItemId=999999998

 
#### Response
**HTTP Code:** 204 No Content


### Upload case document
Attaches a document to a dispute case. The 'caseId' will be unique, regardless of number of transactions involved in a given case. 'caseItemId' is unique to a single transaction in a given case.

#### Request
**HTTP METHOD:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/dispute/v1/cases/999999999/caseItems/999999999/document
```
Example curl for this endpoint:
    curl --location 'https://card-sandbox.api.fiservapps.com/cs/dispute/v1/cases/999999999/caseItems/999999999/document' \
        --header 'accept: application/json' \
        --header 'x-fapi-financial-id: 12345678' \
        --header 'Content-Type: multipart/form-data; boundary=' \
        --header 'Authorization: Bearer {token}' \
        --form 'document=@"{your_document}"'
    
Document size cannot exceed 10 MB. File types supported are pdf, tiff, jpeg, and png. Use the appropriate filename extension to indicate filetype.
```
#### Response
**HTTP Code:** 204 No Content
```
Successful.
```
 
### Upload case note by caseId and caseItemId
 Update dispute case with notes.

#### Request
**HTTP METHOD:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/api/dispute/v1/cases/999999999/caseItems/999999999/note

```
{
   "notes": "string of notes"
}
```
 
#### Response
**HTTP Code:** 204 No Content

### Upload case document by caseId and caseItemId
Attaches a document to a dispute case. The'caseId' must be unique, regardless of number of transactions involved in a given case. The 'caseItemId' must be unique to a single transaction in a given case.

#### Request
**HTTP METHOD:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/api/dispute/v1/cases/999999999/caseItems/999999999/document

```
MULTIPART/FORM-DATA

document: Select a file to upload. The maximum size is 5 MB.
File name (fileName) and extension type: allowed file types are pdf, tiff, jpeg, or png. For example. Fpr example, if you are uploading a pdf file, the extension is ".pdf".
```
 
#### Response
**HTTP Code:** 204 No Content
