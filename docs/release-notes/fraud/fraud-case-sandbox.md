# Test Cases

<span style="color:#ff6600;">**Fraud API Endpoints**</span>

When testing these endpoints, please use the test cases and test data from the Sandbox.

## Case

### Fraud Case v1: Search using date range

Search for fraud cases based on request criteria(fromDateTime and toDateTime).

#### Request

**HTTP Method:** POST

**Target URL:**  https://card-sandbox.api.fiservapps.com/cs/fraud/v1/cases/search

```
{
   "fromDateTime": "2021-07-20T07:00:00Z",
   "toDateTime": "2021-07-20T07:00:00Z"
}
```

#### Response

**HTTP Code:** 200 OK

```
{
   "caseSearchResults": [
      {
         "logo": "APIP",
         "cardNumber": "400020XXXXXX4000",
         "caseNumber": "999999999",
         "caseTenant": "60",
         "caseCreatedDateTime": "2021-07-20T07:00:00Z",
         "caseStatus": "OPEN",
         "name": "Alex Smith",
         "caseClosedDateTime": "2021-07-21T07:00:00Z",
         "archived": "No",
         "baseCreateScore": "0",
         "baseHighScore": "430",
         "taxId1": "1234",
         "taxId2": "1234",
         "homePhone": "1005550001",
         "secondaryPhone": "1005550001",
         "workPhone": "1005550001",
         "cellPhone": "1005550001",
         "addressLine1": "123 Any Street",
         "addressLine2": "123 Any Lane",
         "city": "New Jersey",
         "state": "NJ",
         "postalCode": "12345",
         "actionStrategy": "A1",
         "adaptiveCreateScore": "0",
         "adaptiveHighScore": "430",
         "primaryBirthDate": "1990-08-24",
         "otherBirthDate": "1990-08-24",
         "cardStatusAtCaseCreate": "Active",
         "cardTrackerSeverity": "5",
         "fraudApproach": "Minimum",
         "memberNumber": "0",
         "highTransactionDateTime": "2021-07-20T07:00:00Z",
         "lastAnalyst": "Analyst",
         "lastFraudCode": "CASE_FRAUD_TYPE_APP_FRD",
         "lastName": "Smith",
         "lastScore": "0",
         "lastTransactionDateTime": "2021-07-20T07:00:00Z",
         "OriginalAnalyst": "Analyst",
         "scoreToUse": "Base",
         "rules": "RuleManager Case Create"
      },
      {
         "logo": "APIP",
         "cardNumber": "400020XXXXXX4000",
         "caseNumber": "888888888",
         "caseCreatedDateTime": "2021-07-20T07:00:00Z",
         "caseStatus": "OPEN",
         "name": "Alex Smith",
         "caseClosedDateTime": "2021-07-21T07:00:00Z",
         "archived": "No",
         "baseCreateScore": "0",
         "baseHighScore": "430",
         "taxId1": "1234",
         "taxId2": "1234",
         "homePhone": "1005550001",
         "secondaryPhone": "1005550001",
         "workPhone": "1005550001",
         "cellPhone": "1005550001",
         "addressLine1": "123 Any Street",
         "addressLine2": "123 Any Lane",
         "city": "New Jersey",
         "state": "NJ",
         "postalCode": "12345",
         "actionStrategy": "A1",
         "adaptiveCreateScore": "0",
         "adaptiveHighScore": "430",
         "primaryBirthDate": "1990-08-24",
         "otherBirthDate": "1990-08-24",
         "cardStatusAtCaseCreate": "Active",
         "cardTrackerSeverity": "5",
         "fraudApproach": "Minimum",
         "memberNumber": "0",
         "highTransactionDateTime": "2021-07-20T07:00:00Z",
         "lastAnalyst": "Analyst",
         "lastFraudCode": "CASE_FRAUD_TYPE_APP_FRD",
         "lastName": "Smith",
         "lastScore": "0",
         "lastTransactionDateTime": "2021-07-20T07:00:00Z",
         "OriginalAnalyst": "Analyst",
         "scoreToUse": "Base",
         "rules": "RuleManager Case Create"
      }
   ]
}
```

### Fraud Case v1: Search using date range and card number

Search for fraud cases based on required fields fromDateTime and toDateTime and optional field cardNumber.

#### Request

**HTTP Method:** POST

**Target URL:**  https://card-sandbox.api.fiservapps.com/cs/fraud/v1/cases/search

```
{
   "fromDateTime": "2021-07-20T07:00:00Z",
   "toDateTime": "2021-07-20T07:00:00Z",
   "cardNumber": "4000200030004000"
}
```

#### Response

**HTTP Code:** 200 OK

```
{
   "caseSearchResults": [
      {
         "logo": "APIP",
         "cardNumber": "400020XXXXXX4000",
         "caseNumber": "999999999",
         "caseTenant": "60",
         "caseCreatedDateTime": "2021-07-20T07:00:00Z",
         "caseStatus": "OPEN",
         "name": "Alex Smith",
         "caseClosedDateTime": "2021-07-21T07:00:00Z",
         "archived": "No",
         "baseCreateScore": "0",
         "baseHighScore": "430",
         "taxId1": "1234",
         "taxId2": "1234",
         "homePhone": "1005550001",
         "secondaryPhone": "1005550001",
         "workPhone": "1005550001",
         "cellPhone": "1005550001",
         "addressLine1": "123 Any Street",
         "addressLine2": "123 Any Lane",
         "city": "New Jersey",
         "state": "NJ",
         "postalCode": "12345",
         "actionStrategy": "A1",
         "adaptiveCreateScore": "0",
         "adaptiveHighScore": "430",
         "primaryBirthDate": "1990-08-24",
         "otherBirthDate": "1990-08-24",
         "cardStatusAtCaseCreate": "Active",
         "cardTrackerSeverity": "5",
         "fraudApproach": "Minimum",
         "memberNumber": "0",
         "highTransactionDateTime": "2021-07-20T07:00:00Z",
         "lastAnalyst": "Analyst",
         "lastFraudCode": "CASE_FRAUD_TYPE_APP_FRD",
         "lastName": "Smith",
         "lastScore": "0",
         "lastTransactionDateTime": "2021-07-20T07:00:00Z",
         "OriginalAnalyst": "Analyst",
         "scoreToUse": "Base",
         "rules": "RuleManager Case Create"
      },
      {
         "logo": "APIP",
         "cardNumber": "400020XXXXXX4000",
         "caseNumber": "888888888",
         "caseCreatedDateTime": "2021-07-20T07:00:00Z",
         "caseStatus": "OPEN",
         "name": "Alex Smith",
         "caseClosedDateTime": "2021-07-21T07:00:00Z",
         "archived": "No",
         "baseCreateScore": "0",
         "baseHighScore": "430",
         "taxId1": "1234",
         "taxId2": "1234",
         "homePhone": "1005550001",
         "secondaryPhone": "1005550001",
         "workPhone": "1005550001",
         "cellPhone": "1005550001",
         "addressLine1": "123 Any Street",
         "addressLine2": "123 Any Lane",
         "city": "New Jersey",
         "state": "NJ",
         "postalCode": "12345",
         "actionStrategy": "A1",
         "adaptiveCreateScore": "0",
         "adaptiveHighScore": "430",
         "primaryBirthDate": "1990-08-24",
         "otherBirthDate": "1990-08-24",
         "cardStatusAtCaseCreate": "Active",
         "cardTrackerSeverity": "5",
         "fraudApproach": "Minimum",
         "memberNumber": "0",
         "highTransactionDateTime": "2021-07-20T07:00:00Z",
         "lastAnalyst": "Analyst",
         "lastFraudCode": "CASE_FRAUD_TYPE_APP_FRD",
         "lastName": "Smith",
         "lastScore": "0",
         "lastTransactionDateTime": "2021-07-20T07:00:00Z",
         "OriginalAnalyst": "Analyst",
         "scoreToUse": "Base",
         "rules": "RuleManager Case Create"
      }
   ]
}
```

### Fraud Case v1: Search using date range and case number

Search for fraud cases based on request criteria fromDateTime, toDateTime and caseNumber.

#### Request

**HTTP Method:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/fraud/v1/cases/search

```
{
   "fromDateTime": "2021-07-20T07:00:00Z",
   "toDateTime": "2021-07-20T07:00:00Z",
   "caseNumber": "999999999"
}
```

#### Response

**HTTP Code:** 200 OK

```
{
   "caseSearchResults": [
      {
         "logo": "APIP",
         "cardNumber": "400020XXXXXX4000",
         "caseNumber": "999999999",
         "caseTenant": "60",
         "caseCreatedDateTime": "2021-07-20T07:00:00Z",
         "caseStatus": "OPEN",
         "name": "Alex Smith",
         "caseClosedDateTime": "2021-07-21T07:00:00Z",
         "archived": "No",
         "baseCreateScore": "0",
         "baseHighScore": "430",
         "taxId1": "1234",
         "taxId2": "1234",
         "homePhone": "1005550001",
         "secondaryPhone": "1005550001",
         "workPhone": "1005550001",
         "cellPhone": "1005550001",
         "addressLine1": "123 Any Street",
         "addressLine2": "123 Any Lane",
         "city": "New Jersey",
         "state": "NJ",
         "postalCode": "12345",
         "actionStrategy": "A1",
         "adaptiveCreateScore": "0",
         "adaptiveHighScore": "430",
         "primaryBirthDate": "1990-08-24",
         "otherBirthDate": "1990-08-24",
         "cardStatusAtCaseCreate": "Active",
         "cardTrackerSeverity": "5",
         "fraudApproach": "Minimum",
         "memberNumber": "0",
         "highTransactionDateTime": "2021-07-20T07:00:00Z",
         "lastAnalyst": "Analyst",
         "lastFraudCode": "CASE_FRAUD_TYPE_APP_FRD",
         "lastName": "Smith",
         "lastScore": "0",
         "lastTransactionDateTime": "2021-07-20T07:00:00Z",
         "OriginalAnalyst": "Analyst",
         "scoreToUse": "Base",
         "rules": "RuleManager Case Create"
      }
   ]
}
```

### Fraud Case v1: Search using date range, last name, phone number and postal code

Search for fraud cases based on fromDateTime and todateTime,lastName, phone and postalCode fields.

#### Request

**HTTP Method:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/fraud/v1/cases/search

```
{
   "fromDateTime": "2021-07-20T07:00:00Z",
   "toDateTime": "2021-07-20T07:00:00Z",
   "lastName": "Smith",
   "phoneNumber": "1005550001",
   "postalCode": "12345"
}
```

#### Response

**HTTP Code:** 200 OK

```
{
   "caseSearchResults": [
      {
         "logo": "APIP",
         "cardNumber": "400020XXXXXX4000",
         "caseNumber": "999999999",
         "caseTenant": "60",
         "caseCreatedDateTime": "2021-07-20T07:00:00Z",
         "caseStatus": "OPEN",
         "name": "Alex Smith",
         "caseClosedDateTime": "2021-07-21T07:00:00Z",
         "archived": "No",
         "baseCreateScore": "0",
         "baseHighScore": "430",
         "taxId1": "1234",
         "taxId2": "1234",
         "homePhone": "1005550001",
         "secondaryPhone": "1005550001",
         "workPhone": "1005550001",
         "cellPhone": "1005550001",
         "addressLine1": "123 Any Street",
         "addressLine2": "123 Any Lane",
         "city": "New Jersey",
         "state": "NJ",
         "postalCode": "12345",
         "actionStrategy": "A1",
         "adaptiveCreateScore": "0",
         "adaptiveHighScore": "430",
         "primaryBirthDate": "1990-08-24",
         "otherBirthDate": "1990-08-24",
         "cardStatusAtCaseCreate": "Active",
         "cardTrackerSeverity": "5",
         "fraudApproach": "Minimum",
         "memberNumber": "0",
         "highTransactionDateTime": "2021-07-20T07:00:00Z",
         "lastAnalyst": "Analyst",
         "lastFraudCode": "CASE_FRAUD_TYPE_APP_FRD",
         "lastName": "Smith",
         "lastScore": "0",
         "lastTransactionDateTime": "2021-07-20T07:00:00Z",
         "OriginalAnalyst": "Analyst",
         "scoreToUse": "Base",
         "rules": "RuleManager Case Create"
      },
      {
         "logo": "APIP",
         "cardNumber": "400020XXXXXX4000",
         "caseNumber": "888888888",
         "caseCreatedDateTime": "2021-07-20T07:00:00Z",
         "caseStatus": "OPEN",
         "name": "Alex Smith",
         "caseClosedDateTime": "2021-07-21T07:00:00Z",
         "archived": "No",
         "baseCreateScore": "0",
         "baseHighScore": "430",
         "taxId1": "1234",
         "taxId2": "1234",
         "homePhone": "1005550001",
         "secondaryPhone": "1005550001",
         "workPhone": "1005550001",
         "cellPhone": "1005550001",
         "addressLine1": "123 Any Street",
         "addressLine2": "123 Any Lane",
         "city": "New Jersey",
         "state": "NJ",
         "postalCode": "12345",
         "actionStrategy": "A1",
         "adaptiveCreateScore": "0",
         "adaptiveHighScore": "430",
         "primaryBirthDate": "1990-08-24",
         "otherBirthDate": "1990-08-24",
         "cardStatusAtCaseCreate": "Active",
         "cardTrackerSeverity": "5",
         "fraudApproach": "Minimum",
         "memberNumber": "0",
         "highTransactionDateTime": "2021-07-20T07:00:00Z",
         "lastAnalyst": "Analyst",
         "lastFraudCode": "CASE_FRAUD_TYPE_APP_FRD",
         "lastName": "Smith",
         "lastScore": "0",
         "lastTransactionDateTime": "2021-07-20T07:00:00Z",
         "OriginalAnalyst": "Analyst",
         "scoreToUse": "Base",
         "rules": "RuleManager Case Create"
      }
   ]
}
```

### Fraud Case v1: Search using date range and case tenant

Search for fraud cases based on fromDateTime and todateTime and optional field caseTenant field.

#### Request

**HTTP Method:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/fraud/v1/cases/search

```
{
   "fromDateTime": "2021-07-20T07:00:00Z",
   "toDateTime": "2021-07-20T07:00:00Z",
   "caseTenant": "60"
}
```

#### Response

**HTTP Code:** 200 OK

```
{
   "caseSearchResults": [
      {
         "logo": "APIP",
         "cardNumber": "400020XXXXXX4000",
         "caseNumber": "999999999",
         "caseTenant": "60",
         "caseCreatedDateTime": "2021-07-20T07:00:00Z",
         "caseStatus": "OPEN",
         "name": "Alex Smith",
         "caseClosedDateTime": "2021-07-21T07:00:00Z",
         "archived": "No",
         "baseCreateScore": "0",
         "baseHighScore": "430",
         "taxId1": "1234",
         "taxId2": "1234",
         "homePhone": "1005550001",
         "secondaryPhone": "1005550001",
         "workPhone": "1005550001",
         "cellPhone": "1005550001",
         "addressLine1": "123 Any Street",
         "addressLine2": "123 Any Lane",
         "city": "New Jersey",
         "state": "NJ",
         "postalCode": "12345",
         "actionStrategy": "A1",
         "adaptiveCreateScore": "0",
         "adaptiveHighScore": "430",
         "primaryBirthDate": "1990-08-24",
         "otherBirthDate": "1990-08-24",
         "cardStatusAtCaseCreate": "Active",
         "cardTrackerSeverity": "5",
         "fraudApproach": "Minimum",
         "memberNumber": "0",
         "highTransactionDateTime": "2021-07-20T07:00:00Z",
         "lastAnalyst": "Analyst",
         "lastFraudCode": "CASE_FRAUD_TYPE_APP_FRD",
         "lastName": "Smith",
         "lastScore": "0",
         "lastTransactionDateTime": "2021-07-20T07:00:00Z",
         "OriginalAnalyst": "Analyst",
         "scoreToUse": "Base",
         "rules": "RuleManager Case Create"
      },
      {
         "logo": "APIP",
         "cardNumber": "400020XXXXXX4000",
         "caseNumber": "888888888",
         "caseCreatedDateTime": "2021-07-20T07:00:00Z",
         "caseStatus": "OPEN",
         "name": "Alex Smith",
         "caseClosedDateTime": "2021-07-21T07:00:00Z",
         "archived": "No",
         "baseCreateScore": "0",
         "baseHighScore": "430",
         "taxId1": "1234",
         "taxId2": "1234",
         "homePhone": "1005550001",
         "secondaryPhone": "1005550001",
         "workPhone": "1005550001",
         "cellPhone": "1005550001",
         "addressLine1": "123 Any Street",
         "addressLine2": "123 Any Lane",
         "city": "New Jersey",
         "state": "NJ",
         "postalCode": "12345",
         "actionStrategy": "A1",
         "adaptiveCreateScore": "0",
         "adaptiveHighScore": "430",
         "primaryBirthDate": "1990-08-24",
         "otherBirthDate": "1990-08-24",
         "cardStatusAtCaseCreate": "Active",
         "cardTrackerSeverity": "5",
         "fraudApproach": "Minimum",
         "memberNumber": "0",
         "highTransactionDateTime": "2021-07-20T07:00:00Z",
         "lastAnalyst": "Analyst",
         "lastFraudCode": "CASE_FRAUD_TYPE_APP_FRD",
         "lastName": "Smith",
         "lastScore": "0",
         "lastTransactionDateTime": "2021-07-20T07:00:00Z",
         "OriginalAnalyst": "Analyst",
         "scoreToUse": "Base",
         "rules": "RuleManager Case Create"
      }
   ]
}
```

### Fraud Case v1: Search transactions using case number and filter- AUTHORIZATIONS

Returns specified transactions associated with a case based on filter value "AUTHORIZATIONS"

#### Request

**HTTP Method:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/fraud/v1/cases/transactions?filter=AUTHORIZATIONS

```
{
  "caseNumber": "999999999"
}
```

#### Response

**HTTP Code:** 200 OK

```
{
  "authTransactions": [
    {
      "transactionId": "0000001234",
      "disposition": "Not Fraud",
      "cardNumber": "400020XXXXXX4000",
      "transactionDateTime": "2021-07-20T07:00:00Z",
      "amount": "25.05",
      "authDecision": "D",
      "cardPresent": true,
      "baseScore": "0",
      "adaptiveScore": "0",
      "scoreUsed": "Base & Adaptive",
      "mcc": "1111",
      "merchantName": "Home Supply",
      "countryCode": "840",
      "countryAlpha": "US",
      "actionStrategy": "A1",
      "authReason": "O",
      "authResponse": "090",
      "authSubResponse": "G",
      "cv": "I",  "authResponse": "090",
      "authSubResponse": "G",
      "cardCapacity": "1",
      "eci": "0",
      "entryMode": "U",
      "mcEMSReasonCode": "45",
      "mcEMSScore": "0",
      "memberNumber": "0",
      "merchantCity": "New Jersey",
      "merchantIdentifier": "Home Supply",
      "merchantPostalCode": "12345",
      "merchantState": "NJ",
      "messageType": "136",
      "pin": "X",
      "realTimeResponse": "4250",
      "starScore": "0",
      "tokenAssuranceLevel": "23",
      "tokenId": "5046490000000004",
      "tokenRequestorId": "12345678901",
      "tokenizationIndicator": "S",
      "transType": "I",
      "transactionPOS": "2",
      "vaaRCC1": "12",
      "vaaRCC2": "34",
      "vaaRCC3": "56",
      "vaaRRC": "34",
      "vaaRTD": "",
      "vaaScore": "12"
    }
  ]
}
```

### Fraud Case v1: Search transactions using case number, case tenant and filter- AUTHORIZATIONS

Search for fraud cases transactions based on request criteria caseNumber and caseTenant with filter value "AUTHORIZATIONS

#### Request

**HTTP Method:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/fraud/v1/cases/transactions?filter=AUTHORIZATIONS

```
{
    "caseNumber": "999999999",
    "caseTenant": "60"
}
```

#### Response

**HTTP Code:** 200 OK

```
{
    "authTransactions": [
        {
          "transactionId": "0000001234",
          "disposition": "Not Fraud",
          "cardNumber": "400020XXXXXX4000",
          "transactionDateTime": "2021-07-20T07:00:00Z",
          "amount": "25.05",
          "authDecision": "D",
          "cardPresent": true,
          "baseScore": "0",
          "adaptiveScore": "0",
          "scoreUsed": "Base & Adaptive",
          "mcc": "1111",
          "merchantName": "Home Supply",
          "countryCode": "840",
          "countryAlpha": "US",
          "actionStrategy": "A1",
          "authReason": "O",
          "authResponse": "090",
          "authSubResponse": "G",
          "cv": "I",
          "cardCapacity": "1",
          "eci": "0",
          "entryMode": "U",
          "mcEMSReasonCode": "45",
          "mcEMSScore": "0",
          "memberNumber": "0",
          "merchantCity": "New Jersey",
          "merchantIdentifier": "Home Supply",
          "merchantPostalCode": "12345",
          "merchantState": "NJ",
          "messageType": "136",
          "pin": "X",
          "realTimeResponse": "4250",
          "starScore": "0",
          "tokenAssuranceLevel": "23",
          "tokenId": "5046490000000004",
          "tokenRequestorId": "12345678901",
          "tokenizationIndicator": "S",
          "transType": "I",
          "transactionPOS": "2",
          "vaaRCC1": "12",
          "vaaRCC2": "34",
          "vaaRCC3": "56",
          "vaaRRC": "34",
          "vaaRTD": "",
          "vaaScore": "12"
        }
    ]
}
```

### Fraud Case v1: Search transactions using case number and filter- DEPOSIT_AND_PAYMENTS

Returns specified transactions associated to a case based on filter value "DEPOSIT_AND_PAYMENTS"

#### Request

**HTTP Method:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/fraud/v1/cases/transactions?filter=DEPOSIT_AND_PAYMENTS

```
{
  "caseNumber" : "999999999"
}
```

#### Response

**HTTP Code:** 200 OK

```
{
    "depositAndPaymentTransactions": [
        {
            "transactionId": "1111115678",
            "disposition": "Not Fraud",
            "cardNumber": "400020XXXXXX4000",
            "transactionDateTime": "2021-07-20T07:00:00Z",
            "amount": "25.05",
            "authDecision": "D",
            "merchantName": "Home Supply",
            "countryCode": "840",
            "countryAlpha": "US",
            "actionStrategy": "A1",
            "authReason": "O",
            "authResponse": "090",
            "authSubResponse": "G",
            "memberNumber": "0",
            "transactionCity": "New Jersey",
            "merchantIdentifier": "Home Supply",
            "transactionPostalCode": "12345",
            "transactionState": "NJ",
            "messageType": "136",
            "realTimeResponse": "",
            "transType": "I",
            "transactionPOS": "2",
            "vaaRCC1": "42",
            "vaaRCC2": "23",
            "vaaRCC3": "11",
            "vaaRRC": "51",
            "vaaRTD": "2"
        }
    ]
}
```

### Fraud Case v1: Search transactions using case number, case tenant and filter- DEPOSIT_AND_PAYMENTS

Search for fraud cases transactions based on request criteria caseNumber and optional fields with filter value "DEPOSIT_AND_PAYMENTS".

#### Request

**HTTP Method:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/fraud/v1/cases/transactions?filter=DEPOSIT_AND_PAYMENTS

```
{
    "caseNumber": "999999999",
    "caseTenant": "60",
    "pageLimit": 50,
    "pageOffset": 1
}
```

#### Response

**HTTP Code:** 200 OK

```
{
    "depositAndPaymentTransactions": [
        {
            "transactionId": "1111115678",
            "disposition": "Not Fraud",
            "cardNumber": "400020XXXXXX4000",
            "transactionDateTime": "2021-07-20T07:00:00Z",
            "amount": "25.05",
            "authDecision": "D",
            "merchantName": "Home Supply",
            "countryCode": "840",
            "countryAlpha": "US",
            "actionStrategy": "A1",
            "authReason": "O",
            "authResponse": "090",
            "authSubResponse": "G",
            "memberNumber": "0",
            "transactionCity": "New Jersey",
            "merchantIdentifier": "Home Supply",
            "transactionPostalCode": "12345",
            "transactionState": "NJ",
            "messageType": "136",
            "realTimeResponse": "",
            "transType": "I",
            "transactionPOS": "2",
            "vaaRCC1": "42",
            "vaaRCC2": "23",
            "vaaRCC3": "11",
            "vaaRRC": "51",
            "vaaRTD": "2"
        }
    ]
}
```

### Fraud Case v1: Search rules using case number only

Search for fraud cases rules based on required field caseNumber.

#### Request

**HTTP Method:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/fraud/v1/cases/rules

```
{
  "caseNumber": "999999999"
}
```

#### Response

**HTTP Code:** 200 OK

```
{
  "associatedRulesAndTransactions": [
    {
      "transactionId": "0000001234",
      "createdCase": true,
      "reactivatedCase": false,
      "rules": [
        {
          "ruleFiredDateTime": "2021-07-20T07:00:00Z",
          "ruleSet": "decision_DBTRAN25",
          "ruleName": "RuleManager Case Create"
        }
      ]
    }
  ]
}
```

### Fraud Case v1: Search rules using case number and case tenant

Search for fraud cases rules based on required field caseNumber and optional field caseTenant.

#### Request

**HTTP Method:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/fraud/v1/cases/rules

```
{
  "caseNumber": "999999999",
  "caseTenant": "60"
}
```

#### Response

**HTTP Code:** 200 OK

```
{
  "associatedRulesAndTransactions": [
    {
      "transactionId": "0000001234",
      "createdCase": true,
      "reactivatedCase": false,
      "rules": [
        {
          "ruleFiredDateTime": "2021-07-20T07:00:00Z",
          "ruleSet": "decision_DBTRAN25",
          "ruleName": "RuleManager Case Create"
        }
      ]
    }
  ]
}
```

### Fraud Case v1: Retrieve details using case number only

Returns all the case details including the status.

#### Request

**HTTP Method:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/fraud/v1/cases/case

```
{
   "caseNumber": "999999999"
}
```

#### Response

**HTTP Code:** 200 OK

```
{
    "logo": "APIP",
    "cardNumber": "400020XXXXXX4000",
    "caseNumber": "999999999",
    "caseTenant": "60",
    "caseCreatedDateTime": "2021-07-20T07:00:00Z",
    "name": "Alex Smith",
    "otherName": "Smith",
    "fraudApproach": "Custom",
    "languagePreference": "English",
    "newReactivatedIndication": "New",
    "currentCardStatus": "Active",
    "currentCaseStatus": "OPEN",
    "actionStrategy": "A1",
    "currentContactChannel": [
        "Email CH",
        "SMS CH"
    ],
    "homePhone": "1005550001",
    "workPhone": "1005550001",
    "cellPhone": "1005550001",
    "emailAddress": "alexsmith@example.com",
    "textAddress": "1005550001",
    "enrollmentStatus": "Sent",
    "enrollmentDate": "2021-07-20T07:00:00Z",
    "createScore": "0",
    "highScore": "430",
    "usedForEnfact": {
        "homePhone": true,
        "cellPhone": true,
        "workPhone": true,
        "emailAddress": true,
        "textAddress": true
    }
}
```

### Fraud Case v1: Retrieve details using case number and case tenant

Returns all the case details including the status and caseTenant.

#### Request

**HTTP Method:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/fraud/v1/cases/case

```
{
  "caseNumber": "999999999",
  "caseTenant": "60",
}
```

#### Response

**HTTP Code:** 200 OK

```
{
  "logo": "APIP",
  "cardNumber": "400020XXXXXX4000",
  "caseNumber": "999999999",
  "caseTenant": "60",
  "caseCreatedDateTime": "2021-07-20T07:00:00Z",
  "name": "Alex Smith",
  "otherName": "Smith",
  "fraudApproach": "Custom",
  "languagePreference": "English",
  "newReactivatedIndication": "New",
  "currentCardStatus": "Active",
  "currentCaseStatus": "OPEN",
  "actionStrategy": "A1",
  "currentContactChannel": [
    "Email CH",
    "SMS CH"
  ],
  "homePhone": "1005550001",
  "workPhone": "1005550001",
  "cellPhone": "1005550001",
  "emailAddress": "alexsmith@example.com",
  "textAddress": "1005550001",
  "enrollmentStatus": "Sent",
  "enrollmentDate": "2021-07-20T07:00:00Z",
  "createScore": "0",
  "highScore": "430",
  "usedForEnfact": {
    "homePhone": true,
    "cellPhone": true,
    "workPhone": true,
    "emailAddress": true,
    "textAddress": true
  }
}
```

### Fraud Case v1: Update details for existing case

Update the fraud case details for existing details.

#### Request

**HTTP Method:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/fraud/v1/cases

```
{
    "caseNumber": "999999999",
    "caseStatus": "CLOSED_UNCONFIRMED_FRAUD",
    "cardStatus": "ACTIVE",
    "leftMessage": true,
    "contactedCardholder": true,
    "homePhoneValid": true,
    "workPhoneValid": true,
    "cellPhoneValid": true,
    "caseComments": "No Contact Found due to INVALID data",
    "transactionDetails": [
        {
            "transactionId": "1111115678",
            "transactionDisposition": "NOT_FRAUD"
        }
    ]
}
```

#### Response

**HTTP Code:** 204 No Content

### Fraud Case v1: Update details using case tenant

Update the fraud case details with caseTenant

#### Request

**HTTP Method:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/fraud/v1/cases

```
{
  "caseNumber": "999999999",
  "caseTenant": "60",
  "caseStatus": "CLOSED_UNCONFIRMED_FRAUD",
  "fraudCode": "APPLICATION_FRAUD",
  "cardStatus": "ACTIVE",
  "leftMessage": true,
  "contactedCardholder": true,
  "homePhoneValid": true,
  "workPhoneValid": true,
  "cellPhoneValid": true,
  "caseComments": "No Contact Found due to INVALID data",
  "transactionDetails": [
    {
      "transactionId": "1111115678",
      "transactionDisposition": "NOT_FRAUD"
    }
  ]
}
```

#### Response

**HTTP Code:** 204 No Content
