# Test Cases

##Limits

<span style="color:#ff6600;">**Account API endpoints**</span>

### Limits search
Search of account limits.
#### Request
**HTTP METHOD:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/accounts/v1/accounts/limits/search
```
{

    "accountNumber": "123456789"

}
```
#### Response
**HTTP code:** 200 OK
```
 {

   
    "currentBalanceAmount": "6457.72",
    "creditLimitAmount": "0000000000006000",
    "availableCreditAmount": "-457.00",
    "cashLimitAmount": "0000000000000070",
    "availableCashAmount": "-6387.00",
    "creditLineMaximumAmount": "0000000000030000",
    "temporaryCreditLine": true,
    "previousCreditLimitAmount": "000000000000000700",
    "temporaryCreditLimitAmount": "000000000000006000",
    "temporaryCreditLineEndDate": "2023-05-22",
    "billingCycle": "04",
    "lastpermanentCreditLimit": "000000000000800",
    "lastPermanentCreditLimitDate": "2023-02",
    "highBalanceDate": "2016-02-19",
    "highBalanceAmount": "6658.00"


}
```

## Limits update

Update of account limits.

### Update credit limit

#### Request
Update credit limit.
**HTTP METHOD:** PATCH

**Target URL:** https://card-sandbox.api.fiservapps.com /cs/v1/limits
```
{

    "accountNumber": "123456789",
	 "creditLimit": 8000

} 
```
#### Response
**HTTP code:** 204 No Content

 

### Update cash limit

#### Request
**HTTP METHOD:** PATCH

**Target URL:** https://card-sandbox.api.fiservapps.com /cs/v1/limits
```
{

    "accountNumber": "123456789",
	"cashLimit": {
        "limitType": "AMOUNT",
        "amount": 5000
    }

} 
```
#### Response
**HTTP code:** 204 No Content

### Update Temporary-Credit Limit

#### Request
**Update temporary-credit limit**
**HTTP METHOD:** PATCH

**Target URL:** https://card-sandbox.api.fiservapps.com /cs/v1/limits
```
{

    "accountNumber": "123456789",
	  "temporaryCreditLimit": {
		"setLimit": true,
		"amount": 5000,
		"endDate": "2024-06-30"
	}

}
```
#### Response
**HTTP code:** 204 No Content

### Remove temporary-credit limit

#### Request
**Remove temporary-credit limit**
**HTTP METHOD:** PATCH

**Target URL:** https://card-sandbox.api.fiservapps.com /cs/v1/limits

{

    "accountNumber": "123456789",
	  "temporaryCreditLimit": {
		"setLimit": false
	}

} 
#### Response
**HTTP code:** 204 No Content
