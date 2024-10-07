# Test Cases

<span style="color:#ff6600;">**Company API Endpoints**</span>

## Company Details

Tests must use only requests given here.

### Company Details v1: Search details using company ID

This method is used to get a company's details by using a combination of company, system, principal & agent identifier.

#### Request

**HTTP METHOD:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/companies/v1/id/search

```
{
   "companyIdentifier": "TEST0002",
   "systemIdentifier": "3771",
   "principalIdentifier": "0050",
   "agentIdentifier": "0000"
}
```

#### Response

**HTTP Code:** 200 OK

```
{
   "address": [
      {
         "addressLine1": "123 ANY STREET",
         "addressLine2": "APT 100",
         "country": "USA",
         "state": "NJ",
         "zipCode": "07054",
         "city": "PARSIPPANY"
      }
   ],
   "summary": [
      {
         "companyIdentifier": "TEST0002",
         "companyName": "FISERV",
         "systemIdentifier": "3771",
         "principalIdentifier": "0050",
         "agentIdentifier": "0000",
         "institutionName": "360 FEDERAL CREDIT UNION",
         "productName": "360 FCU VISA BUSINESS",
         "companyCreditLine": "100000",
         "companyAvailableCreditAmount": "86489",
         "companyContactTelephoneNumber": "9898989898",
         "openDate": "2020-07-15",
         "lastChangeDate": "2021-09-17",
         "billingCycleCode": "03",
         "annualFeeAmount": "0.0",
         "statementOptionCode": "SEND_STATEMENTS_TO_ISSUER",
         "paperStatementSuppressCode": "DO_NOT_SUPPRESS",
         "companyLastBillingDate": "2021-09-17",
         "companyNextBillingDate": "2021-10-17",
         "companyContactName": "DAVID",
         "principalOfficerName": "CLARA",
         "businessType": "ASSOCIATIONS",
         "goodAccountOutstandingBalanceAmount": "13511",
         "externallyStatusedAccountsOutstandingBalance": "0",
         "companyCreditLineExceptionPercentage": "100",
         "cardholderCreditLineExceptionPercentageRate": "100",
         "federalTaxFormTaxTypeCode": "TAX_ID",
         "federalTaxIdentifier": "981231256",
         "averageCardholderBalanceAmount": "3466",
         "goodAccountMaximumCreditLineAmount": "597600",
         "externallyStatusedAccountsMaximumCredit": "11250",
         "contractExpirationDate": "2099-12",
         "goodAccountsCount": "33",
         "externallyStatusedAccountsCount": "0",
         "fiscalYearEndCode": "JAN",
         "generalLedgerCostCenterIdentifier": "A32424RTRTREQW2311413241",
         "cdfIndicator": "CDF_REPORTING_ACTIVE",
         "vcfIndicator": "VCF_REPORORTING_ACTIVE",
         "reportLanguageCode": "ENGLISH",
         "miscellaneousField1Text": "OP1",
         "miscellaneousField2Text": "OP2",
         "miscellaneousField3Text": "OP3",
         "miscellaneousField4Text": "OP4",
         "creditScoreCode": "800",
         "numberOfEmployees": "10",
         "clientDefinedOneText": "1",
         "clientDefinedTwoText": "12",
         "clientDefinedThreeText": "123",
         "clientDefinedFourText": "123",
         "clientDefinedFiveText": "123",
         "clientDefinedSixText": "123",
         "clientDefinedSevenText": "1"
      }
   ]
}
```

### Company Details v1: Search details using company name

This method is to get list of companies by using company name. This will act as wild card search.

#### Request

**HTTP METHOD:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/companies/v1/name/search

```
{
   "companyName": "FISERV",
   "systemIdentifier": "3771"
}
```

#### Response

**HTTP Code:** 201 Created

```
{
   "summary": [
      {
         "agentIdentifier": "0000",
         "companyCreditLine": "100000",
         "companyIdentifier": "TEST0002",
         "companyName": "FISERV",
         "goodAccountsCount": "36",
         "principalIdentifier": "0050",
         "systemIdentifier": "3771",
         "address": [
            {
               "addressLine1": "123 ANY STREET",
               "addressLine2": "APT 100",
               "country": "USA",
               "state": "NJ",
               "zipCode": "07054",
               "city": "PARSIPPANY"
            }
         ]
      }
   ]
}
```

### Company Details v1: Update company summary fields

This API is used to update the company summary fields such as companyCreditLimit, billingCycleCode, fiscalYearEndCode and paperStatementSuppressCode.

#### Request

**HTTP METHOD:** PATCH

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/companies/v1/company

```
{
    "companyIdentifier": "TEST0002",
    "systemIdentifier": "3771",
    "principalIdentifier": "0050",
    "agentIdentifier": "0000",
    "companyCreditLimit": "1500",
    "billingCycleCode": "01",
    "fiscalYearEndCode": "JAN",
    "paperStatementSuppressCode": "DO_NOT_SUPPRESS",
    "vcfIndicator": "VCF_REPORTING_NOT_ACTIVE",
    "cdfIndicator": "CDF_REPORTING_NOT_ACTIVE"
}
```

#### Response

**HTTP Code:** 204 No Content

### Company Demographics v1: Delete company demographics details

This API is used to delete demographic details associated to the company.

#### Request

**HTTP METHOD:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/companies/v1/demographics

```
{
    "op": "DELETE_ASSOCIATION",
    "sequenceNumber": "00001",
    "companyIdentifier": "TEST0002",
    "systemIdentifier": "3771",
    "principalIdentifier": "0050",
    "agentIdentifier": "0000",
    "addressType": "INDIVIDUAL_GUARANTOR"
}
```

#### Response

**HTTP Code:** 204 No Content
