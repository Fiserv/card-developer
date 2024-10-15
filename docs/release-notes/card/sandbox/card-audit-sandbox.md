# Test Cases

<span style="color:#ff6600;">**Card API Endpoints**</span>

When testing these endpoints, please use the test cases and test data from the Sandbox.

## Audit

### Debit Audit v1: Retrieve details of audit records for card

Retrieves the details of audit log records for card.

#### Request

**HTTP Method:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v1/audit/details

```
{
      "cardNumber": "4000200030004000",
      "memberNumber": "0",
      "auditLogDateTime": "2021-07-20T08:00:00Z",
      "auditLogAction": "UPDATE",
      "pageLimit": 50,
      "pageOffset": 1
  }
```

#### Response

**HTTP Code:** 200 OK

```
{
      "cardNumber": "400010xxxxxx4000",
      "memberNumber": "0",
      "auditRecordDetails": [
          {
              "fieldName": "Account Type",
              "before": "Checking",
              "after": "Savings"
          }
      ]
  }
```

### Debit Audit v1: Retrieve audit records for a card for date range

Retrieves the audit details of a given debit card for date range.

#### Request

**HTTP Method:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v1/audit/search

```
{
      "cardNumber": "4000200030004000",
      "nonTransToken": "piUVBJKZGfks4000",
      "memberNumber": "0",
      "fromDateTime": "2021-07-20T07:00:00Z",
      "toDateTime": "2021-08-20T07:00:00Z"
  }
```

#### Response

**HTTP Code:** 200 OK

```
{
 "cardNumber": "400020XXXXXX4000",
  "nonTransToken": "piUVBJKZGfks4000",
  "memberNumber": "0",
  "auditLogSearch": [
    {
      "auditLogDateTime": "2021-07-20T08:00:00Z",
      "auditLogSource": "ATM",
      "auditLogAction": "UPDATE",
      "recordType": "Card Details (DAF).",
      "auditLogId": "Alex"
    }
 ]
}
```
