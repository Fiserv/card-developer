# Test Cases

<span style="color:#ff6600;">**Payments API Endpoints**</span>

Tests must use only requests given here.

## Payment Actions

### Payments Action v1: Update fixed payments

This method is used to update fixed payment.

#### Request

**HTTP Method:** POST

**Target URL:**  https://card-sandbox.api.fiservapps.com/cs/payments/v1/payments/actions

```
{
    "updateFixedPayment": {
        "paymentAmount": "200.18"
    },
    "accountNumber": "123456789"
}
```

#### Response

**HTTP Code:** 200 OK

### Payments Action v1: Update recurring payments

This method is used to update recurring payment.

#### Request

**HTTP Method:** POST

**Target URL:**  https://card-sandbox.api.fiservapps.com/cs/payments/v1/payments/actions

```
{
    "updateRecurringPayment": {
        "autoPaymentDesignatedAmount": "200.18",
        "autoPaymentChargeDdaFlag": "1",
        "transitRoutingAccount": "403912001",
        "autoPaymentStartDate": "2023-01-30",
        "autoPaymentEndDate": "9999-99-99"
    },
    "accountNumber": "123456789"
}
```

#### Response

**HTTP Code:** 200 OK

### Payments Action v1: Delete auto payments.

This method is used to delete auto payment.

#### Request

**HTTP Method:** POST

**Target URL:**  https://card-sandbox.api.fiservapps.com/cs/payments/v1/payments/actions

```
{
    "deleteAutoPayment": {
        "autoPaymentStartDate": "0000-00-00",
        "autoPaymentChargeDdaFlag": "0",
        "autoPaymentEndDate": "9999-99-99",
        "autoPaymentDesignatedAmount": "0"
    },
    "accountNumber": "123456789"
}
```

#### Response

**HTTP Code:** 200 OK

### Payments Action v1: Search scheduled payments

This method is used to search scheduled payments.

#### Request

**HTTP Method:** POST

**Target URL:**  https://card-sandbox.api.fiservapps.com/cs/payments/v1/payments/scheduledPayments/search

```
{
    "accountNumber": "123456789",
    "registrationId": "1234567",
    "registrationLookup": "12345678"
}
```

#### Response

**HTTP Code:** 200 OK

```
{
    "scheduleCount": 3,
    "scheduledPayments": [
        {
            "paymentDate": "2024-02-25",
            "paymentAmount": "100.00",
            "paymentType": "ONETIME_ACH",
            "routingNumberBankId": "123456789",
            "bankAccountNumber": "XXXXX6789",
            "paymentAccountType": "SAVINGS",
            "registrationId": "1234567",
            "confirmationNumber": "12345678",
            "recurringPaymentId": "12345",
            "appId": "1234",
            "transactionResultCode": "Payment_Pending",
            "paymentMedium": "eCheck"
        },
        {
            "paymentDate": "-",
            "paymentAmount": "-",
            "paymentType": "RECURRING_ACH",
            "routingNumberBankId": "123456789",
            "bankAccountNumber": "XXXXX6789",
            "paymentAccountType": "SAVINGS",
            "recurringPaymentType": "PayMinimumDue",
            "recurringStartDate": "2024-08-19",
            "recurringEndDate": "2024-12-20",
            "recurrenceDate": "ON_TIME_PAYMENT_DUE",
            "autoPaymentChargeDdaFlag": "I",
            "automaticPaymentCode": "I",
            "savingsAccountIdentifier": "XXXXX6789"
        },
        {
            "paymentDate": "2024-10-25",
            "paymentAmount": "100.00",
            "paymentType": "RECURRING_ACH",
            "routingNumberBankId": "123456789",
            "bankAccountNumber": "XXXXX6789",
            "paymentAccountType": "SAVINGS",
            "recurringPaymentType": "PayMinimumDue",
            "recurringStartDate": "2024-10-14",
            "recurringEndDate": "2024-12-11",
            "recurringCalendarDay": "25",
            "recurrenceDate": "SPECIFIC_DAY_MONTH",
            "registrationId": "1234567",
            "convenienceFeeRefundAmount": "0.00",
            "recurringPaymentId": "12345",
            "isDisabled": false,
            "recurringIntervalType": "Monthly",
            "intervalParam1": "Days",
            "intervalParam2": "25",
            "convFeeAmount": "0.00",
            "reference": "123456789002/08/2024",
            "appId": "1234",
            "nextPayDate": "2024-10-25",
            "createddate": "2024-02-08"
        }
    ]
}
```

### Payments Action v1: Make scheduled payments

This method is used to make scheduled payments.

#### Request

**HTTP Method:** POST

**Target URL:**  https://card-sandbox.api.fiservapps.com/cs/payments/v1/payments/scheduledPayment

```
{ 
  "accountNumber": "123456789",
  "registrationId": "1234567",
   "makePayment": {
       "paymentAmount": "9.00",
        "taxAmount": "0",
        "paymentMedium": "eCheck",
        "authorizationMedium": "Voice",
        "paymentDate": "2022-12-17",
        "recurringStartDate": "2024-08-19",
        "paymentType": "RECURRING_ACH",
        "recurringPaymentType": "1",
        "recurrenceDate": "ON_TIME_PAYMENT_DUE",
        "paymentAccountType": "SAVINGS",
        "registrationId": "2778508",
        "bankAccountNumber": "123456789",
        "routingNumberBankId": "123456",
        "autoPaymentChargeDdaFlag": "I",
        "recurringEndDate": "2024-12-20",
        "recurringCalendarDay": "23",
        "failedCount": "0"
   }

}
```

#### Response

**HTTP Code:** 200 OK

### Payments Action v1: Update scheduled payments.

This method updates scheduled payments.

#### Request

**HTTP Method:** POST

**Target URL:**  https://card-sandbox.api.fiservapps.com/cs/payments/v1/payments/scheduledPayment

```
{ 
  "accountNumber": "123456789",
  "registrationId": "1234567",
   "updatePayment": {
      "paymentDate": "2021-12-31",
        "paymentAmount": "2.00",
        "paymentType": "RECURRING_ACH",
        "routingNumberBankId": "072403004",
        "bankAccountNumber": "123456789",
        "paymentAccountType": "CHECKING",
        "recurringPaymentType": "2",
        "recurringStartDate": "2021-12-14",
        "recurringEndDate": "2022-12-11",
        "recurringCalendarDay": "11",
        "recurrenceDate": "SPECIFIC_DAY_MONTH",
        "registrationId": "3495264",
        "autoPaymentChargeDdaFlag": null,
        "paymentPostDate": null,
        "confirmationNumber": "1234",
        "convenienceFeeRefundAmount": null,
        "recurringPaymentId": "12345678",
        "isDisabled": false,
        "disabledDate": "2022-12-11",
        "demandDepositAccount": "123456789",
        "disabledReason": "01",
        "recurringIntervalType": "Monthly",
        "intervalParam1": "Days",
        "intervalParam2": "11",
        "convFeeAmount": "1",
        "amountPaid": "10.00",
        "taxAmount": "0.00",
        "authorizationMedium": "Voice",
        "paymentMedium": "eCheck",
        "failedCount": "0",
   }

}
```

#### Response

**HTTP Code:** 200 OK

### Payments Action v1: Cancel scheduled payments

This method cancels scheduled payments.

#### Request

**HTTP Method:** POST

**Target URL:**  https://card-sandbox.api.fiservapps.com/cs/payments/v1/payments/scheduledPayment

```
{ 
  "accountNumber": "123456789",
  "registrationId": "1234567",
   "cancelPayment": {
      "paymentType": "RECURRING_ACH",
        "recurrenceDate": "ON_TIME_PAYMENT_DUE",
        "paymentAccountType": "CHECKING",
        "bankAccountNumber": "123456789",
        "routingNumberBankId": "123456",
        "autoPaymentStartDate": "2021-12-11",
        "autoPaymentEndDate": "2021-12-12",
        "autoPaymentDesignatedAmount": "0",
        "autoPaymentEnrollmentTypeCode": "T",
        "autoPaymentChargeDdaFlag": "0"
   }
}
```

#### Response

**HTTP Code:** 200 OK

### Payments Action v1: Search registered account

This method searches the registered account.

#### Request

**HTTP Method:** POST

**Target URL:**  https://card-sandbox.api.fiservapps.com/cs/payments/v1/payments/registeredAccount/search

```
{
    "accountNumber": "123456789",
    "registrationId": "1234567",
    "registrationLookup": "12345678"
}
```

#### Response

**HTTP Code:** 200 OK

```
{
    "registeredAccounts": [
        {
            "registrationId": "1234567",
            "bankRoutingNumber": "123456789",
            "accountType": "SAVINGS",
            "bankAccountNumber": "1234",
            "nameFirst": "John",
            "namelast": "Doe",
            "nameFull": "johndoe",
            "paymentmedium": "eCheck"
        },
        {
            "registrationId": "1234567",
            "bankRoutingNumber": "123456789",
            "accountType": "SAVINGS",
            "bankAccountNumber": "1234",
            "nameFirst": "John",
            "namelast": "Doe",
            "nameFull": "johndoe",
            "paymentmedium": "eCheck"
        },
        {
            "registrationId": "1234567",
            "bankRoutingNumber": "123456789",
            "accountType": "SAVINGS",
            "bankAccountNumber": "1234",
            "nameFirst": "John",
            "namelast": "Doe",
            "nameFull": "johndoe",
            "paymentmedium": "eCheck"
        }
    ]
}
```

### Payments Action v1: Add registered account

This method adds the registered account.

#### Request

**HTTP Method:** POST

**Target URL:**  https://card-sandbox.api.fiservapps.com/cs/payments/v1/payments/registeredAccount

```
{ 
  "accountNumber": "123456789",
  "registrationId": "1234567",
   "addRegisteredAccount": {
    "registrationId": null,
        "bankRoutingNumber": "123456789",
        "accountType": "SAVINGS",
        "bankAccountNumber": "123456789",
        "nameFirst": "JOHN",
        "nameLast": "DOE",
        "nameFull": "JOHN DOE",
        "authorizationMedium": "Voice",
        "paymentMedium": "eCheck",
        "lookupReference": "123456789",
        "agreedToTerms": "true"
   }

}
```

#### Response

**HTTP Code:** 201 Created

```
{
    "registeredAccounts": [
        {
            "registrationId": "1234567",
            "bankRoutingNumber": "123456789",
            "accountType": "SAVINGS",
            "bankAccountNumber": "XXXXX6789",
            "nameFirst": "JOHN",
            "nameLast": "DOE",
            "nameFull": "JOHNDOE",
            "authorizationMedium": "Voice",
            "paymentMedium": "eCheck",
            "lookupReference": "XXXXX6789",
            "agreedToTerms": "true"
        }
    ]
}
```

### Payments Action v1: Delete registered account

This method deletes the registered account.

#### Request

**HTTP Method:** POST

**Target URL:**  https://card-sandbox.api.fiservapps.com/cs/payments/v1/payments/registeredAccount

```
{
    "accountNumber": "123456789",
      
   "deleteRegisteredAccount": {
    "registrationId": "1234567",
    "accountType": "CHECKING",
    "firstName": "JOHN",
    "lastName": "DOE",
    "fullName": "JOHN DOE",
    "authorizationMedium": "Web",
    "paymentMedium": "e-Check",
    "lookupReference": "123456789",
    "agreedToTerms": true
  }
}
```

#### Response

**HTTP Code:** 201 Created

```
{
    "registeredAccounts": [
        {
            "registrationId": "1234567",
            "bankRoutingNumber": "123456789",
            "accountType": "SAVINGS",
            "bankAccountNumber": "XXXXX6789",
            "nameFirst": "JOHN",
            "nameLast": "DOE",
            "nameFull": "JOHNDOE",
            "authorizationMedium": "Voice",
            "paymentMedium": "eCheck",
            "lookupReference": "XXXXX6789",
            "agreedToTerms": "true"
        }
    ]
}
```

### Payments Action v1: Add right time payment

Use this method to add the right time payment.

#### Request

**HTTP Method:** POST

**Target URL:**  https://card-sandbox.api.fiservapps.com/cs/payments/v1/payments/rightTimePayment

```
{
    "paymentAmount": "05.09",
    "transactionDate": "2023-10-31",
    "cardNumber": "4000200030004001"
}
```

#### Response

**HTTP Code:** 200 OK

### Payments Action v1: Reverse right time payment

Use this method to reverse the right time payment.

#### Request

**HTTP Method:** POST

**Target URL:**  https://card-sandbox.api.fiservapps.com/cs/payments/v1/payments/reverseRightTimePayment

```
{
    "merchantNumber": "123456789",
    "cardNumber": "4000200030004001",
    "paymentAmount": "05.09",
    "paymentSourceCode": "UNKNOWN",
    "paymentTypeCode": "UNKNOWN",
    "transactionDate": "2023-10-31"
}
```

#### Response

**HTTP Code:** 204 No Content
