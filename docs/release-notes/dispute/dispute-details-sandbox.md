# Test Cases

<span style="color:#ff6600;">**Dispute API Endpoints**</span>

## Dispute details

### Retreive cases by cardNumber
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
  "referenceId": "serv.net:___212344MBVKXK4K:0103b250-a424-4cd7-bfaa-807f0ff79d23",
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
   
### Retrieve cases by caseId
Returns dispute case details for a given caseId. 'caseId' must be unique, regardless of the number of transactions involved in a given case. 'caseItemId' must be unique to a single transaction in a given case.

#### Request
**HTTP METHOD:** GET

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/dispute/v1/cases/999999999

#### Response
**HTTP Code:**  200 OK
```
{
  "caseId": "999999999",
  "cardNumber": "400020XXXXXX4000",
  "role": "I",
  "roleDesc": "Issuer",
  "referenceId": "serv.net:___212344MBVKXK4K:0103b250-a424-4cd7-bfaa-807f0ff79d23",
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

### Retrieve caseItems details by caseID and caseItemIDs

 Returns dispute case Item details for a disputed transaction.

#### Request
**HTTP METHOD:** GET

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/dispute/v1/cases/999999999/caseItems/999999999

 
#### Response
**HTTP Code:** 200 OK
```
 {
  "transactionDescription": "Transaction Description",
  "imageCount": "1",
  "referenceId": "serv.net:___212344MBVKXK4K:0103b250-a424-4cd7-bfaa-807f0ff79d23",
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

### Retrieve case document
Retrieves a document attached to a case item. 

**Note**: There are three parameters in URL:

   - CaseID- It must be unique, regardless of number of transactions involved in a given case creation.
   - CaseItemID- It must be unique to a single transaction in a given case.
   - DocID- It is a Document ID which is returned in Query Item Status.

#### Request
**HTTP METHOD:** GET

**Target URL:** https://card-sandbox.api.fiservapps.com/api/dispute/v1/cases/999999999/caseItems/999999999/document/987654321369

 
#### Response
**HTTP Code:** 200 OK

```
file.pdf
```

### View questionnaire
View submitted questionnaire answers for a completed case item. 

#### Request
**HTTP METHOD:** GET

**Target URL:**  https://card-sandbox.api.fiservapps.com/cs/dispute/v1/cases/999999999/questionnaire/999999999

#### Response
**HTTP Code:** 200 OK

```
{
  "caseItemId": "999999999",
  "referenceId": "serv.net:___212344MBVKXK4K:0103b250-a424-4cd7-bfaa-807f0ff79d23",
  "questions": [
        {
            "questionName": "QuestVar_CaseItem.Unauth_Participation",
            "questionValue": "Yes",
            "questionDescription": "Did you participate in the transaction?"
        },
        {
            "questionName": "QuestVar_CaseItem.DisputeCategory",
            "questionValue": "C",
            "questionDescription": "Why are you disputing this transaction?"
        },
        {
            "questionName": "QuestVar_CaseItem.Auth_MerchantDesc",
            "questionValue": "Test",
            "questionDescription": "What did you purchase? Please be specific as possible. (Brand, size, color, etc.) "
        },
        {
            "questionName": "QuestVar_CaseItem.Merchnds_Or_Service",
            "questionValue": "B",
            "questionDescription": "Is this merchandise or a service?"
        },
        {
            "questionName": "Questvar_CaseItem.DisputeReasonService",
            "questionValue": "Test",
            "questionDescription": "Why are you dissatisfied with the service? (Please be as detailed as possible.)"
        },
        {
            "questionName": "QuestVar_CaseItem.RecurringCharge",
            "questionValue": "No",
            "questionDescription": "Is this a recurring charge?"
        },
        {
            "questionName": "QuestVar_CaseItem.DisputePortion",
            "questionValue": "A",
            "questionDescription": "How much of the transaction amount are you disputing?"
        },
        {
            "questionName": "QuestVar_CaseItem.MerchContactAttemptMer",
            "questionValue": "No",
            "questionDescription": "Did you attempt to contact the merchant to resolve the issue?"
        },
        {
            "questionName": "QuestVar_CaseItem.AdditionalInformation",
            "questionValue": "No",
            "questionDescription": "Is there any additional information you would like to provide?"
        },
        {
            "questionName": "QuestVar_CaseItem.OralNotification",
            "questionValue": "No",
            "questionDescription": "Change date of Oral Notification?"
        }
  ]
}
```        
