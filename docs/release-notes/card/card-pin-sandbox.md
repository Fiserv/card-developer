# Test Cases

<span style="color:#ff6600;">**Card API Endpoints**</span>

When testing these endpoints, please use the test cases and test data from the Sandbox.

## PIN

### Debit PIN v1: Obtain JWT token using card number

To select a PIN, you must supply the JWT returned by this operation. The JWT changes each time you make this request.

#### Request

**HTTP Method:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v1/cards/token

```
    {
        "cardNumber": "4000200030004000"
    }
```

#### Response

**HTTP Code:** 200 OK

```
    {
        "jwt": "eyJ0eXAiOiJKV1QiLCJlbmMiOiJBMTI4R0NNIiwiYWxnIjoiUlNBLU9BRVAtMjU2In0.WrliT8nLQOTRnXldrYj0brobAyi6M7-U8_iHovmTH1VAZksc4mOGQCfaSx-sbDNjdkpeznR8lU1sHOX26qom94jBO6uePEw1cBbTHLpOSEPDYiWS6SzTgxguF7zT2g5Ui1HHi2GKgPtH5L0XC_QqP5TIs3A15fqpAnvMaSwW9O_GDRzxnsUDCgEZCkwQOuEpWYDbM7r7yKrfAlkWKOHOlZuUtvJvg3k8p-1qwKpuGexhWXQdgKsWphBWbMzbindOIefIo4VTrOVMxWOdP_bLNId0E0CBLxSpRHX1u3EeAjUykUdifT2CP4bb6kbJf4pp0dRc_uPZGJLj7faPyq6UeQ.zTLJMNI8bjGh-KBy.FW0W0ihL2sj7pYin2iY1gavS4W-yPswjKmrb6-ROwHgEOscfeGGLmUihzoV6vy9KvTJ9ytnIPqh-K94UsShUJ0-KgsY4_eWyUwx4IYpYaJkPeUVd4ni_1eZMBy6-hPr3n39DES_kXfnv3MJOiZZj0I-GJXw99WBV7xhl7KZcFKyMXYnszyboV8Xi2iZqHglvEoYRjKLvOlEq2j4pJoMRVfBB8oIOZm6uyCaOnyuWuE_Lg1HeuNMnHddTm8gexDAfwj3WYHkJazsN1PZVhPZVImyKwCNM.TOYk3lw2SKYamQL7XiLXlg"
    }
```

### Debit PIN v1: Obtain JWT token using NTT

To select a PIN, you must supply the JWT returned by this operation. The JWT changes each time you make this request.

#### Request

**HTTP Method:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v1/cards/token

```
{
     "nonTransToken": "piUVBJKZGfks4000"
  }
```

#### Response

**HTTP Code:** 200 OK

```
{
     "jwt": "eyJ0eXAiOiJKV1QiLCJlbmMiOiJBMTI4R0NNIiwiYWxnIjoiUlNBLU9BRVAtMjU2In0.XU56gXVBUVLIH83fDZ_uUNj-C4f2UpGnTbP0kHLKPFEfOjn0vYP-TCcV0Cy8Q5t0bRNxE_eI6LIRT-p-dL-lQkv5Sx1GXVvsC9L_vFBzz4QU2DbkpwVjVin088uA23OV6EhylCgiwf8Yswu_1Pu8jFyvaFJUIiEvwZkFbHX73IE6fJanhMjgn_4Eo42CVdGgmzYJtfDQ9wkbAW3w3D2C2dkvzQiYeiTTCkRdzIxEeTDcN9NSM_vwElz_zO5ONExRa_2LTPlQPcen9meot8Dzlcqlz0i4Jo2xtLmkG6bA2uQzbAID4dRujhaOhCoW-GodyOvRCjOqFNYHX8tVLBio7w.oDrfGhbXOLDEWBNA.avKcJYf5i_zP2fov70cqzEW0B2znGvIF2zdEp4bkRtSDJrRBKfcbJeEaEakLZaItLDAlXz6ANJLUntsCpyrQ0Jm4nWfjRgtVmWFSUF3TvgLUH8_Pd5e8yZsI_TuJCPDMHSIt8XEkrpyRwsQT8BgUIU-iAuGe70KoFK5Cr5qvGNLgKJDIwSzlaZma-z9HFxTs6m8hKM3_5YMK5AUGsSpsy8Fb6QNhE6enfjc3GeZei1_dwhJC3Cfd8NkeNpH8AkYWGrY_ZvyZ1YAfFdgXeasCAA.yxrJMUH91uZWejU5N1VDRQ"
  }
```

### Debit PIN v1: Reset PIN attempts using card number

Reset the number of PIN attempts to zero for the selected cardholder record.

#### Request

**HTTP METHOD**: POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v1/cards/pinAttempts

```
{
      "cardNumber": "4000200030004000",
      "memberNumber":"0"
  }
```

#### Response

**HTTP Code:** 204 No Content

### Debit PIN v1: Reset PIN attempts using NTT

Reset the number of PIN attempts to zero for the selected cardholder record.

#### Request

**HTTP Method:** PUT

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v1/cards/pinAttempts

```
{
      "nonTransToken": "piUVBJKZGfks4000"
  }
```

#### Response

**HTTP Code:** 204 No Content

### Debit PIN v1: Select a PIN

Provide the selected PIN and include the JWT card token.The JWT token must be used within 15 minutes.

#### Request

**HTTP Method:** PATCH

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v1/cards/pin

```
{
    "pin": "3578",
    "jwt": "eyJ0eXAiOiJKV1QiLCJlbmMiOiJBMTI4R0NNIiwiYWxnIjoiUlNBLU9BRVAtMjU2In0.XU56gXVBUVLIH83fDZ_uUNj-C4f2UpGnTbP0kHLKPFEfOjn0vYP-TCcV0Cy8Q5t0bRNxE_eI6LIRT-p-dL-lQkv5Sx1GXVvsC9L_vFBzz4QU2DbkpwVjVin088uA23OV6EhylCgiwf8Yswu_1Pu8jFyvaFJUIiEvwZkFbHX73IE6fJanhMjgn_4Eo42CVdGgmzYJtfDQ9wkbAW3w3D2C2dkvzQiYeiTTCkRdzIxEeTDcN9NSM_vwElz_zO5ONExRa_2LTPlQPcen9meot8Dzlcqlz0i4Jo2xtLmkG6bA2uQzbAID4dRujhaOhCoW-GodyOvRCjOqFNYHX8tVLBio7w.oDrfGhbXOLDEWBNA.avKcJYf5i_zP2fov70cqzEW0B2znGvIF2zdEp4bkRtSDJrRBKfcbJeEaEakLZaItLDAlXz6ANJLUntsCpyrQ0Jm4nWfjRgtVmWFSUF3TvgLUH8_Pd5e8yZsI_TuJCPDMHSIt8XEkrpyRwsQT8BgUIU-iAuGe70KoFK5Cr5qvGNLgKJDIwSzlaZma-z9HFxTs6m8hKM3_5YMK5AUGsSpsy8Fb6QNhE6enfjc3GeZei1_dwhJC3Cfd8NkeNpH8AkYWGrY_ZvyZ1YAfFdgXeasCAA.yxrJMUH91uZWejU5N1VDRQ"
}
```

#### Response

**HTTP Code:** 204 No Content

### Debit PIN v1:Set PIN offset using card number

Update the PIN Offset for the selected cardholder record.

#### Request

**HTTP Method:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v1/cards/pinOffset

```
{
   "cardNumber": "4000200030004000",
   "memberNumber": "0",
   "pinOffset": "1234"
}
```

#### Response

**HTTP Code:** 204 No Content

### Debit PIN v1: Set PIN offset using NTT

Update the PIN Offset for the selected cardholder record.

#### Request

**HTTP Method:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v1/cards/pinOffset

```
{
   "nonTransToken": "piUVBJKZGfks4000",
   "pinOffset": "1234"
}
```
