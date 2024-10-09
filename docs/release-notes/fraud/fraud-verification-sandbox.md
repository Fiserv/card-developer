# Test Cases

<span style="color:#ff6600;">**Fraud API Endpoints**</span>

When testing these endpoints, please use the test cases and test data from the Sandbox.

## Verification

### Verification Search v3: Using card number

Retrieves allowed and available media addresses for cardholder's Verification. Possible media address types are Voice, Text, and Email. Media addresses are semi-masked for cardholder's confidentiality.

#### Request

**HTTP Method:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/fraud/v3/verification/search

```
{
   "cardNumber": "4000200030004000"
}
```

#### Response

**HTTP Code:** 200 OK

```
{
   "cardNumber": "400020XXXXXX4000",
   "nonTransToken": "piUVBJKZGfks4000",
   "memberNumber": "0",
   "contact": {
      "emailAddress": "ale******@example.com",
      "homePhone": "******0001",
      "workPhone": "******0001",
      "cellPhone": "******0001",
      "textAddress": "******0001"
   }
}
```

### Verification Search v3: Using NTT

Retrieves allowed and available media addresses for cardholder's Verification. Possible media address types are Voice, Text, and Email. Media addresses are semi-masked for cardholder's confidentiality.

#### Request

**HTTP Method:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/fraud/v3/verification/search

```
{
   "nonTransToken": "piUVBJKZGfks4000"
}
```

#### Response

**HTTP Code:** 200 OK

```
{
   "cardNumber": "400020XXXXXX4000",
   "nonTransToken": "piUVBJKZGfks4000",
   "memberNumber": "0",
   "contact": {
      "emailAddress": "ale******@example.com",
      "homePhone": "******0001",
      "workPhone": "******0001",
      "cellPhone": "******0001",
      "textAddress": "******0001"
   }
}
```

### Verification OTP v3: Generate passcode in email using card number

Retrieves a one time passcode for cardholder's verification. Generated passcode expires in 10 mins. Passcode is delivered on selected media address.

#### Request

**HTTP Method:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/fraud/v3/verification/otp

```
{
   "cardNumber": "4000200030004000",
   "memberNumber": "0",
   "jwtTokenFlag": true,
   "mediaType": "EMAIL",
   "mediaAddress": "ale******@example.com"
}
```

#### Response

**HTTP Code:** 201 Created

```
{
   "cardNumber": "400020XXXXXX4000",
   "nonTransToken": "piUVBJKZGfks4000",
   "memberNumber": "0",
   "otpId": "1234567",
   "jwt": "eyJ0eXAiOiJKV1QiLCJlbmMiOiJBMTI4R0NNIiwiYWxnIjoiUlNBLU9BRVAtMjU2In0.WrliT8nLQOTRnXldrYj0brobAyi6M7-U8_iHovmTH1VAZksc4mOGQCfaSx-sbDNjdkpeznR8lU1sHOX26qom94jBO6uePEw1cBbTHLpOSEPDYiWS6SzTgxguF7zT2g5Ui1HHi2GKgPtH5L0XC_QqP5TIs3A15fqpAnvMaSwW9O_GDRzxnsUDCgEZCkwQOuEpWYDbM7r7yKrfAlkWKOHOlZuUtvJvg3k8p-1qwKpuGexhWXQdgKsWphBWbMzbindOIefIo4VTrOVMxWOdP_bLNId0E0CBLxSpRHX1u3EeAjUykUdifT2CP4bb6kbJf4pp0dRc_uPZGJLj7faPyq6UeQ.zTLJMNI8bjGh-KBy.FW0W0ihL2sj7pYin2iY1gavS4W-yPswjKmrb6-ROwHgEOscfeGGLmUihzoV6vy9KvTJ9ytnIPqh-K94UsShUJ0-KgsY4_eWyUwx4IYpYaJkPeUVd4ni_1eZMBy6-hPr3n39DES_kXfnv3MJOiZZj0I-GJXw99WBV7xhl7KZcFKyMXYnszyboV8Xi2iZqHglvEoYRjKLvOlEq2j4pJoMRVfBB8oIOZm6uyCaOnyuWuE_Lg1HeuNMnHddTm8gexDAfwj3WYHkJazsN1PZVhPZVImyKwCNM.TOYk3lw2SKYamQL7XiLXlg",
   "status": "SUCCESS",
   "statusDescription": "SUCCESS",
   "mediaType": "EMAIL",
   "mediaAddress": "ale******@example.com"
}
```

### Verification OTP v3: Generate passcode in email using NTT

Retrieves a one time passcode for cardholder's verification. Generated passcode expires in 10 mins. Passcode is delivered on selected media address.

**HTTP Method:**POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/fraud/v3/verification/otp

#### Request

```
{
   "nonTransToken": "piUVBJKZGfks4000",
   "memberNumber": "0",
   "jwtTokenFlag": false,
   "mediaType": "EMAIL",
   "mediaAddress": "ale******@example.com"
}
```

#### Response

**HTTP Code:** 201 Created

```
{
   "cardNumber": "400020XXXXXX4000",
   "nonTransToken": "piUVBJKZGfks4000",
   "memberNumber": "0",
   "otpId": "1234567",
   "status": "SUCCESS",
   "statusDescription": "SUCCESS",
   "mediaType": "EMAIL",
   "mediaAddress": "ale******@example.com"
}
```

### Verification OTP v3: Generate generated passcode in email using NTT and JWT

Retrieves a one time passcode for cardholder's verification. Generated passcode expires in 10 mins. Passcode is delivered on selected media address.

#### Request

**HTTP Method:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/fraud/v3/verification/otp

```
{
   "nonTransToken": "piUVBJKZGfks4000",
   "memberNumber": "0",
   "jwtTokenFlag": true,
   "mediaType": "EMAIL",
   "mediaAddress": "ale******@example.com"
}
```

#### Response

**HTTP Code:** 201 Created

```
{
   "cardNumber": "400020XXXXXX4000",
   "nonTransToken": "piUVBJKZGfks4000",
   "memberNumber": "0",
   "otpId": "1234567",
   "jwt": "eyJ0eXAiOiJKV1QiLCJlbmMiOiJBMTI4R0NNIiwiYWxnIjoiUlNBLU9BRVAtMjU2In0.WrliT8nLQOTRnXldrYj0brobAyi6M7-U8_iHovmTH1VAZksc4mOGQCfaSx-sbDNjdkpeznR8lU1sHOX26qom94jBO6uePEw1cBbTHLpOSEPDYiWS6SzTgxguF7zT2g5Ui1HHi2GKgPtH5L0XC_QqP5TIs3A15fqpAnvMaSwW9O_GDRzxnsUDCgEZCkwQOuEpWYDbM7r7yKrfAlkWKOHOlZuUtvJvg3k8p-1qwKpuGexhWXQdgKsWphBWbMzbindOIefIo4VTrOVMxWOdP_bLNId0E0CBLxSpRHX1u3EeAjUykUdifT2CP4bb6kbJf4pp0dRc_uPZGJLj7faPyq6UeQ.zTLJMNI8bjGh-KBy.FW0W0ihL2sj7pYin2iY1gavS4W-yPswjKmrb6-ROwHgEOscfeGGLmUihzoV6vy9KvTJ9ytnIPqh-K94UsShUJ0-KgsY4_eWyUwx4IYpYaJkPeUVd4ni_1eZMBy6-hPr3n39DES_kXfnv3MJOiZZj0I-GJXw99WBV7xhl7KZcFKyMXYnszyboV8Xi2iZqHglvEoYRjKLvOlEq2j4pJoMRVfBB8oIOZm6uyCaOnyuWuE_Lg1HeuNMnHddTm8gexDAfwj3WYHkJazsN1PZVhPZVImyKwCNM.TOYk3lw2SKYamQL7XiLXlg",
   "status": "SUCCESS",
   "statusDescription": "SUCCESS",
   "mediaType": "EMAIL",
   "mediaAddress": "ale******@example.com"
}
```

### Verification OTP v3: Generate passcode in text using card number

Retrieves a one time passcode for cardholder's verification. Generated passcode expires in 10 mins. Passcode is delivered on selected media address.

#### Request

**HTTP Method:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/fraud/v3/verification/otp

```
{
   "cardNumber": "4000100020003000",
   "memberNumber": "0",
   "mediaType": "TEXT",
   "mediaAddress": "1005550001"
}
```

#### Response

**HTTP Code:** 201 Created

```
{
   "cardNumber": "400010XXXXXX3000",
   "memberNumber": "0",
   "otpId": "1234567",
   "status": "SUCCESS",
   "statusDescription": "SUCCESS",
   "mediaType": "TEXT",
   "mediaAddress": "1005550001"
}
```

### Verification OTP v3: Generate passcode in text using NTT

Retrieves a one time passcode for cardholder's verification. Generated passcode expires in 10 mins. Passcode is delivered on selected media address.

#### Request

**HTTP Method:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/fraud/v3/verification/otp

```
{
   "nonTransToken": "piUVBJKZGfks4000",
   "jwtTokenFlag": false,
   "mediaType": "TEXT",
   "mediaAddress": "1005550001"
}
```

#### Response

**HTTP Code:** 201 Created

```
{
    "cardNumber": "400020XXXXXX4000",
    "nonTransToken": "piUVBJKZGfks4000",
    "memberNumber": "0",
    "otpId": "1234567",
    "status": "SUCCESS",
    "statusDescription": "SUCCESS",
    "mediaType": "TEXT",
    "mediaAddress": "******0001"
}
```

### Verification OTP v3: Generate passcode in text using card number with JWT

Retrieves a one time passcode for cardholder's verification. Generated passcode expires in 10 mins. Passcode is delivered on selected media address.

#### Request

**HTTP Method:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/fraud/v3/verification/otp

```
{
   "cardNumber": "4000200030004000",
   "memberNumber": "0",
   "jwtTokenFlag": true,
   "mediaType": "TEXT",
   "mediaAddress": "1005550001"
}
```

#### Response

**HTTP Code:** 201 Created

```
{
    "cardNumber": "400020XXXXXX4000",
    "nonTransToken": "piUVBJKZGfks4000",
    "memberNumber": "0",
    "otpId": "1234567",
    "jwt": "eyJ0eXAiOiJKV1QiLCJlbmMiOiJBMTI4R0NNIiwiYWxnIjoiUlNBLU9BRVAtMjU2In0.WrliT8nLQOTRnXldrYj0brobAyi6M7-U8_iHovmTH1VAZksc4mOGQCfaSx-sbDNjdkpeznR8lU1sHOX26qom94jBO6uePEw1cBbTHLpOSEPDYiWS6SzTgxguF7zT2g5Ui1HHi2GKgPtH5L0XC_QqP5TIs3A15fqpAnvMaSwW9O_GDRzxnsUDCgEZCkwQOuEpWYDbM7r7yKrfAlkWKOHOlZuUtvJvg3k8p-1qwKpuGexhWXQdgKsWphBWbMzbindOIefIo4VTrOVMxWOdP_bLNId0E0CBLxSpRHX1u3EeAjUykUdifT2CP4bb6kbJf4pp0dRc_uPZGJLj7faPyq6UeQ.zTLJMNI8bjGh-KBy.FW0W0ihL2sj7pYin2iY1gavS4W-yPswjKmrb6-ROwHgEOscfeGGLmUihzoV6vy9KvTJ9ytnIPqh-K94UsShUJ0-KgsY4_eWyUwx4IYpYaJkPeUVd4ni_1eZMBy6-hPr3n39DES_kXfnv3MJOiZZj0I-GJXw99WBV7xhl7KZcFKyMXYnszyboV8Xi2iZqHglvEoYRjKLvOlEq2j4pJoMRVfBB8oIOZm6uyCaOnyuWuE_Lg1HeuNMnHddTm8gexDAfwj3WYHkJazsN1PZVhPZVImyKwCNM.TOYk3lw2SKYamQL7XiLXlg",
    "status": "SUCCESS",
    "statusDescription": "SUCCESS",
    "mediaType": "TEXT",
    "mediaAddress": "******0001"
}
```

### Verification CardAuthInfo v1: Search using card number, member number, OTP and JWT

Retrieves CV2 and expiration date for given card by validating OTP and JWT.
Note : This API should be used in the order of -

1. /v3/verification/search
2. /v3/verification/otp
3. /v1/verification/cardAuthInfo.

#### Request

**HTTP Method:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/fraud/v1/verification/cardAuthInfo

```
{
   "cardNumber": "4000200030004000",
   "memberNumber": "0",
   "otp": "123456",
   "jwt": "eyJ0eXAiOiJKV1QiLCJlbmMiOiJBMTI4R0NNIiwiYWxnIjoiUlNBLU9BRVAtMjU2In0.WrliT8nLQOTRnXldrYj0brobAyi6M7-U8_iHovmTH1VAZksc4mOGQCfaSx-sbDNjdkpeznR8lU1sHOX26qom94jBO6uePEw1cBbTHLpOSEPDYiWS6SzTgxguF7zT2g5Ui1HHi2GKgPtH5L0XC_QqP5TIs3A15fqpAnvMaSwW9O_GDRzxnsUDCgEZCkwQOuEpWYDbM7r7yKrfAlkWKOHOlZuUtvJvg3k8p-1qwKpuGexhWXQdgKsWphBWbMzbindOIefIo4VTrOVMxWOdP_bLNId0E0CBLxSpRHX1u3EeAjUykUdifT2CP4bb6kbJf4pp0dRc_uPZGJLj7faPyq6UeQ.zTLJMNI8bjGh-KBy.FW0W0ihL2sj7pYin2iY1gavS4W-yPswjKmrb6-ROwHgEOscfeGGLmUihzoV6vy9KvTJ9ytnIPqh-K94UsShUJ0-KgsY4_eWyUwx4IYpYaJkPeUVd4ni_1eZMBy6-hPr3n39DES_kXfnv3MJOiZZj0I-GJXw99WBV7xhl7KZcFKyMXYnszyboV8Xi2iZqHglvEoYRjKLvOlEq2j4pJoMRVfBB8oIOZm6uyCaOnyuWuE_Lg1HeuNMnHddTm8gexDAfwj3WYHkJazsN1PZVhPZVImyKwCNM.TOYk3lw2SKYamQL7XiLXlg"
}
```

#### Response

**HTTP Code:** 200 OK

```
{
   "cardNumber": "4000200030004000",
   "CV2": "282",
   "expirationDate": "10/28"
}
```

### Verification CardAuthInfo v1: Search using card number, OTP and JWT

Retrieves CV2 and expiration date for given card by validating OTP and JWT.
Note : This API should be used in the order of -

1. /v3/verification/search
2. /v3/verification/otp
3. /v1/verification/cardAuthInfo.

#### Request

**HTTP Method:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/fraud/v1/verification/cardAuthInfo

```
{
   "cardNumber": "4000200030004000",
   "otp": "123456",
   "jwt": "eyJ0eXAiOiJKV1QiLCJlbmMiOiJBMTI4R0NNIiwiYWxnIjoiUlNBLU9BRVAtMjU2In0.WrliT8nLQOTRnXldrYj0brobAyi6M7-U8_iHovmTH1VAZksc4mOGQCfaSx-sbDNjdkpeznR8lU1sHOX26qom94jBO6uePEw1cBbTHLpOSEPDYiWS6SzTgxguF7zT2g5Ui1HHi2GKgPtH5L0XC_QqP5TIs3A15fqpAnvMaSwW9O_GDRzxnsUDCgEZCkwQOuEpWYDbM7r7yKrfAlkWKOHOlZuUtvJvg3k8p-1qwKpuGexhWXQdgKsWphBWbMzbindOIefIo4VTrOVMxWOdP_bLNId0E0CBLxSpRHX1u3EeAjUykUdifT2CP4bb6kbJf4pp0dRc_uPZGJLj7faPyq6UeQ.zTLJMNI8bjGh-KBy.FW0W0ihL2sj7pYin2iY1gavS4W-yPswjKmrb6-ROwHgEOscfeGGLmUihzoV6vy9KvTJ9ytnIPqh-K94UsShUJ0-KgsY4_eWyUwx4IYpYaJkPeUVd4ni_1eZMBy6-hPr3n39DES_kXfnv3MJOiZZj0I-GJXw99WBV7xhl7KZcFKyMXYnszyboV8Xi2iZqHglvEoYRjKLvOlEq2j4pJoMRVfBB8oIOZm6uyCaOnyuWuE_Lg1HeuNMnHddTm8gexDAfwj3WYHkJazsN1PZVhPZVImyKwCNM.TOYk3lw2SKYamQL7XiLXlg"
}
```

#### Response

**HTTP Code:** 200 OK

```
{
   "cardNumber": "4000200030004000",
   "CV2": "282",
   "expirationDate": "10/28"
}
```

### Verification CardAuthInfo v1: Search using OTP and JWT

Retrieves CV2 and expiration date for given card by validating OTP and JWT.
Note : This API should be used in the order of -

1. /v3/verification/search
2. /v3/verification/otp
3. /v1/verification/cardAuthInfo.

#### Request

**HTTP Method:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/fraud/v1/verification/cardAuthInfo

```
{
   "otp": "123456",
   "jwt": "eyJ0eXAiOiJKV1QiLCJlbmMiOiJBMTI4R0NNIiwiYWxnIjoiUlNBLU9BRVAtMjU2In0.WrliT8nLQOTRnXldrYj0brobAyi6M7-U8_iHovmTH1VAZksc4mOGQCfaSx-sbDNjdkpeznR8lU1sHOX26qom94jBO6uePEw1cBbTHLpOSEPDYiWS6SzTgxguF7zT2g5Ui1HHi2GKgPtH5L0XC_QqP5TIs3A15fqpAnvMaSwW9O_GDRzxnsUDCgEZCkwQOuEpWYDbM7r7yKrfAlkWKOHOlZuUtvJvg3k8p-1qwKpuGexhWXQdgKsWphBWbMzbindOIefIo4VTrOVMxWOdP_bLNId0E0CBLxSpRHX1u3EeAjUykUdifT2CP4bb6kbJf4pp0dRc_uPZGJLj7faPyq6UeQ.zTLJMNI8bjGh-KBy.FW0W0ihL2sj7pYin2iY1gavS4W-yPswjKmrb6-ROwHgEOscfeGGLmUihzoV6vy9KvTJ9ytnIPqh-K94UsShUJ0-KgsY4_eWyUwx4IYpYaJkPeUVd4ni_1eZMBy6-hPr3n39DES_kXfnv3MJOiZZj0I-GJXw99WBV7xhl7KZcFKyMXYnszyboV8Xi2iZqHglvEoYRjKLvOlEq2j4pJoMRVfBB8oIOZm6uyCaOnyuWuE_Lg1HeuNMnHddTm8gexDAfwj3WYHkJazsN1PZVhPZVImyKwCNM.TOYk3lw2SKYamQL7XiLXlg"
}

```

#### Response

**HTTP Code:** 200 OK

```
{
   "cardNumber": "4000200030004000",
   "CV2": "282",
   "expirationDate": "10/28"
}
```

### Verification Validate v2: Using card number

Validates generated passcode sent to Cardholder on chosen media address. Note passcode expires in 10 minutes.

#### Request

**HTTP Method:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/fraud/v2/verification/validation

```
{
    "cardNumber": "4000200030004000",
    "memberNumber": "0",
    "otpId": "******0001",
    "otpPassCode": "123456"
}

```

#### Response

**HTTP Code:** 200 OK

```
{
    "cardNumber": "400020XXXXXX4000",
    "memberNumber": "0",
    "cardType": "DEBIT",
    "otpId": "1816063",
    "status": "SUCCESS",
    "statusDescription": "SUCCESS"
}
```

### Verification History v1: Search for a selected cardholder

Retrieves verification history details for a given card number

#### Request

**HTTP Method:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/fraud//v1/verification/history

```
{
   "cardNumber": "4000200030004000",
   "memberNumber": "0",
   "fromDate": "1989-08-24",
   "toDate": "1990-08-24",
   "pageLimit": 50,
   "pageOffset": 1
}

```

#### Response

**HTTP Code:** 200 OK

```
{
   "verificationHistory": [
      {
         "dateTime": "2021-07-20T07:00:00Z",
         "mediaType": "TEXT",
         "mediaAddress": "1005550001",
         "contactStatus": "SENT",
         "validationStatus": "VALID",
         "updatedByUser": "smith"
      }
   ]
}
```
