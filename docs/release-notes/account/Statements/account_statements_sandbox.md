# Test Cases

## Statements

### Retrieve statement with detail filter

Returns full detail information.

#### Request
**HTTP METHOD:** POST

**Target URL:**   https://card-sandbox.api.fiservapps.com/cs/accounts/v1/accounts/statements/search?filter=detail

``` 
{
    "accountNumber": "123456789",
    "fromDate": "2020-12-09",
    "toDate": "2022-12-28"
}
``` 
#### Response
**HTTP code:** 200

``` 
{
    "cardNumber": [
        "4257691000200020",
        "4257691000200021"
    ],
    "statementDetails": [
        {
            "statementDate": "2021-12-30",
            "statementEndingBalance": "1500.00",
            "delinquentAmount": "100.00",
            "statementFinanceChargeAmount": "10.00",
            "minimumPaymentDueAmount": "200.00",
            "paymentDueDate": "12-25",
            "statementOpeningBalanceAmount": "3000.00",
            "statementDebitAmount": "1500.00",
            "statementSalesAmount": "12.09",
            "statementOtherCreditsAmount": "15.15",
            "statementPaymentAmount": "400.00",
            "externalAccountStatusCode": "NORMAL",
            "yearToDateInterestAmount": "30.00",
            "purchaseCount": "15",
            "creditCount": "5",
            "paymentsCount": "10",
            "daysInBillingCycle": "31",
            "billingCycleCode": "28",
            "sinceLastStatementInterestAmount": "1.09",
            "overlimitFees": "5.00",
            "skipPaymentFlag": "No",
            "statementCreditLineAmount": "5000.00",
            "availableCreditRemaining": "4000.00",
            "statementTotals": {
                "adjustments": "99485.00",
                "cashAdvance": "1692.00",
                "credit": "10100.00",
                "payment": "665572.00",
                "purchase": "39181.00"
            },
            "statementTransactionDetails": {
                "totalTransactionsCount": 1,
                "statementTransactions": [
                    {
                        "cardOrAccountNumber": "4000200030004000",
                        "cardOrAccountTransactions": [
                            {
                                "authorizationCode": "606",
                                "currencyCode": "840",
                                "issuerAmount": "10.00",
                                "merchandiseDescription": "shoes",
                                "merchantAccount": "123456XXXXXX4067",
                                "merchantCategoryCode": "6010",
                                "merchantDescription": "Store1",
                                "merchantCity": "Newark",
                                "merchantState": "NJ",
                                "postDate": "2022-01-11",
                                "transactedCardOrAccountNumber": "400020XXXXXX4000",
                                "transactionAccountNumber": "123456XXXXXX4067",
                                "transactionCode": "251",
                                "transactionDate": "2021-04-24"
                            }
                        ]
                    }
                ]
            }
        }
    ]
}
 ```


### Retrieve statement with summary filter

Returns summary information only.

#### Request
**HTTP METHOD:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/accounts/v1/accounts/statements/search?filter=summary

``` 
{
    "accountNumber": "123456789",
    "fromDate": "2020-12-09",
    "toDate": "2022-12-28"
}
``` 
#### Response
**HTTP code:** 200

``` 
{
    "cardNumber": [
        "4257691000200020",
        "4257691000200021"
    ],
    "statementDetails": [
        {
            "statementDate": "2021-12-30",
            "statementEndingBalance": "1500.00",
            "delinquentAmount": "100.00",
            "statementFinanceChargeAmount": "10.00",
            "minimumPaymentDueAmount": "200.00",
            "paymentDueDate": "12-25"
        }
    ]
}
 ```
### Get PDF doc for account statements

Returns account statement PDF document against a docId provided in Request path variable.

#### Request
**HTTP METHOD:** GET

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/accounts/v1/accounts/statements/pdf/E68A974727A06929B786939B8C68B030CA4E56A3079985834543673C575B740FBE67229617FB

``` 
{
    "accountNumber": "123456789",
    "fromDate": "2020-12-09",
    "toDate": "2022-12-28"
}
``` 
#### Response
**HTTP code:** 200

``` 
Sample document will be visible.

 ```
### PDF search for given accountNumber

Returns list of all PDF statements for the given account number based on the date range passed in request.

#### Request
**HTTP METHOD:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/accounts/v1/accounts/statements/pdf/search

``` 
{
    "accountNumber": "123456789",
    "priorAccountNumber": "987456123",
    "fromDate": "2020-12-09",
    "toDate": "2022-12-28"
}
``` 
#### Response
**HTTP code:** 200

``` 
{
       "pdfs": [
   {
      "statementDate": "2022-05-31",
      "docId": "E68A974727A06929B786939B8C68B030CA4E56A3079985834543673C575B740FBE67229617FB",
      "link": "https://card.dsp.apimz.onefiserv.net/v2/statements/search/pdf/E68A974727A06929B786939B8C68B030CA4E56A3079985834543673C575B740FBE67229617FB"
    }
  ]
}
 ```
