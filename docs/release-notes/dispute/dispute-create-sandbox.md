# Test Cases

<span style="color:#ff6600;">**Dispute API Endpoints**</span>

## Dispute create
**Version 3**

### Create claim V3: Single transaction ID
Creates a dispute case for given transactions of a particular card number.

#### Request
**HTTP METHOD:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/dispute/v3/cases/claim

```
{
  "cardNumber": "4000200030004000",
  "listOfTransactions": [
    {
      "transactionId": "{\"lifeCycleKey\":\"12323301232312331\",\"activeKey\":\"0210\",\"duID\":\"11348539120200526\"}"
    }
  ]
}
```
#### Response
**HTTP Code:** 200 OK

```
{
  "caseId": "999999999",
  "referenceId": "serv.net:___212344MBVKXK4K:0103b250-a424-4cd7-bfaa-807f0ff79d23",
  "caseItemIds": [
    "transactionID[{\"lifeCycleKey\":\"12323301232312331\",\"activeKey\":\"0210\",\"duID\":\"11348539120200526\"}]:caseItemId[999999999]"
  ]
}
```

### Create claim V3: Multiple transaction IDs
Creates a dispute case for given transactions of a particular card number.

#### Request
**HTTP METHOD:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/dispute/v3/cases/claim


```
{
  "cardNumber": "4000200030004000",
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
    "referenceId": "serv.net:___212344MBVKXK4K:0103b250-a424-4cd7-bfaa-807f0ff79d23",
    "caseItemIds": [
        "transactionID[{\"lifeCycleKey\":\"12323301232312331\",\"activeKey\":\"0210\",\"duID\":\"11348539120200526\"}]:caseItemId[999999999]",
        "transactionID[{\"lifeCycleKey\":\"12323301232312331\",\"activeKey\":\"0210\",\"duID\":\"11348539120200527\"}]:caseItemId[999999998]"
    ]
}
```
### Create claim V3: Partial scenario
Creates a dispute case for given transactions of a particular card number.

#### Request
**HTTP METHOD:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/dispute/v3/cases/claim


```
{
    "cardNumber": "4000200030004000",
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
    "referenceId": "serv.net:___212344MBVKXK4K:0103b250-a424-4cd7-bfaa-807f0ff79d23",
    "caseItemIds": [
        "transactionID[{\"lifeCycleKey\":\"12323301232312331\",\"activeKey\":\"0210\",\"duID\":\"11348539120200526\"}]:caseItemId[999999999]",
        "transactionID[{\"lifeCycleKey\":\"12323301232312331\",\"activeKey\":\"0210\",\"duID\":\"11348539120200527\"}]:caseItemId[999999998]"
    ],
    "warningInfo": {
        "message": "Draft caseitem could not be created for some of the transactionId(s)",
        "warningDetails": [
            {
                "code": "321",
                "detail": "INFO: [3] transactionId - That transaction is already in use by 999999997.",
                "spanId": "b4a6e572-dbf3-4edb-9cb4-ea295d504aa2",
                "timestamp": "2023-01-09T13:40:43.087Z"
            }
        ]
    },
    "instance": "/api/basepath",
    "status": "206"
}
```

 
### Questionnaire withdrawal nonfraud
Submits a questionnaire for a case item. Questionnaires belongs in the Withdrawal-Nonfraud Flow.

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
  "referenceId": "serv.net:___212344MBVKXK4K:0103b250-a424-4cd7-bfaa-807f0ff79d23",
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
###  Questionnaire deposit nonfraud: Multi caseItem
Submits the questionnaire for a case item. Questionnaires belongs to Deposit- Nonfraud Flow for Multi-case Items.

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
        }    "caseItemIds": [
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
  "referenceId": "serv.net:___212344MBVKXK4K:0103b250-a424-4cd7-bfaa-807f0ff79d23",
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
### Questionnaire payment merchant: Nonfraud
Submits the questionnaire for a case item. Questionnaires belongs to Withdrawal- Nonfraud Flow.

#### Request
**HTTP METHOD:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/dispute/v1/cases/999999999/questionnaire
```
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
 "referenceId": "serv.net:___212344MBVKXK4K:0103b250-a424-4cd7-bfaa-807f0ff79d23",
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


### Questionnaire fraud
Submits a questionnaire for a case item. Questionnaires belongs in the Fraud Flow.

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
  "referenceId": "serv.net:___212344MBVKXK4K:0103b250-a424-4cd7-bfaa-807f0ff79d23",
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

### Finalize case: Single case item
Finalize  intake for a case item.

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
  "referenceId": "serv.net:___212344MBVKXK4K:0103b250-a424-4cd7-bfaa-807f0ff79d23",
  "caseItemDetails": [
    {
      "caseItemId": "999999999",
      "caseItemStatus": "QUEUED",
      "caseItemStateCodeDescription": "QUESTIONNAIRE_COMPLETE"
    }
  ]
}
```


### Finalize case: Multi case item
Finalize intake for a  case with multple caseItemIds.

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
 "referenceId": "serv.net:___212344MBVKXK4K:0103b250-a424-4cd7-bfaa-807f0ff79d23",
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
