# Test Cases

<span style="color:#ff6600;">**Account API endpoints**</span>

## Details

### Account Details v1: Search account information using summary filter

This case retrieves the account details using summary filter.

#### Request

**HTTP METHOD:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/accounts/v1/accounts/search?filter=summary


``` 
{
    "accountNumber": "123456789" 
}
``` 
#### Response
**HTTP code:** 200

``` 
{
    "accountType": "Consumer",
    "description": "VISA Classic",
    "customerName": "Doe, Jesse H",
    "association": "PRIMARY",
    "accountStatus": "NORMAL"
}
``` 
### Account Details v1: Search account details using detail filter

This case retrieves the account information using detail filter.

#### Request

**HTTP METHOD:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/accounts/v1/accounts/search?filter=detail

``` 
{
    "accountNumber": "123456789" 
}
``` 

**HTTP code:** 200

``` 
{
    "accountType": "Consumer",
    "description": "VISA Classic",
    "customerName": "Doe, Jesse H",
    "association": "PRIMARY",
    "accountStatus": "NORMAL",
    "accountStatusReason": "00–Normal",
    "accountTransferStatus": "NO_TRANSFER_INVOLVEMENT",
    "accountUsageStatus": "NEVER_ACTIVE",
    "authorizationCode": "0",
    "automaticPaymentCode": "4",
    "automaticPaymentFlag": "1",
    "cashBalance": "30.00",
    "currentBalanceAmount": "3000.00",
    "coveredByMilitaryLendingAct": true,
    "expirationDate": "02/2029",
    "highBalanceDate": "2022-01-09",
    "highBalanceAmount": "90.00",
    "interestAccrualCode": "2",
    "lastNonMonetaryDate": "2020-09-23",
    "lastStatementBalanceAmount": "2500.00",
    "lastStatusChangeDate": "2020-09-23",
    "memberId": "411411",
    "nextCycleDate": "2022-12-09",
    "openedDate": "2020-09-23",
    "plasticCount": 1,
    "prepayCode": "0",
    "secured": "NOT_SECURED",
    "serviceMember": false,
    "serviceStartDate": "2021-12-23",
    "serviceEndDate": "2021-11-23",
    "vip": true
}
```  
