# Test Cases

<span style="color:#ff6600;">**Reward API endpoints**</span>

## uChoose Rewards

### uChoose Rewards v1: Retrieve SSO Link

Retrieve SSO link for UChoose rewards.

#### Request

**HTTP METHOD:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/uChooseRewards/v1/sso-url
```
{
 "client" : {
    "id":"11122203",
    "applicationName":"CM",
    "vendorName":"ITI",
    "auditId":"123456"
 },
 "rewardsKeyInfo" : {
    "cardNumber":"5004065676691",
    "accountNumber":"3445454545",
    "useMultiAuth":false
 },
 "email":"sandbox.app@fiserv.com"
}
```
#### Response

**HTTP code:** 200 OK

```
{
 "destURL": "https://uat.uchooserewards.com/members/ssoredirect.php?sid=40XpKlKoY837589&xmembid=32380882&redoip=y"
}
```

### uChoose Rewards v1: Add cardholder rewards points

Add reward points for cardholder.

#### Request

**HTTP METHOD:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/uChooseRewards/v1/addpoints

```
{
   "client": {
      "id": "11122203",
      "applicationName": "CM",
      "vendorName": "ITI",
      "auditId": "Saint Michael"
   },
   "rewardsKeyInfo": {
      "cardNumber": "5004065676691",
      "accountNumber": "3445454545",
      "useMultiAuth": "false"
   },
   "addPoints": {
      "points": "19",
      "description": "Add",
      "vest": "true"
   }
}
```
#### Response

**HTTP code:** 200 OK

```
{
   "pointsInfo": {
      "pointsToDate": 50,
      "availablePoints": 10,
      "vestedPoints": 35,
      "ccName": "A1",
      "ccType": "MASTERCARD",
      "ccStatus": true,
      "earnStart": "2017-10-19",
      "earnEnd": "2050-12-31"
   },
   "scoreId": "78901"
}
```

### uChoose Rewards v1: Redeem cardholder rewards points

Redeem reward points for cardholder.

#### Request

**HTTP METHOD:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/uChooseRewards/v1/redeempoints

```
{
 "client": {
  "id": "11122203",
  "applicationName": "CM",
  "vendorName": "ITI",
  "auditId": "Saint Michael"
  },
 "rewardsKeyInfo": {
  "cardNumber": "5004065676691",
  "accountNumber": "3445454545",
  "useMultiAuth": "false"
  },
 "redeemPoints": {
  "points": "19",
  "description": "b",
  "reference": "B"
  }
}
```
#### Response

**HTTP code:** 200 OK

```
{
 "pointsInfo": {
  "pointsToDate": 50,
  "availablePoints": 10,
  "vestedPoints": 35,
  "ccName": "A1",
  "ccType": "MASTERCARD",
  "ccStatus": true,
  "earnStart": "2017-10-19",
  "earnEnd": "2050-12-31"
 },
 "redeemID": "78901"
}
```

### uChoose Rewards v1: Retrieve cardholder rewards points

Retrieve reward points for cardholder.

#### Request

**HTTP METHOD:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/uChooseRewards/v1/points
```
{
 "client": {
    "id":11122203,
    "applicationName":"CM",
    "vendorName":"ITI",
    "auditId":"123456"
  },
 "rewardsKeyInfo": {
    "cardNumber":"5004065676691",
    "accountNumber":"3445454545",
    "useMultiAuth":true
  }
}

```
#### Response

**HTTP code:** 200 OK

```
{
 "pointsInfo": {
  "pointsToDate": 0,
  "availablePoints": 0,
  "vestedPoints": 0,
  "ccName": "A1",
  "ccType": "MASTERCARD",
  "ccStatus": true,
  "earnStart": "2017-10-19",
  "earnEnd": "2050-12-31"
 }
}
```
