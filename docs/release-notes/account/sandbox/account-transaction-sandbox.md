# Test Cases

## Transactions

<span style="color:#ff6600;">**Account API endpoints**</span>

### Accounts Transactions v1: Search account transactions using summary filter

This case retrieves the account transactions using summary filter.

#### Request

**HTTP METHOD:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/accounts/v1/accounts/transactions/search?filter=summary

```
{
    "accountNumber": "123456789",
    "filterCriteria": [
        {
            "filterBy": "FROM_DATE",
            "filterValue": "2022-09-17"
        },
        {
            "filterBy": "FROM_DATE",
            "filterValue": "2022-10-22"
        }
    ]
}
```

#### Response

**HTTP code:** 200 OK

```
{
    "count": 2,
    "transactions": [
        {
            "transactionDateTime": "2022-10-22T19:50:40Z",
            "merchantName": "Store1",
            "authorizationCode": "121052",
            "transactionCode": "255",
            "transactionType": "Return",
            "merchantCategoryCode": "00000",
            "transactionStatus": "POSTED",
            "transactionAmount": "40.00"
        },
        {
            "transactionDateTime": "2022-09-17T04:00:00Z",
            "merchantName": "Store1",
            "authorizationCode": "121052",
            "transactionCode": "255",
            "transactionType": "Return",
            "merchantCategoryCode": "00000",
            "transactionStatus": "POSTED",
            "transactionAmount": "100.00"
        }
    ]
}
```

### Accounts Transactions v1: Search account transactions using detail filter

This case retrieves the account transactions using detail filter.

#### Request

**HTTP METHOD:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/accounts/v1/accounts/transactions/search?filter=detail

```
{
    "accountNumber": "123456789",
    "filterCriteria": [
        {
            "filterBy": "FROM_DATE",
            "filterValue": "2022-09-17"
        },
        {
            "filterBy": "FROM_DATE",
            "filterValue": "2022-10-22"
        }
    ]
}
```

#### Response

**HTTP code:** 200 OK

```
{
    "count": 2,
    "transactions": [
        {
            "authorizationCode": "121052",
            "merchantCategoryCode": "00000",
            "merchantCity": "Newark",
            "merchantState": "NJ",
            "transactionDateTime": "2022-10-22T19:50:40Z",
            "transactedCardOrAccountNumber": "400020XXXXXX4000",
            "statusDescription": "64-PILOST",
            "merchantName": "Store1",
            "transactionCode": "255",
            "transactionType": "Return",
            "transactionStatus": "POSTED",
            "transactionAmount": "40.00",
            "responseCode": "096",
            "responseCodeDescription": "SYSTEM MALFUNCTION",
            "postedTransactionDetails": {
                "cardholderAccountNumber": "XXXXXXXXXXXX6789",
                "transactionDescription": "BALANCE TRANSFER CASH",
                "promotionId": "124",
                "postingDate": "2014-10-02",
                "detailTransactionIdentifier": "0000001234",
                "referenceNumber": "85548362L00XTMK3P"
            }
        },
        {
            "authorizationCode": "121052",
            "merchantCategoryCode": "00000",
            "merchantCity": "Newark",
            "merchantState": "NJ",
            "transactionDateTime": "2022-09-17T04:00:00Z",
            "transactedCardOrAccountNumber": "400020XXXXXX4000",
            "statusDescription": "64-PILOST",
            "merchantName": "Store1",
            "transactionCode": "255",
            "transactionType": "Return",
            "transactionStatus": "POSTED",
            "transactionAmount": "100.00",
            "responseCode": "096",
            "responseCodeDescription": "-NETWORK NOT FOUND",
            "postedTransactionDetails": {
                "cardholderAccountNumber": "XXXXXXXXXXXX6789",
                "transactionDescription": "BALANCE TRANSFER CASH",
                "promotionId": "124",
                "postingDate": "2014-11-20",
                "detailTransactionIdentifier": "0000001234",
                "referenceNumber": "76248362L00XTMK3P"
            }
        }
    ]
}
```
