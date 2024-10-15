# Test Cases

<span style="color:#ff6600;">**Company API Endpoints**</span>

## Company Accounts

Tests must use only requests given here.

### Company Accounts v1: Search company account details without using card number

This API will return all accounts associated with a company.

#### Request

**HTTP METHOD:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/companies/v1/accounts/search

```
{
    "companyIdentifier": "TEST0002",
    "systemIdentifier": "3771",
    "principalIdentifier": "0050",
    "agentIdentifier": "0000",
    "startSequence": "1",
    "endSequence": "3"
}
```

#### Response

**HTTP Code:** 200 OK

```
{
    "count": "3",
    "summary": [
	      {
            "accountNumber": "4907570050500063",
            "cardholderName": "JESSE, DOE",
            "accountType": "CONTROL",
            "creditLimitAmount": "59200.00",
            "currentBalanceAmount": "2501.74",
            "minimumPaymentDueAmount": "0.00",
            "statementEndingBalanceAmount": "2501.74",
            "lastStatementDate": "2024-01-01",
            "nextPaymentDueDate": "2024-01-26",
            "externalStatusCode": "NORMAL"
        },
	      {
            "accountNumber": "4907570050500071",
            "cardholderName": "JOHN, DOE",
            "accountType": "SUB",
            "creditLimitAmount": "200001.00",
            "currentBalanceAmount": "0.00",
            "controlAccountNumber": "4907570050500063",
            "minimumPaymentDueAmount": "0.00",
            "statementEndingBalanceAmount": "0.00",
            "lastStatementDate": "000000",
            "nextPaymentDueDate": "2024-01-26",
            "externalStatusCode": "NORMAL"
        },
	      {
            "accountNumber": "4907570050500089",
            "cardholderName": "COMPANY, TEST",
            "accountType": "INDIVIDUAL",
            "creditLimitAmount": "200001.00",
            "currentBalanceAmount": "0.00",
            "minimumPaymentDueAmount": "0.00",
            "statementEndingBalanceAmount": "0.00",
            "lastStatementDate": "000000",
            "nextPaymentDueDate": "2024-01-26",
            "externalStatusCode": "NORMAL"
        }
    ]
}
```

### Company Accounts v1: Add company control account

This API is used to add company control account.

#### Request

**HTTP METHOD:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/companies/v1/accounts/controls

```

{
    "companyIdentifier": "TEST0002",
    "systemIdentifier": "3771",
    "principalIdentifier": "0050",
    "agentIdentifier": "0000",
    "customerName": "JESSE, DOE",
    "creditLimitAmount": "99999",
    "federalTaxFormTaxTypeCode": "SOCIAL_SECURITY",
    "federalTaxIdentifier": "981231256",
    "personalizedEmbossing": "Test",
    "pricingStrategy": "AA01",
    "cardStock": "00",
    "workPhoneNumber": "2223334444",
    "workEmail": "zyz@test.com",
    "address": {
        "addressLine1": "123 Any Street",
        "addressLine2": "Apt 100",
        "country": "USA",
        "state": "NJ",
        "zipCode": "07054",
        "city": "Pasrippany",
        "isFormattedAddress": true
    }
}

```

#### Response

**HTTP Code:** 201 Created

```
{
  "companyIdentifier": "TEST0002",
  "systemIdentifier": "3771",
  "principalIdentifier": "0050",
  "agentIdentifier": "0000",
  "accountNumber": "4907570054342454",
  "cardNumber": "4907570054342389",
  "externalCustomerId": "B24029052933423554035550"
}
```

### Company Accounts v1: Add individual account

This API is used to add individual account.

#### Request

**HTTP METHOD:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/companies/v1/accounts/individuals

```
{
    "companyIdentifier": "TEST0002",
    "systemIdentifier": "3771",
    "principalIdentifier": "0050",
    "agentIdentifier": "0000",
    "customerName": "COMPANY, TEST",
    "mothersMaidenName": "Nancy",
    "dateOfBirth": "1990-08-24",
    "creditLimitAmount": "3000",
    "specialAccountHandeling": "NONE",
    "federalTaxFormTaxTypeCode": "SOCIAL_SECURITY",
    "federalTaxIdentifier": "981231256",
    "personalizedEmbossing": "John Doe",
    "pricingStrategy": "AA01",
    "cardStock": "00",
    "homePhoneNumber": "7406520178",
    "workPhoneNumber": "7406520178",
    "mobilePhoneNumber": "7406520178",
    "homeEmail": "testemail@email.com",
    "workEmail": "testemail@company.com",
    "address": {
        "addressLine1": "123 Any Street",
        "addressLine2": "Apt 100",
        "country": "USA",
        "state": "NJ",
        "zipCode": "07054",
        "city": "Parsippany",
        "isFormattedAddress": true
    }
}
```

#### Response

**HTTP Code:** 201 Created

```
{
    "companyIdentifier": "TEST0002",
    "systemIdentifier": "3771",
    "principalIdentifier": "0050",
    "agentIdentifier": "0000",
    "accountNumber": "4907570050500089",
    "cardNumber": "4907570054342215",
    "externalCustomerId": "B24029052933423554035550"
}
```

### Company Accounts v1: Add sub account

This API is used to add sub account.

#### Request

**HTTP METHOD:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/companies/v1/accounts/subs

```
{
    "companyIdentifier": "TEST0002",
    "systemIdentifier": "3771",
    "principalIdentifier": "0050",
    "agentIdentifier": "0000",
    "controlAccount": "4907570050500063",
    "customerName": "JOHN, DOE",
    "mothersMaidenName": "NANCY",
    "dateOfBirth": "1990-08-24",
    "creditLimitAmount": "3000",
    "specialAccountHandeling": "NONE",
    "federalTaxFormTaxTypeCode": "SOCIAL_SECURITY",
    "federalTaxIdentifier": "981231256",
    "personalizedEmbossing": "DOE, JOHN",
    "pricingStrategy": "AA01",
    "cardStock": "00",
    "homePhoneNumber": "7406520178",
    "workPhoneNumber": "7406520178",
    "mobilePhoneNumber": "7406520178",
    "homeEmail": "testemail@mail.com",
    "workEmail": "testemail@company.com",
    "address": {
        "addressLine1": "123 ANY STREET",
        "addressLine2": "APT 100",
        "country": "USA",
        "state": "NJ",
        "zipCode": "07054",
        "city": "PARSIPPANY",
        "isFormattedAddress": true
    }
}
```

#### Response

**HTTP Code:** 201 Created

```
{
    "companyIdentifier": "TEST0002",
    "systemIdentifier": "3771",
    "principalIdentifier": "0050",
    "agentIdentifier": "0000",
    "accountNumber": "4907570050500071",
    "cardNumber": "4907570054342454",
    "externalCustomerId": "B24029052933423554035550"
}
```
