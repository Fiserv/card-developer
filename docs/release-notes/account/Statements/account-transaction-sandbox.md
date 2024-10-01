# Test Cases

<span style="color:#ff6600;">**Account API endpoints**</span>

## Transactions

### Retrieve transaction summary
 

#### Request
**HTTP METHOD:** POST

**Target URL:** https://cardsandbox.api.fiservapps.com/cs/accounts/v1/accounts/transactions/search?filter=summary
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
### Retrieve transaction summary with pageOffset and pageLimit
 
#### Request
**HTTP METHOD:** POST

**Target URL:** https://cardsandbox.api.fiservapps.com/cs/accounts/v1/accounts/transactions/search?filter=summary&pageOffset=1&pageLimit=2
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
### Retrieve transaction detail
 

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
````
### Retrieve transaction detail with pageOffset and pageLimit
 
#### Request
**HTTP METHOD:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/accounts/v1/accounts/transactions/search?filter=detail&pageOffset=1&pageLimit=2
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
