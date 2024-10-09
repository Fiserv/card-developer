# Test Cases

<span style="color:#ff6600;">**Fraud API Endpoints**</span>

When testing these endpoints, please use the test cases and test data from the Sandbox.

## Fraud Alerts

### Fraud Alerts v1: Search fraud case

Retrieve current fraud case information from Fiserv.

#### Request

**HTTP Method:** POST

**Target URL:**  https://card-sandbox.api.fiservapps.com/cs/legate/fraud/v1/case/search

```
{
  "clientId": "07100015",
  "clientApplicationName": "FRAUDALERTRWS",
  "clientVendorName": "ABC VENDOR",
  "clientAuditId": "Maria",
  "systemRecordIdentifier": "/XpwDirKMMx5Svoi48Y/n7VB8mzZRcJndyFgFuL/LPCT/dnqH2Gi2OwOIriS8Vtt",
  "caseID": "60384538"
}
```

#### Response

**HTTP Code:** 200 OK

```
{
  "caseData": [
    {
      "caseID": "60384538",
      "workflowCode": "14",
      "lastUpdated": "2019-07-26T15:43:34.291Z"
    }
  ],
  "tranData": [
    {
      "tranId": "016001da2e000044",
      "tranDate": "2019-07-26T11:22:04.000Z",
      "tranAmount": 600,
      "merchantName": "NETFLIX COM",
      "merchantCity": "LOS GATOS",
      "merchantState": "CA",
      "merchantCntry": "840",
      "tranMcc": "4899",
      "decisionCode": "D"
    }
  ]
}
```

### Fraud Alerts v1: Alert outcome

Enable business partners to notify Fiserv of updates to a case under review. Fiserv returns a response that identifies if a case outcome request is accepted or rejected and, if rejected, the reason why.

#### Request

**HTTP Method:** POST

**Target URL:**  https://card-sandbox.api.fiservapps.com/cs/legate/fraud/v1/alertOutcome

```
{
  "clientId": "07100015",
  "clientApplicationName": "FRAUDALERTRWS",
  "clientVendorName": "ABC VENDOR",
  "clientAuditId": "Maria",
  "systemRecordIdentifier": "/XpwDirKMMx5Svoi48Y/n7VB8mzZRcJndyFgFuL/LPCT/dnqH2Gi2OwOIriS8Vtt",
  "caseData": {
    "caseID": "60384538",
    "lastUpdated": "2019-07-26T15:43:34.291Z"
  },
  "tranResult": [
    {
      "number": "177185",
      "result": "NO_FRAUD"
    }
  ],
  "cardStatusAction": "BLOCK",
  "response": {
    "code": "61",
    "description": "Fraud"
  },
  "subResponse": {
    "code": "",
    "description": ""
  },
  "notificationTimestamp": "2018-04-13T14:06:02.197Z"
}
```

### Fraud Alerts v1: Close a fraud case

Notify Fiserv if a case for Fraud Alert is closed on the vendor platform.

#### Request

**HTTP Method:** PUT

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/legate/fraud/v1/caseClose

```
{
  "clientId": "07100015",
  "clientApplicationName": "FRAUDALERTRWS",
  "clientVendorName": "ABC VENDOR",
  "clientAuditId": "Maria",
  "systemRecordIdentifier": "/XpwDirKMMx5Svoi48Y/n7VB8mzZRcJndyFgFuL/LPCT/dnqH2Gi2OwOIriS8Vtt",
  "caseData": {
    "caseID": "60384538",
    "lastUpdated": "2019-07-26T15:43:34.291Z"
  },
  "caseResultData": {
    "code": "61",
    "description": "Fraud"
  },
  "caseFinish": "2019-06-18T20:18:02.197Z"
}
```

#### Response

**HTTP Code:** 200 OK
