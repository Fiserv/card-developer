# Test Cases

<span style="color:#ff6600;">**Payments API Endpoints**</span>

Tests must use only requests given here.

## Payment Search

### Payments Details v1: Search details using account number

This method returns all the Payments associated to one specific Account Number

#### Request

**HTTP Method:** POST

**Target URL:**  https://card-sandbox.api.fiservapps.com/cs/payments/v1/payments/search

```
{
    "accountNumber": "123456789"
}
```

#### Response

**HTTP Code:** 200 OK

```
{
    "count": 2,
    "payments": [
        {
            "paymentDate": "2023-12-15",
            "paymentAmount": "14.00",
            "dueDate": "2023-12-17",
            "effectiveDate": "2023-12-15",
            "cycleDate": "2023-11-22",
            "paymentDueAmount": "0.00",
            "reversalCode": "Not Reversed",
            "description": "Payments",
            "daysDelinquent": "0",
            "delinquentAmount": "0.00",
            "fixPaymentAmount": "0.00",
            "paymentTicketIdentifier": "349301656011603",
            "postDate": "2023-12-15",
            "transactionAmount": "-14.00",
            "transactionCode": "271",
            "interestFeesDistribution": [
                {
                    "paymentBalanceDescription": "REV CASH ADVANCE",
                    "balanceId": "0000000",
                    "paymentChangeToPrincipalAmount": "-14.00",
                    "paymentFeeAdjustmentAmount": "0.00"
                }
            ]
        },
        {
            "paymentDate": "2023-11-16",
            "paymentAmount": "40675.48",
            "dueDate": "2023-11-16",
            "effectiveDate": "2023-11-16",
            "cycleDate": "2023-10-22",
            "paymentDueAmount": "40675.48",
            "reversalCode": "Not Reversed",
            "description": "Payments",
            "daysDelinquent": "240",
            "delinquentAmount": "40675.48",
            "fixPaymentAmount": "0.00",
            "paymentTicketIdentifier": "320312500000001",
            "postDate": "2023-11-16",
            "transactionAmount": "-40675.48",
            "transactionCode": "271",
            "interestFeesDistribution": [
                {
                    "paymentBalanceDescription": "REV MERCHANDISE",
                    "balanceId": "0000000",
                    "paymentChangeToPrincipalAmount": "-9698.60",
                    "paymentFeeAdjustmentAmount": "-407.42"
                },
                {
                    "paymentBalanceDescription": "AHBALXFR",
                    "balanceId": "2217901",
                    "paymentChangeToPrincipalAmount": "-29532.98",
                    "paymentFeeAdjustmentAmount": "-1036.48"
                }
            ]
        }
    ]
}
```
