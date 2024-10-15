# Test Cases

<span style="color:#ff6600;">**Dispute API Endpoints**</span>

## Dispute create

### Dispute Create Claim V2- Single TransactionID

Creates a dispute case for given transactions of a particular card number

#### Request

**HTTP METHOD:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/dispute/v2/cases/claim

```
{
  "cardNumber": "4000200030004000",
  "errorBehaviour": "ABORT_ON_FIRST_NO_ROLLBACK",
  "issuerOrAcquirer": "Issuer",
  "listOfTransactions": [
    {
      "transactionId": "{\"lifeCycleKey\":\"12323301232312331\",\"activeKey\":\"0210\",\"duID\":\"11348539120200526\"}"
    }
  ]

```

#### Response

**HTTP Code:** 200 OK

```
{
  "caseId": "999999999",
  "caseItemIds": [
    "999999999"
  ]
}
```

### Dispute Create Claim V2- Multi TransactionID

Creates a dispute case for given transactions of a particular card number

#### Request

**HTTP METHOD:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/dispute/v2/cases/claim

```
{
  "cardNumber": "4000200030004000",
  "errorBehaviour": "ABORT_ON_FIRST_NO_ROLLBACK",
  "issuerOrAcquirer": "Issuer",
  "listOfTransactions": [
    {
      "transactionId": "{\"lifeCycleKey\":\"12323301232312331\",\"activeKey\":\"0210\",\"duID\":\"11348539120200526\"}"
    },
    {
      "transactionId": "{\"lifeCycleKey\":\"12323301232312331\",\"activeKey\":\"0210\",\"duID\":\"11348539120200527\"}"
    }
  ]
}
```

#### Response

**HTTP Code:** 200 OK

```
{
  "caseId": "999999999",
  "caseItemIds": [
    "999999999",
    "999999998"
  ]
}
```

### Dispute Create Claim V2- Partial Scenario

Creates a dispute case for given transactions of a particular card number

#### Request

**HTTP METHOD:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/dispute/v2/cases/claim

```
{
  "cardNumber": "4000200030004000",
  "errorBehaviour": "ABORT_ON_FIRST_NO_ROLLBACK",
  "issuerOrAcquirer": "Issuer",
  "listOfTransactions": [
    {
      "transactionId": "{\"lifeCycleKey\":\"12323301232312331\",\"activeKey\":\"0210\",\"duID\":\"11348539120200526\"}"
    },
    {
      "transactionId": "{\"lifeCycleKey\":\"12323301232312331\",\"activeKey\":\"0210\",\"duID\":\"11348539120200527\"}"
    },
    {
      "transactionId": "{\"lifeCycleKey\":\"12323301232312331\",\"activeKey\":\"0210\",\"duID\":\"11348539120200528\"}"
    }
  ]
}
```

#### Response

**HTTP Code:** 206 Partial Successful

```
{
    "caseId": "999999999",
    "caseItemIds": [
        "999999999",
        "999999998"
    ],
    "warningInfo": {
        "message": "Draft case could not be created for some of the transactionIds",
        "warningDetails": [
            {
                "code": "325",
                "detail": "INFO: [3] transactionId - That transaction is already in use by 999999997",
                "spanId": "219b5ea63f7a53e6",
                "timestamp": "2024-05-21T07:43:41.259700487"
            }
        ]
    },
    "instance": "/cs/dispute/v2/cases/claim",
    "status": "206"
}
```

### Dispute Submit Questionnaire- Withdrawal- Non Fraud

Submits the questionnaire for a case item. Questionnaires belongs to Withdrawal- Non Fraud Flow

#### Request

**HTTP METHOD:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/dispute/v1/cases/999999999/questionnaire

```
{
  "caseItemIds": [
    "999999999"
  ],
  "questionnaire": [
        {
            "questionName": "QuestVar_CaseItem.Unauth_Participation",
            "questionValue": "Yes"
        },
        {
            "questionName": "QuestVar_CaseItem.ATMWDL_DSReason",
            "questionValue": "B" 
        },
        {
            "questionName": "QuestVar_CaseItem.ATM_ReceiveAmount",
            "questionValue": "10.00"
        },
        {
            "questionName": "QuestVar_CaseItem.AdditionalInformation",
            "questionValue": "Yes"
        },
        {
            "questionName": "QuestVar_CaseItem.GeneralComments",
            "questionValue": "This is for testing Dispute Case"
        },
        {
            "questionName": "QuestVar_CaseItem.OralNotification",
            "questionValue": "Yes"
        },
        {
            "questionName": "QuestVar_CaseItem.OralNotificationDate",
            "questionValue": "04/10/2023"
        }
  ]
}
```

#### Response

**HTTP Code:** 200 OK

```
{
  "caseId": "999999999",
  "caseItemDetails": [
    {
      "caseItemType": "DISPUTE",
      "caseItemId": "999999999",
      "caseItemStatus": "PENDING",
      "caseItemStateCodeDescription": "QUESTIONNAIRE_COMPLETE",
      "reasonCode": "105",
      "reasonCodeDescription": "CHARGED MORE THAN ONCE"
    }
  ]
}
```

### Dispute Submit Questionnaire- Deposit- Non Fraud- Multi CaseItem

Submits the questionnaire for a case item. Questionnaires belongs to Deposit- Non Fraud Flow for Multi Case Items

#### Request

**HTTP METHOD:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/dispute/v1/cases/999999999/questionnaire

```
{
    "caseItemIds": [
        "999999999"
        "999999998"
    ],
    "questionnaire": [
        {
            "questionName": "QuestVar_CaseItem.Unauth_Participation",
            "questionValue": "Yes"
        },
        {
            "questionName": "QuestVar_CaseItem.SelectATMDSReason",
            "questionValue": "A" 
        },
        {
            "questionName": "QuestVar_CaseItem.Cash_or_Checks_Returned",
            "questionValue": "Yes"
        },
        {
            "questionName": "QuestVar_CaseItem.AmountReturned",
            "questionValue": "10.00"
        },
        {
            "questionName": "QuestVar_CaseItem.TotalAmountofDispute",
            "questionValue": "5.00"
        },
        {
            "questionName": "QuestVar_CaseItem.AdditionalInformation",
            "questionValue": "Yes"
        },
        {
            "questionName": "QuestVar_CaseItem.GeneralComments",
            "questionValue": "This is for testing Dispute Case"
        },
        {
            "questionName": "QuestVar_CaseItem.OralNotification",
            "questionValue": "Yes"
        },
        {
            "questionName": "QuestVar_CaseItem.OralNotificationDate",
            "questionValue": "04/10/2023"
        }
    ]
}
```

#### Response

**HTTP Code:** 200 OK

```
{
  "caseId": "999999999",
  "caseItemDetails": [
    {
      "caseItemType": "DISPUTE",
      "caseItemId": "999999999",
      "caseItemStatus": "PENDING",
      "caseItemStateCodeDescription": "QUESTIONNAIRE_COMPLETE",
      "reasonCode": "101",
      "reasonCodeDescription": "DEPOSIT NOT POSTED"
    },
    {
      "caseItemType": "DISPUTE",
      "caseItemId": "999999998",
      "caseItemStatus": "PENDING",
      "caseItemStateCodeDescription": "QUESTIONNAIRE_COMPLETE",
      "reasonCode": "101",
      "reasonCodeDescription": "DEPOSIT NOT POSTED"
    }
  ]
}
```

### Dispute Submit Questionnaire- Payment to Merchant- Non Fraud

Submits the questionnaire for a case item. Questionnaires belongs to Withdrawal- Non Fraud Flow

#### Request

**HTTP METHOD:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/dispute/v1/cases/999999999/questionnaire

```
{
    "caseItemIds": [
        "999999999"
    ],
    "questionnaire": [
        {
            "questionName": "QuestVar_CaseItem.Unauth_Participation",
            "questionValue": "Yes"
        },
        {
            "questionName": "QuestVar_CaseItem.DisputeCategory",
            "questionValue": "D" 
        },
        {
            "questionName": "QuestVar_CaseItem.SelectDisputeDetails",
            "questionValue": "A" 
        },
        {
            "questionName": "QuestVar_CaseItem.ChargesOnSameCard",
            "questionValue": "Yes"
        },
        {
            "questionName": "QuestVar_CaseItem.HotelRentalCarChrg",
            "questionValue": "Yes"
        },
        {
            "questionName": "QuestVar_CaseItem.FinalBill",
            "questionValue": "Yes"
        },
        {
            "questionName": "QuestVar_CaseItem.ChargeDescription",
            "questionValue": "Yes" 
        },
        {
            "questionName": "QuestVar_CaseItem.Auth_MerchantDesc",
            "questionValue": "for purchasing product"
        },
        {
            "questionName": "QuestVar_CaseItem.DateValidCharge",
            "questionValue": "04/10/2024"    
        },
        {
            "questionName": "QuestVar_CaseItem.AmountofValidCharge",
            "questionValue": "15"
        },
        {
            "questionName": "QuestVar_CaseItem.DisputePortion",
            "questionValue": "A" 
        },
        {
            "questionName": "QuestVar_CaseItem.MerchContactAttemptMer",
            "questionValue": "Yes"
        },
        {
            "questionName": "QuestVar_CaseItem.CaptureMerchResp",
            "questionValue": "Method - Email , Response - Try to resolve the issue at the earliest."    
        },
        {
            "questionName": "QuestVar_CaseItem.MerchantAttemptResolveDate",
            "questionValue": "01/14/2024"
        },
        {
            "questionName": "QuestVar_CaseItem.AdditionalInformation",
            "questionValue": "Yes"
        },
        {
            "questionName": "QuestVar_CaseItem.GeneralComments",
            "questionValue": "This is for testing Dispute Case"
        },
        {
            "questionName": "QuestVar_CaseItem.OralNotification",
            "questionValue": "No"
        }
    ]
}
```

#### Response

**HTTP Code:** 200 OK

```
{
  "caseId": "999999999",
  "caseItemDetails": [
    {
      "caseItemType": "DISPUTE",
      "caseItemId": "999999999",
      "caseItemStatus": "PENDING",
      "caseItemStateCodeDescription": "QUESTIONNAIRE_COMPLETE",
      "reasonCode": "137",
      "reasonCodeDescription": "CHARGED INCORRECT AMOUNT"
    }
  ]
}
```

### Dispute Submit Questionnaire- Fraud

Submits the questionnaire for a case item. Questionnaires belongs to Fraud Flow

#### Request

**HTTP METHOD:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/dispute/v1/cases/999999999/questionnaire

```
{
    "caseItemIds": [
        "999999999"
    ],
    "questionnaire": [
        {
            "questionName": "QuestVar_CaseItem.Unauth_Participation",
            "questionValue": "No"
        },
        {
            "questionName": "QuestVar_CaseItem.CardLostStolen",
            "questionValue": "Yes" 
        },
        {
            "questionName": "QuestVar_CaseItem.LostOrStolen",
            "questionValue": "A" 
        },
        {
            "questionName": "QuestVar_CaseItem.WhoUsedCard",
            "questionValue": "No"
        },
        {
            "questionName": "QuestVar_CaseItem.Unauth_AuthorizedUsers",
            "questionValue": "TEST"
        },
        {
            "questionName": " QuestVar_CaseItem.CardUsePermission",
            "questionValue": "Yes"
        },
        {  
            "questionName": " QuestVar_CaseItem.PINConsent",
            "questionValue": "No"
        },
        {
            "questionName": "QuestVar_CaseItem.AdditionalInformation",
            "questionValue": "Yes"
        },
        {
            "questionName": "QuestVar_CaseItem.GeneralComments",
            "questionValue": "This is for testing Dispute Case"
        },
        {
            "questionName": "QuestVar_CaseItem.OralNotification",
            "questionValue": "No"
        },
        {
            "questionName": "QuestVar_CaseItem.OralNotificationDate",
            "questionValue": "04/02/2024"
        }
    ]
}
```

#### Response

**HTTP Code:** 200 OK

```
{
  "caseId": "999999999",
  "caseItemDetails": [
    {
      "caseItemType": "FRAUD",
      "caseItemId": "999999999",
      "caseItemStatus": "PENDING",
      "caseItemStateCodeDescription": "QUESTIONNAIRE_COMPLETE",
      "reasonCode": "114",
      "reasonCodeDescription": "LOST"
    }
  ]
}
```

### Dispute Finalize case - Single Case Item

Finalize the case intake for a case.

#### Request

**HTTP METHOD:** PATCH

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/dispute/v1/cases/999999999/finalize

```
{
  "caseItemIds": [
    "999999999"
  ]
}
```

#### Response

**HTTP Code:** 200 OK

```
{
  "caseId": "999999999",
  "caseItemDetails": [
    {
      "caseItemId": "999999999",
      "caseItemStatus": "QUEUED",
      "caseItemStateCodeDescription": "QUESTIONNAIRE_COMPLETE"
    }
  ]
}
```

### Dispute Finalize case - Multi Case Item

Finalize the case intake for a case.

#### Request

**HTTP METHOD:** PATCH

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/dispute/v1/cases/999999999/finalize

```
{
  "caseItemIds": [
    "999999999",
    "999999998"
  ]
}
```

#### Response

**HTTP Code:** 200 OK

```
{
  "caseId": "999999999",
  "caseItemDetails": [
    {
      "caseItemId": "999999999",
      "caseItemStatus": "QUEUED",
      "caseItemStateCodeDescription": "QUESTIONNAIRE_COMPLETE"
    },
    {
      "caseItemId": "999999998",
      "caseItemStatus": "QUEUED",
      "caseItemStateCodeDescription": "QUESTIONNAIRE_COMPLETE"
    }
  ]
}
```
