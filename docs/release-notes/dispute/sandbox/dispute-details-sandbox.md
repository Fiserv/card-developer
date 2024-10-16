# Test Cases

<span style="color:#ff6600;">**Dispute API Endpoints**</span>

## Dispute details

### Dispute Details v1: Search by caseId

Returns dispute case details for a given caseId. 'caseId' is a unique value, regardless of number of transactions involved in a given case. 'caseItemId' is a unique value to a single transaction in a given case.

#### Request

**HTTP METHOD:** GET

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/dispute/v1/cases/999999999
     
#### Response

**HTTP Code:** 200 OK

```
{
  "caseId": "999999999",
  "cardNumber": "400020XXXXXX4000",
  "role": "I",
  "roleDesc": "Issuer",
  "caseItems": [
    {
      "caseItemId": "999999999",
      "accountNumber": "123456XXX7789",
      "type": "DS",
      "typeDesc": "Dispute",
      "status": "Closed",
      "createdDateTime": "2021-07-20T07:00:00Z",
      "closedDateTime": "2021-07-20T07:00:00Z",
      "claimAmount": "200.50",
      "claimCurrency": "US Dollar (USD)",
      "reasonCode": "112",
      "currentStep": 999,
      "issuerFiId": "12345678",
      "acquirerFiId": "87654321",
      "acquirerRefNum": "14515501298011980119806",
      "sequence": "121980",
      "transactionDate": "1990-08-24",
      "transactionAmount": "200.50",
      "transactionCurrency": "US Dollar (USD)",
      "network": "VISA",
      "authorizationCode": "628934",
      "terminalId": "VMDIEOS1",
      "terminalName": "Home Supply",
      "stateCode": "299",
      "stateCodeDesc": "Case Closed",
      "completionCode": "390",
      "completionCodeDesc": "Closed - Claim resolved via RDR"
    },
    {
      "caseItemId": "999999998",
      "accountNumber": "123456XXX7789",
      "type": "DS",
      "typeDesc": "Dispute",
      "status": "Closed",
      "createdDateTime": "2021-07-20T07:00:00Z",
      "closedDateTime": "2021-07-20T07:00:00Z",
      "claimAmount": "200.50",
      "claimCurrency": "US Dollar (USD)",
      "reasonCode": "112",
      "currentStep": 999,
      "issuerFiId": "12345678",
      "acquirerFiId": "87654321",
      "acquirerRefNum": "14515501298011980119806",
      "sequence": "121980",
      "transactionDate": "1990-08-24",
      "transactionAmount": "200.50",
      "transactionCurrency": "US Dollar (USD)",
      "network": "VISA",
      "authorizationCode": "628934",
      "terminalId": "VMDIEOS1",
      "terminalName": "Home Supply",
      "stateCode": "299",
      "stateCodeDesc": "Case Closed",
      "completionCode": "390",
      "completionCodeDesc": "Closed - Claim resolved via RDR"
    }
  ]
}
```
   
### Dispute Details v1: Search by caseitemid

Returns dispute case Item details for a disputed transaction

#### Request

**HTTP METHOD:** GET

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/dispute/v1/cases/999999999/caseItems/999999999

#### Response

**HTTP Code:**  200 OK

```
{
  "transactionDescription": "Transaction Description",
  "imageCount": "1",
  "adjustments": [
    {
      "id": "55748",
      "type": "CB",
      "typeDesc": "chargeback",
      "intExtType": "I",
      "amount": "20.00",
      "comment": "Credit Cardholder-Disputed Transaction",
      "status": "Done",
      "debitCreditIndicator": "C"
    }
  ],
  "history": [
    {
      "dateTime": "2021-07-20T07:00:00Z",
      "stepName": "EN",
      "description": "johndoe (Public): Item# 123456789:  200.05 04/21/220.   223 - PC credit issued"
    }
  ],
  "forms": [
    {
      "id": "12473205",
      "name": "FRM_Dispute_accepted_and_PC_Given",
      "sourceFileName": "sourceFile.pdf",
      "createdDateTime": "2021-07-20T07:00:00Z"
    }
  ],
  "networkReasonCode": "115"
}
```        

### Dispute Details v1: Search by card number

Returns dispute case details for a given card number.

#### Request

**HTTP METHOD:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/dispute/v1/cases/searchByCard

```
{
  "cardNumber": "4000200030004000",
  "createFromDate": "1990-08-24",
  "createToDate": "1990-08-24",
  "claimAmountMin": 25.05,
  "claimAmountMax": 80.5,
  "dispositionIndicator": "UNRESOLVED"
}
```

#### Response

**HTTP Code:** 200 OK

```
{
  "cardNumber": "400020XXXXXX4000",
  "cases": [
    {
      "caseId": "999999999",
      "role": "I",
      "roleDesc": "Issuer",
      "caseItems": [
        {
          "caseItemId": "999999999",
          "accountNumber": "123456XXX7789",
          "type": "DS",
          "typeDesc": "Dispute",
          "status": "Closed",
          "createdDateTime": "2021-07-20T07:00:00Z",
          "closedDateTime": "2021-07-20T07:00:00Z",
          "claimAmount": "200.50",
          "claimCurrency": "US Dollar (USD)",
          "reasonCode": "112",
          "reasonCodeDescription": "Merchandise not as described",
          "currentStep": 999,
          "issuerFiId": "12345678",
          "acquirerFiId": "87654321",
          "acquirerRefNum": "14515501298011980119806",
          "sequence": "121980",
          "transactionDate": "1990-08-24",
          "transactionAmount": "200.50",
          "transactionCurrency": "US Dollar (USD)",
          "network": "VISA",
          "authorizationCode": "628934",
          "terminalId": "VMDIEOS1",
          "terminalName": "Home Supply",
          "stateCode": "299",
          "stateCodeDesc": "Case Closed",
          "completionCode": "390",
          "completionCodeDesc": "Closed - Claim resolved via RDR"
        }
      ]
    }
  ]
}
``` 

### Dispute Details v1: Retrieve submitted questionnaire using caseitemId

View the completed questionnaire answer for a case item.

#### Request

**HTTP METHOD:** GET

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/dispute/v1/cases/999999999/questionnaire/999999999

#### Response

**HTTP Code:** 200 OK

```
{
  "caseItemId": "999999999",
  "questions": [
    {
      "questionName": "QuestVar_CaseItem.Unauth_Participation",
      "questionValue": "Yes",
      "questionDescription": "Did you participate in the transaction?"
    }
  ]
}
```

### Dispute Details v1: Retrieve uploaded document of caseitemId

Retrieves a document attached to a case item. Note: There are 3 parameters in URL. CaseID- It is a unique value, regardless of number of transactions involved in a given case creation. CaseItemID- It is a unique value to a single transaction in a given case. DocID- It is a Document ID which is returned in Query Item Status. 

#### Request

**HTTP METHOD:** GET

**Target URL:**  https://card-sandbox.api.fiservapps.com/api/dispute/v1/cases/999999999/caseItems/999999999/document/987654321369

#### Response

**HTTP Code:** 200 OK

```
file.pdf
```        
