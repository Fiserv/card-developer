# Test Cases

<span style="color:#ff6600;">**Card API Endpoints**</span>

When testing these endpoints, please use the test cases and test data from the Sandbox.

## Transactions

### Credit Transaction v3: Search using card number, date and detail filter

Retrieve transaction details of a given card based on the filter criteria passed.

**HTTP Method:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v3/cards/transactions/search?filter=detail

#### Request

```
{
     "cardNumber": "4000200030004001",
      "filterCriteria": [
          {
              "filterBy": "FROM_DATE",
              "filterValue": "2021-09-10"
          },
          {
              "filterBy": "TO_DATE",
              "filterValue": "2021-10-15"
          }
      ]
}
```

#### Response

**HTTP Code:** 200 OK

```
{
 "count": 1,
  "cardNumber": "400020XXXXXX4001",
  "nonTransToken": "pSAZIXCAXrAo4001",
  "transactions": [
    {
      "transactionSummary": {
        "authorizationCode": "000229",
        "responseCode": "912",
        "responseCodeDescription": "APPROVED - WITH BALANCES",
        "responseDetails": "51-B W/D purchase transfer",
        "status": "APPROVED",
        "tranCode": "012000",
        "tranId": "314003065381779",
        "transactionStatus": "APPROVED",
        "transactionType": "WITHDRAWAL",
        "creditOnly": {
          "effectiveDate": "04-OCT-2021 05:01:05 AM",
          "merchantCode": "6011",
          "messageId": "9906",
          "networkId": "0004"
        }
      },
      "transactionDetails": {
        "acquiringId": "11100170",
        "applicationTranCounter": "00AF",
        "cardAcceptorId": "CARD ACCEPTOR",
        "cardEntryMode": "Swiped/Machine read",
        "cavvResult": "V",
        "cvResult": "Passed",
        "cvvResult": "Pass",
        "enfactNearTimeScore": "0479",
        "enfactRealTimeDecision": "Approve",
        "enfactRealTimeScore": "0243",
        "enfactRecommendation": "approve",
        "expirationDate": "12/30",
        "messageReasonCode": "2104",
        "networkScore": "10",
        "ruleManagerRecommendation": "Pass",
        "ruleManagerRuleName": "FastReplyGlobalRule",
        "settlementCurrencyCode": "840",
        "stateCode": "NJ",
        "systemAuditNumber": "106308",
        "terminalCountryCode": "USA",
        "transactionBlockerResult": "2 - Successful",
        "creditOnly": {
          "acquiringCountryCode": "USA",
          "additionalData1": "D11101B99001",
          "additionalData2": "60905",
          "appInterchangeProfile": "11FF",
          "availableUsage": "72968.00",
          "avsOptionCode": "51",
          "avsPostalCode": "337131520",
          "cardAcceptorCity": "ROGERSVILLE",
          "cardAcceptorName": "Pax Technology I",
          "cardAcceptorTermId": "WD644000",
          "cardSequenceNumber": "",
          "cvcResultCode": false,
          "cvvCVVtwo": "110123",
          "fraudDecision": "decline",
          "originalResponseCode": "59",
          "pinVerified": true,
          "posCode": "006 - PRE-AUTHORIZED REQUEST",
          "posMode": "801",
          "referenceNumber": "109000254949",
          "reversalreason": "2523",
          "riskCodeOne": "15C2BT",
          "riskReasonCodeOne": "441LR",
          "riskScore": "878A1",
          "settlementAmount": "422.72",
          "settlementConversionRate": "808464432",
          "tagCode": "120W00203000",
          "tagData": "910",
          "tranAmtOriginal": "901.53",
          "tranFeeAmount": "20.00",
          "transmissionDateTime": "25-AUG-2023 11:41:21 AM",
          "postedTransactionDetails": {
            "authorizationCode": "000000",
            "cardholderAccountNumber": "443011000000018",
            "detailTransactionIdentifier": "000000000000000",
            "merchantCategoryCode": "00000",
            "merchantNumber": "443011000000398",
            "originalAuthAdjustmentAmount": "20.00",
            "postingDate": "2021-10-14",
            "promotionId": "11100171",
            "referenceNumber": "109000254949",
            "transactionAccountNumber": "443011000000018",
            "transactionCode": "CD",
            "transactionDescription": "MERCHANT ACCOUNT"
          }
        }
      }
    }
  ]
}
```

### Credit Transaction v3: Search using card number, date and summary filter

Retrieve transaction summary of a given card based on the filter criteria passed.

**HTTP Method:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v3/cards/transactions/search?filter=summary

#### Request

```
{
     "cardNumber": "4000200030004001",
      "filterCriteria": [
          {
              "filterBy": "FROM_DATE",
              "filterValue": "2021-09-10"
          },
          {
              "filterBy": "TO_DATE",
              "filterValue": "2021-10-14"
          }
      ]
}
```

#### Response

**HTTP Code:** 200 OK

```
{
   "count": 1,
    "cardNumber": "400020XXXXXX4001",
    "nonTransToken": "pSAZIXCAXrAo4001",
    "transactions": [
        {
         "transactionSummary": {
            "authorizationCode": "000229",
            "responseCode": "912",
            "responseCodeDescription": "APPROVED - WITH BALANCES",
            "responseDetails": "51-B W/D purchase transfer",
            "status": "APPROVED",
            "tranCode": "012000",
            "tranId": "314003065381779",
            "transactionStatus": "APPROVED",
            "transactionType": "WITHDRAWAL",
            "creditOnly": {
              "effectiveDate": "04-OCT-2021 05:01:05 AM",
              "merchantCode": "6011",
              "messageId": "9906",
              "networkId": "0004"
            }
         }
        }
    ]
}
```

### Credit Transaction v3: Search using card number, transaction code, summary filter

Retrieve transaction summary of a given card based on the filter criteria passed.

**HTTP Method:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v3/cards/transactions/search?filter=summary

#### Request

```
   "cardNumber": "4000200030004001",
    "filterCriteria": [
        {
            "filterBy": "TRANSACTION_CODE",
            "filterValue": "012000"
        }
    ]
}
```

#### Response

**HTTP Code:** 200 OK

```
{
    "count": 1,
    "cardNumber": "400020XXXXXX4001",
    "nonTransToken": "pSAZIXCAXrAo4001",
    "transactions": [
        {
         "transactionSummary": {
            "authorizationCode": "000229",
            "responseCode": "912",
            "responseCodeDescription": "APPROVED - WITH BALANCES",
            "responseDetails": "51-B W/D purchase transfer",
            "status": "APPROVED",
            "tranCode": "012000",
            "tranId": "314003065381779",
            "transactionStatus": "APPROVED",
            "transactionType": "WITHDRAWAL",
            "creditOnly": {
              "effectiveDate": "04-OCT-2021 05:01:05 AM",
              "merchantCode": "6011",
              "messageId": "9906",
              "networkId": "0004"
            }
         }
      ]
}
```

### Debit Transaction v3: Search using card number only, date and detail filter

Retrieve transaction details of a given card based on the filter criteria passed.

**HTTP Method:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v3/cards/transactions/search?filter=detail

#### Request

```
{
    "cardNumber": "4000200030004000",
    "filterCriteria": [
        {
            "filterBy": "FROM_DATE",
            "filterValue": "2021-09-10"
        },
        {
            "filterBy": "TO_DATE",
            "filterValue": "2021-10-24"
        }
    ]
}
```

#### Response

**HTTP Code:** 200 OK

```
{
 "count": 1,
  "cardNumber": "400020XXXXXX4000",
  "nonTransToken": "piUVBJKZGfks4000",
  "transactions": [
    {
      "transactionSummary": {
        "authorizationCode": "000229",
        "responseCode": "912",
        "responseCodeDescription": "APPROVED - WITH BALANCES",
        "responseDetails": "51-B W/D purchase transfer",
        "status": "APPROVED",
        "tranCode": "012000",
        "tranId": "314003065381779",
        "transactionStatus": "APPROVED",
        "transactionType": "WITHDRAWAL",
        "debitOnly": {
          "acquirerRefNum": "0000000000",
          "amtCharged": "6471902.00",
          "eciMastercard": "910",
          "eciVisa": "7",
          "expirationDateMismatch": false,
          "journalDateTime": "2023-07-20T13:38:53Z",
          "memberNumber": "0",
          "merchantCategoryCode": "6011",
          "merchantCity": "SAINT LOUIS",
          "merchantName": "FLORIDA MEDICAL",
          "merchantStateCode": "DC",
          "messageType": "210- Auth/Completion",
          "network": "000000 - Managed Service On US",
          "pinTransaction": "1 - Signature Network with PIN",
          "posDataInputCapability": "7 - Contactless chip",
          "posDataInputMode": "2 - Swipe",
          "preAuthAmt": "55.00",
          "retrievalRefNumber": "222815000031",
          "sequenceNumber": "000031",
          "sub#### ResponseCode": "D",
          "terminalId": "CATERMID",
          "transactionAmount": "158.41",
          "transactionDateTime": "2021-10-15T17:13:14Z",
          "transactionId": "{\"lifeCycleKey\":\"12323301232312331\",\"activeKey\":\"0210\",\"duID\":\"11348539120200526\"}",
          "unmatchedCompletionFlag": false
        }
      },
      "transactionDetails": {
        "acquiringId": "11100170",
        "applicationTranCounter": "00AF",
        "cardAcceptorId": "CARD ACCEPTOR",
        "cardEntryMode": "Swiped/Machine read",
        "cavvResult": "V",
        "cvResult": "Passed",
        "cvvResult": "Pass",
        "enfactNearTimeScore": "0479",
        "enfactRealTimeDecision": "Approve",
        "enfactRealTimeScore": "0243",
        "enfactRecommendation": "approve",
        "expirationDate": "12/30",
        "messageReasonCode": "2104",
        "networkScore": "10",
        "ruleManagerRecommendation": "Pass",
        "ruleManagerRuleName": "FastReplyGlobalRule",
        "settlementCurrencyCode": "840",
        "stateCode": "NJ",
        "systemAuditNumber": "106308",
        "terminalCountryCode": "USA",
        "transactionBlockerResult": "2 - Successful",
        "debitOnly": {
          "acqPostDate": "16-DEC-2023 12:00:00 AM",
          "atcResult": "Pass",
          "avsResult": "A",
          "camResult": "Valid",
          "cardCountryCode": "USA",
          "cardCounty": "840",
          "cardholderAddress": "98104    706 5TH AVE S",
          "cardLogo": "FOS3",
          "cashbackAmount": "40.00",
          "cvrResult": "03A01000",
          "cvrResultStat": "Pass",
          "cvv2Cvc2Result": true,
          "depositType": "Cash",
          "eCommerce": true,
          "emvApplicationId": "A0000000046000",
          "emvCard": true,
          "emvCardSequence": "004",
          "emvFallback": true,
          "emvTerminal": true,
          "entryMode": "5 - Chip",
          "fromAccount": "123456789",
          "fromAccountType": "Checking",
          "international": false,
          "locAmt1": "6.55",
          "locAmt2": "89.50",
          "merchantAdviceCode": "01",
          "merchantCountry": "USA",
          "merchantId": "STARBUCKS STORE",
          "mobileDenial": "05",
          "offline": true,
          "pinPresent": "1 - Signature Network with PIN",
          "pointOfService": "014 - GENERIC",
          "posDataCode": "52010120300C",
          "posEntryMode": "620",
          "productType": "ATM",
          "recurringPaymentInd": "R",
          "reversalCode": "10 - HARDWARE MALFUNCTION",
          "secureEci": "02 - 3-D Secure authentication attempt no resp",
          "surchargeAmount": "3.95",
          "surchargeReservalAmount": "2.50",
          "terminalLogo": "DSH4",
          "terminalPinCapable": false,
          "terminalStateCode": "NJ",
          "terminalStreet": "11806 SHELBYVILLE RD",
          "toAccount": "123456789",
          "toAccountType": "Checking",
          "tokenRequestorId": "50148904210",
          "tokenTransaction": false,
          "tokenType": "03",
          "transactionNetAmount": "111.96",
          "transactionSource": "E-COMMERCE",
          "tvrResult": "0400040001",
          "tvrResultStat": "Fail"
        }
      }
    }
  ]
}
```

### Debit Transaction v3: Search using card number, amount, summary filter

Retrieve transaction summary of a given card based on the filter criteria passed.

**HTTP Method:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v3/cards/transactions/search?filter=summary

#### Request

```
{
    "cardNumber": "4000200030004000",
    "memberNumber": "0",
    "filterCriteria": [
        {
            "filterBy": "AMOUNT_FROM",
            "filterValue": "0.00"
        },
        {
            "filterBy": "AMOUNT_TO",
            "filterValue": "200.00"
        }
    ]
}
```

#### Response

**HTTP Code:** 200 OK

```
{
  "count": 1,
    "cardNumber": "400020XXXXXX4000",
    "nonTransToken": "piUVBJKZGfks4000",
    "transactions": [
        {
          "transactionSummary": {
             "authorizationCode": "000229",
             "responseCode": "912",
             "responseCodeDescription": "APPROVED - WITH BALANCES",
             "responseDetails": "51-B W/D purchase transfer",
             "status": "APPROVED",
             "tranCode": "012000",
             "tranId": "314003065381779",
             "transactionStatus": "APPROVED",
             "transactionType": "WITHDRAWAL",
             "debitOnly": {
               "acquirerRefNum": "0000000000",
               "amtCharged": "6471902.00",
               "eciMastercard": "910",
               "eciVisa": "7",
               "expirationDateMismatch": false,
               "journalDateTime": "2023-07-20T13:38:53Z",
               "memberNumber": "0",
               "merchantCategoryCode": "6011",
               "merchantCity": "SAINT LOUIS",
               "merchantName": "FLORIDA MEDICAL",
               "merchantStateCode": "DC",
               "messageType": "210- Auth/Completion",
               "network": "000000 - Managed Service On US",
               "pinTransaction": "1 - Signature Network with PIN",
               "posDataInputCapability": "7 - Contactless chip",
               "posDataInputMode": "2 - Swipe",
               "preAuthAmt": "55.00",
               "retrievalRefNumber": "222815000031",
               "sequenceNumber": "000031",
               "subResponseCode": "D",
               "terminalId": "CATERMID",
               "transactionAmount": "158.41",
               "transactionDateTime": "2021-10-15T17:13:14Z",
               "transactionId": "{\"lifeCycleKey\":\"12323301232312331\",\"activeKey\":\"0210\",\"duID\":\"11348539120200526\"}",
               "unmatchedCompletionFlag": false
             }
           }
        }
    ]
}
```

### Debit Transaction v3: Search using card number, date and detail filter

Retrieve transaction details of a given card based on the filter criteria passed.

**HTTP METHOD:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v3/cards/transactions/search?filter=detail

#### Request

```
{
    "cardNumber": "4000200030004000",
    "memberNumber": "0",
    "filterCriteria": [
        {
            "filterBy": "FROM_DATE",
            "filterValue": "2021-09-10"
        },
        {
            "filterBy": "TO_DATE",
            "filterValue": "2021-10-24"
        }
    ]
}
```

#### Response

**HTTP Code:** 200 OK

```
{
  "count": 1,
  "cardNumber": "400020XXXXXX4000",
  "nonTransToken": "piUVBJKZGfks4000",
  "transactions": [
    {
      "transactionSummary": {
        "authorizationCode": "000229",
        "responseCode": "912",
        "responseCodeDescription": "APPROVED - WITH BALANCES",
        "responseDetails": "51-B W/D purchase transfer",
        "status": "APPROVED",
        "tranCode": "012000",
        "tranId": "314003065381779",
        "transactionStatus": "APPROVED",
        "transactionType": "WITHDRAWAL",
        "debitOnly": {
          "acquirerRefNum": "0000000000",
          "amtCharged": "6471902.00",
          "eciMastercard": "910",
          "eciVisa": "7",
          "expirationDateMismatch": false,
          "journalDateTime": "2023-07-20T13:38:53Z",
          "memberNumber": "0",
          "merchantCategoryCode": "6011",
          "merchantCity": "SAINT LOUIS",
          "merchantName": "FLORIDA MEDICAL",
          "merchantStateCode": "DC",
          "messageType": "210- Auth/Completion",
          "network": "000000 - Managed Service On US",
          "pinTransaction": "1 - Signature Network with PIN",
          "posDataInputCapability": "7 - Contactless chip",
          "posDataInputMode": "2 - Swipe",
          "preAuthAmt": "55.00",
          "retrievalRefNumber": "222815000031",
          "sequenceNumber": "000031",
          "subResponseCode": "D",
          "terminalId": "CATERMID",
          "transactionAmount": "158.41",
          "transactionDateTime": "2021-10-15T17:13:14Z",
          "transactionId": "{\"lifeCycleKey\":\"12323301232312331\",\"activeKey\":\"0210\",\"duID\":\"11348539120200526\"}",
          "unmatchedCompletionFlag": false
        }
      },
      "transactionDetails": {
        "acquiringId": "11100170",
        "applicationTranCounter": "00AF",
        "cardAcceptorId": "CARD ACCEPTOR",
        "cardEntryMode": "Swiped/Machine read",
        "cavvResult": "V",
        "cvResult": "Passed",
        "cvvResult": "Pass",
        "enfactNearTimeScore": "0479",
        "enfactRealTimeDecision": "Approve",
        "enfactRealTimeScore": "0243",
        "enfactRecommendation": "approve",
        "expirationDate": "12/30",
        "messageReasonCode": "2104",
        "networkScore": "10",
        "ruleManagerRecommendation": "Pass",
        "ruleManagerRuleName": "FastReplyGlobalRule",
        "settlementCurrencyCode": "840",
        "stateCode": "NJ",
        "systemAuditNumber": "106308",
        "terminalCountryCode": "USA",
        "transactionBlockerResult": "2 - Successful",
        "debitOnly": {
          "acqPostDate": "16-DEC-2023 12:00:00 AM",
          "atcResult": "Pass",
          "avsResult": "A",
          "camResult": "Valid",
          "cardCountryCode": "USA",
          "cardCounty": "840",
          "cardholderAddress": "98104    706 5TH AVE S",
          "cardLogo": "FOS3",
          "cashbackAmount": "40.00",
          "cvrResult": "03A01000",
          "cvrResultStat": "Pass",
          "cvv2Cvc2Result": true,
          "depositType": "Cash",
          "eCommerce": true,
          "emvApplicationId": "A0000000046000",
          "emvCard": true,
          "emvCardSequence": "004",
          "emvFallback": true,
          "emvTerminal": true,
          "entryMode": "5 - Chip",
          "fromAccount": "123456789",
          "fromAccountType": "Checking",
          "international": false,
          "locAmt1": "6.55",
          "locAmt2": "89.50",
          "merchantAdviceCode": "01",
          "merchantCountry": "USA",
          "merchantId": "STARBUCKS STORE",
          "mobileDenial": "05",
          "offline": true,
          "pinPresent": "1 - Signature Network with PIN",
          "pointOfService": "014 - GENERIC",
          "posDataCode": "52010120300C",
          "posEntryMode": "620",
          "productType": "ATM",
          "recurringPaymentInd": "R",
          "reversalCode": "10 - HARDWARE MALFUNCTION",
          "secureEci": "02 - 3-D Secure authentication attempt no resp",
          "surchargeAmount": "3.95",
          "surchargeReservalAmount": "2.50",
          "terminalLogo": "DSH4",
          "terminalPinCapable": false,
          "terminalStateCode": "NJ",
          "terminalStreet": "11806 SHELBYVILLE RD",
          "toAccount": "123456789",
          "toAccountType": "Checking",
          "tokenRequestorId": "50148904210",
          "tokenTransaction": false,
          "tokenType": "03",
          "transactionNetAmount": "111.96",
          "transactionSource": "E-COMMERCE",
          "tvrResult": "0400040001",
          "tvrResultStat": "Fail"
        }
      }
    }
  ]
}
```

### Debit Transaction v3: Search using NTT, merchant name, summary filter

Retrieve transaction summary of a given card based on the filter criteria passed.

**HTTP METHOD:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v3/cards/transactions/search?filter=summary

#### Request

```
{
     "nonTransToken": "piUVBJKZGfks4000",
    "filterCriteria": [
        {
            "filterBy": "MERCHANT_NAME",
            "filterValue": "FLORIDA MEDICAL"
        }
    ]
}
```

#### Response

**HTTP Code:** 200 OK

```
{
   "count": 1,
    "cardNumber": "400020XXXXXX4000",
    "nonTransToken": "piUVBJKZGfks4000",
    "transactions": [
        {
          "transactionSummary": {
             "authorizationCode": "000229",
             "responseCode": "912",
             "responseCodeDescription": "APPROVED - WITH BALANCES",
             "responseDetails": "51-B W/D purchase transfer",
             "status": "APPROVED",
             "tranCode": "012000",
             "tranId": "314003065381779",
             "transactionStatus": "APPROVED",
             "transactionType": "WITHDRAWAL",
             "debitOnly": {
               "acquirerRefNum": "0000000000",
               "amtCharged": "6471902.00",
               "eciMastercard": "910",
               "eciVisa": "7",
               "expirationDateMismatch": false,
               "journalDateTime": "2023-07-20T13:38:53Z",
               "memberNumber": "0",
               "merchantCategoryCode": "6011",
               "merchantCity": "SAINT LOUIS",
               "merchantName": "FLORIDA MEDICAL",
               "merchantStateCode": "DC",
               "messageType": "210- Auth/Completion",
               "network": "000000 - Managed Service On US",
               "pinTransaction": "1 - Signature Network with PIN",
               "posDataInputCapability": "7 - Contactless chip",
               "posDataInputMode": "2 - Swipe",
               "preAuthAmt": "55.00",
               "retrievalRefNumber": "222815000031",
               "sequenceNumber": "000031",
               "subResponseCode": "D",
               "terminalId": "CATERMID",
               "transactionAmount": "158.41",
               "transactionDateTime": "2021-10-15T17:13:14Z",
               "transactionId": "{\"lifeCycleKey\":\"12323301232312331\",\"activeKey\":\"0210\",\"duID\":\"11348539120200526\"}",
               "unmatchedCompletionFlag": false
             }
           }
        }
    ]
}
```

### Debit Transaction v3: Search using NTT, message type, summary filter

Retrieve transaction summary of a given card based on the filter criteria passed.

**HTTP METHOD:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v3/cards/transactions/search?filter=summary

#### Request

```
{
    "nonTransToken": "piUVBJKZGfks4000",
    "filterCriteria": [
        {
            "filterBy": "MESSAGE_TYPE",
            "filterValue": "210- Auth/Completion"
        }
    ]
}
```

#### Response

**HTTP Code:** 200 OK

```
{
    "nonTransToken": "piUVBJKZGfks4000",
    "filterCriteria": [
        {
            "filterBy": "MESSAGE_TYPE",
            "filterValue": "210- Auth/Completion"
        }
    ]
}
```

### Debit Transaction v3: Search using card number, NTT, date and summary filter

Retrieve transaction summary of a given card based on the filter criteria passed. Note: If both card number and NTT present in the request then priority is given to card number.

**HTTP METHOD:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v3/cards/transactions/search?filter=summary

#### Request

```
{
    "cardNumber": "4000200030004000",
    "nonTransToken": "piUVBJKZGfks4000",
    "memberNumber": "0",
    "filterCriteria": [
        {
            "filterBy": "FROM_DATE",
            "filterValue": "2021-09-10"
        },
        {
            "filterBy": "TO_DATE",
            "filterValue": "2021-10-24"
        }
    ]
}
```

#### Response

**HTTP Code:** 200 OK

```
{
   "count": 1,
   "cardNumber": "400020XXXXXX4000",
   "nonTransToken": "piUVBJKZGfks4000",
   "transactions": [
        {
          "transactionSummary": {
             "authorizationCode": "000229",
             "responseCode": "912",
             "responseCodeDescription": "APPROVED - WITH BALANCES",
             "responseDetails": "51-B W/D purchase transfer",
             "status": "APPROVED",
             "tranCode": "012000",
             "tranId": "314003065381779",
             "transactionStatus": "APPROVED",
             "transactionType": "WITHDRAWAL",
             "debitOnly": {
               "acquirerRefNum": "0000000000",
               "amtCharged": "6471902.00",
               "eciMastercard": "910",
               "eciVisa": "7",
               "expirationDateMismatch": false,
               "journalDateTime": "2023-07-20T13:38:53Z",
               "memberNumber": "0",
               "merchantCategoryCode": "6011",
               "merchantCity": "SAINT LOUIS",
               "merchantName": "FLORIDA MEDICAL",
               "merchantStateCode": "DC",
               "messageType": "210- Auth/Completion",
               "network": "000000 - Managed Service On US",
               "pinTransaction": "1 - Signature Network with PIN",
               "posDataInputCapability": "7 - Contactless chip",
               "posDataInputMode": "2 - Swipe",
               "preAuthAmt": "55.00",
               "retrievalRefNumber": "222815000031",
               "sequenceNumber": "000031",
               "subResponseCode": "D",
               "terminalId": "CATERMID",
               "transactionAmount": "158.41",
               "transactionDateTime": "2021-10-15T17:13:14Z",
               "transactionId": "{\"lifeCycleKey\":\"12323301232312331\",\"activeKey\":\"0210\",\"duID\":\"11348539120200526\"}",
               "unmatchedCompletionFlag": false
             }
           }
        }
    ]
}
```

### Debit Transaction v3: Search using card number, transaction code, summary filter

Retrieve transaction summary of a given card based on the filter criteria passed.

**HTTP METHOD:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v3/cards/transactions/search?filter=summary

#### Request

```
{
    "cardNumber": "4000200030004000",
    "memberNumber": "0",
    "filterCriteria": [
        {
            "filterBy": "TRANSACTION_CODE",
            "filterValue": "012000"
        }
    ]
}
```

#### Response

**HTTP Code:** 200 OK

```
{
    "count": 1,
    "cardNumber": "400020XXXXXX4000",
    "nonTransToken": "piUVBJKZGfks4000",
    "transactions": [
        {
          "transactionSummary": {
             "authorizationCode": "000229",
             "responseCode": "912",
             "responseCodeDescription": "APPROVED - WITH BALANCES",
             "responseDetails": "51-B W/D purchase transfer",
             "status": "APPROVED",
             "tranCode": "012000",
             "tranId": "314003065381779",
             "transactionStatus": "APPROVED",
             "transactionType": "WITHDRAWAL",
             "debitOnly": {
               "acquirerRefNum": "0000000000",
               "amtCharged": "6471902.00",
               "eciMastercard": "910",
               "eciVisa": "7",
               "expirationDateMismatch": false,
               "journalDateTime": "2023-07-20T13:38:53Z",
               "memberNumber": "0",
               "merchantCategoryCode": "6011",
               "merchantCity": "SAINT LOUIS",
               "merchantName": "FLORIDA MEDICAL",
               "merchantStateCode": "DC",
               "messageType": "210- Auth/Completion",
               "network": "000000 - Managed Service On US",
               "pinTransaction": "1 - Signature Network with PIN",
               "posDataInputCapability": "7 - Contactless chip",
               "posDataInputMode": "2 - Swipe",
               "preAuthAmt": "55.00",
               "retrievalRefNumber": "222815000031",
               "sequenceNumber": "000031",
               "subResponseCode": "D",
               "terminalId": "CATERMID",
               "transactionAmount": "158.41",
               "transactionDateTime": "2021-10-15T17:13:14Z",
               "transactionId": "{\"lifeCycleKey\":\"12323301232312331\",\"activeKey\":\"0210\",\"duID\":\"11348539120200526\"}",
               "unmatchedCompletionFlag": false
             }
           }
        }
    ]
}
```

### Debit Transaction v3: Search using NTT, date and detail filter

Retrieve transaction details of a given card based on the filter criteria passed.

**HTTP METHOD:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v3/cards/transactions/search?filter=detail

#### Request

```
{
   "nonTransToken": "piUVBJKZGfks4000",
    "filterCriteria": [
        {
            "filterBy": "FROM_DATE",
            "filterValue": "2021-09-10"
        },
        {
            "filterBy": "TO_DATE",
            "filterValue": "2021-10-24"
        }
    ]
}
```

#### Response

**HTTP Code:** 200 OK

```
{
    "count": 1,
  "cardNumber": "400020XXXXXX4000",
  "nonTransToken": "piUVBJKZGfks4000",
  "transactions": [
    {
      "transactionSummary": {
        "authorizationCode": "000229",
        "responseCode": "912",
        "responseCodeDescription": "APPROVED - WITH BALANCES",
        "responseDetails": "51-B W/D purchase transfer",
        "status": "APPROVED",
        "tranCode": "012000",
        "tranId": "314003065381779",
        "transactionStatus": "APPROVED",
        "transactionType": "WITHDRAWAL",
        "debitOnly": {
          "acquirerRefNum": "0000000000",
          "amtCharged": "6471902.00",
          "eciMastercard": "910",
          "eciVisa": "7",
          "expirationDateMismatch": false,
          "journalDateTime": "2023-07-20T13:38:53Z",
          "memberNumber": "0",
          "merchantCategoryCode": "6011",
          "merchantCity": "SAINT LOUIS",
          "merchantName": "FLORIDA MEDICAL",
          "merchantStateCode": "DC",
          "messageType": "210- Auth/Completion",
          "network": "000000 - Managed Service On US",
          "pinTransaction": "1 - Signature Network with PIN",
          "posDataInputCapability": "7 - Contactless chip",
          "posDataInputMode": "2 - Swipe",
          "preAuthAmt": "55.00",
          "retrievalRefNumber": "222815000031",
          "sequenceNumber": "000031",
          "subResponseCode": "D",
          "terminalId": "CATERMID",
          "transactionAmount": "158.41",
          "transactionDateTime": "2021-10-15T17:13:14Z",
          "transactionId": "{\"lifeCycleKey\":\"12323301232312331\",\"activeKey\":\"0210\",\"duID\":\"11348539120200526\"}",
          "unmatchedCompletionFlag": false
        }
      },
      "transactionDetails": {
        "acquiringId": "11100170",
        "applicationTranCounter": "00AF",
        "cardAcceptorId": "CARD ACCEPTOR",
        "cardEntryMode": "Swiped/Machine read",
        "cavvResult": "V",
        "cvResult": "Passed",
        "cvvResult": "Pass",
        "enfactNearTimeScore": "0479",
        "enfactRealTimeDecision": "Approve",
        "enfactRealTimeScore": "0243",
        "enfactRecommendation": "approve",
        "expirationDate": "12/30",
        "messageReasonCode": "2104",
        "networkScore": "10",
        "ruleManagerRecommendation": "Pass",
        "ruleManagerRuleName": "FastReplyGlobalRule",
        "settlementCurrencyCode": "840",
        "stateCode": "NJ",
        "systemAuditNumber": "106308",
        "terminalCountryCode": "USA",
        "transactionBlockerResult": "2 - Successful",
        "debitOnly": {
          "acqPostDate": "16-DEC-2023 12:00:00 AM",
          "atcResult": "Pass",
          "avsResult": "A",
          "camResult": "Valid",
          "cardCountryCode": "USA",
          "cardCounty": "840",
          "cardholderAddress": "98104    706 5TH AVE S",
          "cardLogo": "FOS3",
          "cashbackAmount": "40.00",
          "cvrResult": "03A01000",
          "cvrResultStat": "Pass",
          "cvv2Cvc2Result": true,
          "depositType": "Cash",
          "eCommerce": true,
          "emvApplicationId": "A0000000046000",
          "emvCard": true,
          "emvCardSequence": "004",
          "emvFallback": true,
          "emvTerminal": true,
          "entryMode": "5 - Chip",
          "fromAccount": "123456789",
          "fromAccountType": "Checking",
          "international": false,
          "locAmt1": "6.55",
          "locAmt2": "89.50",
          "merchantAdviceCode": "01",
          "merchantCountry": "USA",
          "merchantId": "STARBUCKS STORE",
          "mobileDenial": "05",
          "offline": true,
          "pinPresent": "1 - Signature Network with PIN",
          "pointOfService": "014 - GENERIC",
          "posDataCode": "52010120300C",
          "posEntryMode": "620",
          "productType": "ATM",
          "recurringPaymentInd": "R",
          "reversalCode": "10 - HARDWARE MALFUNCTION",
          "secureEci": "02 - 3-D Secure authentication attempt no resp",
          "surchargeAmount": "3.95",
          "surchargeReservalAmount": "2.50",
          "terminalLogo": "DSH4",
          "terminalPinCapable": false,
          "terminalStateCode": "NJ",
          "terminalStreet": "11806 SHELBYVILLE RD",
          "toAccount": "123456789",
          "toAccountType": "Checking",
          "tokenRequestorId": "50148904210",
          "tokenTransaction": false,
          "tokenType": "03",
          "transactionNetAmount": "111.96",
          "transactionSource": "E-COMMERCE",
          "tvrResult": "0400040001",
          "tvrResultStat": "Fail"
        }
      }
    }
  ]
}
```

### Debit Transaction v3: Search using NTT, date and summary filter

Retrieve transaction summary of a given card based on the filter criteria passed.

**HTTP METHOD:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v3/cards/transactions/search?filter=summary

#### Request

```
{
   "nonTransToken": "piUVBJKZGfks4000",
    "filterCriteria": [
        {
            "filterBy": "FROM_DATE",
            "filterValue": "2021-09-10"
        },
        {
            "filterBy": "TO_DATE",
            "filterValue": "2021-10-24"
        }
    ]
}
```

#### Response

**HTTP Code:** 200 OK

```
{
    "count": 1,
    "cardNumber": "400020XXXXXX4000",
    "nonTransToken": "piUVBJKZGfks4000",
    "transactions": [
        {
          "transactionSummary": {
             "authorizationCode": "000229",
             "responseCode": "912",
             "responseCodeDescription": "APPROVED - WITH BALANCES",
             "responseDetails": "51-B W/D purchase transfer",
             "status": "APPROVED",
             "tranCode": "012000",
             "tranId": "314003065381779",
             "transactionStatus": "APPROVED",
             "transactionType": "WITHDRAWAL",
             "debitOnly": {
               "acquirerRefNum": "0000000000",
               "amtCharged": "6471902.00",
               "eciMastercard": "910",
               "eciVisa": "7",
               "expirationDateMismatch": false,
               "journalDateTime": "2023-07-20T13:38:53Z",
               "memberNumber": "0",
               "merchantCategoryCode": "6011",
               "merchantCity": "SAINT LOUIS",
               "merchantName": "FLORIDA MEDICAL",
               "merchantStateCode": "DC",
               "messageType": "210- Auth/Completion",
               "network": "000000 - Managed Service On US",
               "pinTransaction": "1 - Signature Network with PIN",
               "posDataInputCapability": "7 - Contactless chip",
               "posDataInputMode": "2 - Swipe",
               "preAuthAmt": "55.00",
               "retrievalRefNumber": "222815000031",
               "sequenceNumber": "000031",
               "subResponseCode": "D",
               "terminalId": "CATERMID",
               "transactionAmount": "158.41",
               "transactionDateTime": "2021-10-15T17:13:14Z",
               "transactionId": "{\"lifeCycleKey\":\"12323301232312331\",\"activeKey\":\"0210\",\"duID\":\"11348539120200526\"}",
               "unmatchedCompletionFlag": false
             }
           }
        }
    ]
}
```

### Debit Transaction v3: Search using card number, sequence number, retrieval number and detail filter

Retrieve transaction detail of a given card based on the filter criteria passed.

**HTTP METHOD:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v3/cards/transactions/search?filter=detail

#### Request

```
{
    "cardNumber": "4000200030004000",
    "memberNumber": "0",
    "filterCriteria": [
        {
            "filterBy": "SEQUENCE_NUMBER",
            "filterValue": "000031"
        },
        {
            "filterBy": "RETRIEVAL_REF_NUMBER",
            "filterValue": "222815000031"
        }
    ]
}
```

#### Response

**HTTP Code:** 200 OK

```
{
    "count": 1,
  "cardNumber": "400020XXXXXX4000",
  "nonTransToken": "piUVBJKZGfks4000",
  "transactions": [
    {
      "transactionSummary": {
        "authorizationCode": "000229",
        "responseCode": "912",
        "responseCodeDescription": "APPROVED - WITH BALANCES",
        "responseDetails": "51-B W/D purchase transfer",
        "status": "APPROVED",
        "tranCode": "012000",
        "tranId": "314003065381779",
        "transactionStatus": "APPROVED",
        "transactionType": "WITHDRAWAL",
        "debitOnly": {
          "acquirerRefNum": "0000000000",
          "amtCharged": "6471902.00",
          "eciMastercard": "910",
          "eciVisa": "7",
          "expirationDateMismatch": false,
          "journalDateTime": "2023-07-20T13:38:53Z",
          "memberNumber": "0",
          "merchantCategoryCode": "6011",
          "merchantCity": "SAINT LOUIS",
          "merchantName": "FLORIDA MEDICAL",
          "merchantStateCode": "DC",
          "messageType": "210- Auth/Completion",
          "network": "000000 - Managed Service On US",
          "pinTransaction": "1 - Signature Network with PIN",
          "posDataInputCapability": "7 - Contactless chip",
          "posDataInputMode": "2 - Swipe",
          "preAuthAmt": "55.00",
          "retrievalRefNumber": "222815000031",
          "sequenceNumber": "000031",
          "subResponseCode": "D",
          "terminalId": "CATERMID",
          "transactionAmount": "158.41",
          "transactionDateTime": "2021-10-15T17:13:14Z",
          "transactionId": "{\"lifeCycleKey\":\"12323301232312331\",\"activeKey\":\"0210\",\"duID\":\"11348539120200526\"}",
          "unmatchedCompletionFlag": false
        }
      },
      "transactionDetails": {
        "acquiringId": "11100170",
        "applicationTranCounter": "00AF",
        "cardAcceptorId": "CARD ACCEPTOR",
        "cardEntryMode": "Swiped/Machine read",
        "cavvResult": "V",
        "cvResult": "Passed",
        "cvvResult": "Pass",
        "enfactNearTimeScore": "0479",
        "enfactRealTimeDecision": "Approve",
        "enfactRealTimeScore": "0243",
        "enfactRecommendation": "approve",
        "expirationDate": "12/30",
        "messageReasonCode": "2104",
        "networkScore": "10",
        "ruleManagerRecommendation": "Pass",
        "ruleManagerRuleName": "FastReplyGlobalRule",
        "settlementCurrencyCode": "840",
        "stateCode": "NJ",
        "systemAuditNumber": "106308",
        "terminalCountryCode": "USA",
        "transactionBlockerResult": "2 - Successful",
        "debitOnly": {
          "acqPostDate": "16-DEC-2023 12:00:00 AM",
          "atcResult": "Pass",
          "avsResult": "A",
          "camResult": "Valid",
          "cardCountryCode": "USA",
          "cardCounty": "840",
          "cardholderAddress": "98104    706 5TH AVE S",
          "cardLogo": "FOS3",
          "cashbackAmount": "40.00",
          "cvrResult": "03A01000",
          "cvrResultStat": "Pass",
          "cvv2Cvc2Result": true,
          "depositType": "Cash",
          "eCommerce": true,
          "emvApplicationId": "A0000000046000",
          "emvCard": true,
          "emvCardSequence": "004",
          "emvFallback": true,
          "emvTerminal": true,
          "entryMode": "5 - Chip",
          "fromAccount": "123456789",
          "fromAccountType": "Checking",
          "international": false,
          "locAmt1": "6.55",
          "locAmt2": "89.50",
          "merchantAdviceCode": "01",
          "merchantCountry": "USA",
          "merchantId": "STARBUCKS STORE",
          "mobileDenial": "05",
          "offline": true,
          "pinPresent": "1 - Signature Network with PIN",
          "pointOfService": "014 - GENERIC",
          "posDataCode": "52010120300C",
          "posEntryMode": "620",
          "productType": "ATM",
          "recurringPaymentInd": "R",
          "reversalCode": "10 - HARDWARE MALFUNCTION",
          "secureEci": "02 - 3-D Secure authentication attempt no resp",
          "surchargeAmount": "3.95",
          "surchargeReservalAmount": "2.50",
          "terminalLogo": "DSH4",
          "terminalPinCapable": false,
          "terminalStateCode": "NJ",
          "terminalStreet": "11806 SHELBYVILLE RD",
          "toAccount": "123456789",
          "toAccountType": "Checking",
          "tokenRequestorId": "50148904210",
          "tokenTransaction": false,
          "tokenType": "03",
          "transactionNetAmount": "111.96",
          "transactionSource": "E-COMMERCE",
          "tvrResult": "0400040001",
          "tvrResultStat": "Fail"
        }
      }
    }
    ]
}
```

### Debit Transaction v3: Search using card number, sequence number, retrieval number and summary filter

Retrieve transaction detail of a given card based on the filter criteria passed.

**HTTP METHOD:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v3/cards/transactions/search?filter=summary

#### Request

```
{
    "cardNumber": "4000200030004000",
    "memberNumber": "0",
    "filterCriteria": [
        {
            "filterBy": "SEQUENCE_NUMBER",
            "filterValue": "000031"
        },
        {
            "filterBy": "RETRIEVAL_REF_NUMBER",
            "filterValue": "222815000031"
        }
    ]
}
```

#### Response

**HTTP Code:** 200 OK

```
{
    "count": 1,
    "cardNumber": "400020XXXXXX4000",
    "nonTransToken": "piUVBJKZGfks4000",
    "transactions": [
        {
          "transactionSummary": {
             "authorizationCode": "000229",
             "responseCode": "912",
             "responseCodeDescription": "APPROVED - WITH BALANCES",
             "responseDetails": "51-B W/D purchase transfer",
             "status": "APPROVED",
             "tranCode": "012000",
             "tranId": "314003065381779",
             "transactionStatus": "APPROVED",
             "transactionType": "WITHDRAWAL",
             "debitOnly": {
               "acquirerRefNum": "0000000000",
               "amtCharged": "6471902.00",
               "eciMastercard": "910",
               "eciVisa": "7",
               "expirationDateMismatch": false,
               "journalDateTime": "2023-07-20T13:38:53Z",
               "memberNumber": "0",
               "merchantCategoryCode": "6011",
               "merchantCity": "SAINT LOUIS",
               "merchantName": "FLORIDA MEDICAL",
               "merchantStateCode": "DC",
               "messageType": "210- Auth/Completion",
               "network": "000000 - Managed Service On US",
               "pinTransaction": "1 - Signature Network with PIN",
               "posDataInputCapability": "7 - Contactless chip",
               "posDataInputMode": "2 - Swipe",
               "preAuthAmt": "55.00",
               "retrievalRefNumber": "222815000031",
               "sequenceNumber": "000031",
               "subResponseCode": "D",
               "terminalId": "CATERMID",
               "transactionAmount": "158.41",
               "transactionDateTime": "2021-10-15T17:13:14Z",
               "transactionId": "{\"lifeCycleKey\":\"12323301232312331\",\"activeKey\":\"0210\",\"duID\":\"11348539120200526\"}",
               "unmatchedCompletionFlag": false
             }
           }
        }
    ]
}
```

### Debit Terminal Transaction v1: Search using status

Retrieve a list of transactions for the terminal ID based on the filter criteria given.

**HTTP METHOD:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v1/cards/terminalTransactions/search

#### Request

```
{
      "terminalId": "CATERMID",
      "filterCriteria": [
          {
              "filterBy": "STATUS",
              "filterValue": "Approved"
          }
      ]
}
```

#### Response

**HTTP Code:** 200 OK

```
{
      "count": 2,
      "transactions": [
          {
              "systemRecordId": "011103LMFI4F4321377761184|12080251120230113|0120",
              "cardNumber": "400020XXXXXX4000",
              "memberNumber": "1",
              "sequenceNumber": "003503",
              "subResponseCode": "K",
              "subResponseCodeDescription": "57-k Blocked for country code",
              "preAuthAmt": "1.00",
              "amtCharged": "0.00",
              "authorizationCode": "600636",
              "terminalId": "CATERMID",
              "merchantCategoryCode": "4112",
              "merchantCity": "Morris Plains",
              "merchantState": "NJ",
              "eciMastercard": "3",
              "eciVisa": "3",
              "pinTransaction": "1 - Yes",
              "networkID": "773002 - Maestro",
              "acquirerRefNum": "1055556060",
              "posDataInputCapability": "2",
              "posDataInputMode": "2 - Swipe",
              "unmatchedCompletionFlag": "N",
              "expirationDateMismatch": "N",
              "transactionDateTime": "2021-12-29T16:37:51Z",
              "merchantName": "HT02",
              "transactionAmount": "1.00",
              "transactionType": "PAYMENT TO MERCHANT",
              "messageType": "210 - Auth/Completion",
              "transactionStatus": "APPROVED",
              "responseCode": "00",
              "responseCodeDescription": "APPROVED - NO BALANCES",
              "terminalFILogo": "RM22",
              "cardFILogo": "V924",
              "terminalPinCapable": "No",
              "merchantCountry": "USA"
          },
          {
              "systemRecordId": "011103LMFI4F4321377761184|12080251120230113|0120",
              "cardNumber": "400020XXXXXX4000",
              "memberNumber": "1",
              "sequenceNumber": "003487",
              "subResponseCode": "K",
              "subResponseCodeDescription": "57-k Blocked for country code",
              "preAuthAmt": "1.00",
              "amtCharged": "0.00",
              "authorizationCode": "600636",
              "terminalId": "CATERMID",
              "merchantCategoryCode": "4112",
              "merchantCity": "Morris Plains",
              "merchantState": "NJ",
              "eciMastercard": "3",
              "eciVisa": "3",
              "pinTransaction": "1 - Yes",
              "networkID": "773002 - Maestro",
              "acquirerRefNum": "1055556060",
              "posDataInputCapability": "2",
              "posDataInputMode": "2 - Swipe",
              "unmatchedCompletionFlag": "N",
              "expirationDateMismatch": "N",
              "transactionDateTime": "2021-12-29T14:06:04Z",
              "merchantName": "HT02",
              "transactionAmount": "1.00",
              "transactionType": "PAYMENT TO MERCHANT",
              "messageType": "210 - Auth/Completion",
              "transactionStatus": "APPROVED",
              "responseCode": "00",
              "responseCodeDescription": "APPROVED - NO BALANCES",
              "terminalFILogo": "RM22",
              "cardFILogo": "V924",
              "terminalPinCapable": "No",
              "merchantCountry": "USA"
          }
      ]
}
```

### Debit Terminal Transaction v1: Search using terminal FI logo

Retrieve a list of transactions for the terminal ID based on the filter criteria given.

**HTTP METHOD:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v1/cards/terminalTransactions/search

#### Request

```
{
      "terminalId": "CATERMID",
      "filterCriteria": [
          {
              "filterBy": "TERMINALFILOGO",
              "filterValue": "RM22"
          }
      ]
}
```

#### Response

**HTTP Code:** 200 OK

```
{
      "count": 1,
      "transactions": [
          {
              "systemRecordId": "40002075TCXT0001611881614|12080251120230113|0120",
              "cardNumber": "400020XXXXXX4000",
              "memberNumber": "0",
              "sequenceNumber": "007336",
              "subResponseCode": "0",
              "subResponseCodeDescription": "03-0 Approved with Balances",
              "preAuthAmt": "73.00",
              "amtCharged": "73",
              "authorizationCode": "010184",
              "terminalId": "CATERMID",
              "merchantCategoryCode": "6011",
              "merchantCity": "BERKELEY HEIGHTS",
              "merchantState": "NJ",
              "eciMastercard": "210",
              "eciVisa": "6",
              "pinTransaction": "4 - Yes",
              "networkID": "734004 - Plus VisaNet",
              "acquirerRefNum": "0000000000",
              "posDataInputCapability": "5",
              "posDataInputMode": "5 - Chip",
              "unmatchedCompletionFlag": "N",
              "expirationDateMismatch": "N",
              "transactionDateTime": "2021-12-29T16:37:51Z",
              "merchantName": "TEST BANK",
              "transactionAmount": "73.00",
              "transactionType": "WITHDRAWAL FROM CHECKING",
              "messageType": "210 - Auth/Completion",
              "transactionStatus": "APPROVED",
              "responseCode": "03",
              "responseCodeDescription": "APPROVED - BOTH BALANCES PROVIDED",
              "terminalFILogo": "RM22",
              "cardFILogo": "V924",
              "terminalPinCapable": "5",
              "merchantCountry": "USA"
          }
      ]
}
```
