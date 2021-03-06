# Test Cases
<!-- theme: info -->
> #### Note to Unregistered Users
>
> The unregistered user journey enables developers to access a range of Standard Bank Platform APIs on Banking Hub. Currently we are working on developing a registered user journey, therefore all nuances regarding using Banking Hub APIs to our different platforms may not be available on this portal. <br> Once registration is enabled on Developer Studio, you can sign up to obtain credentials along with the instructions to integrate Banking Hub APIs with our banking platforms. Additionally, you get access to our Sandbox environment to test APIs or may choose to test <a href="?path=docs/getting-started/make-your-first-api-call.md#using-third-party-api-testing-tools" > Using Third-party API Testing Tools</a>.


Register to the Fiserv Developer Studio to test the APIs in test and live environments. However, registration is not required to learn about our API integration process and test the APIs in API Explorer.

## Activations
To validate and deploy Fiserv banking APIs into production, create an account with Fiserv Developer Studio to obtain credentials for sandbox testing and live environments.


### Activate Card: Unactivated credit card
<!-- theme: info -->
> This case activates a card.

<span style="font-size:25px;">**Request**</span>

#### HTTP METHOD: PUT

**Target URL:** [https://card-sandbox.api.fiservapps.com/cs/cards/v1/cards/activations](https://card-sandbox.api.fiservapps.com/cs/cards/v1/cards/activations)

		
	{
		"cardNumber": "4000100020003001"
	}
		

<font size="5">**Response** </font>

HTTP Code: 200

	{
		"cardType": "CREDIT",
		"cardActivationStatus": "ACTIVATED"
	}
		

### Activate Card: Unactivated debit card

This case activates a debit card.

<font size="5">**Request** </font>

**HTTP METHOD:** PUT

**Target URL:** [https://card-sandbox.api.fiservapps.com/cs/cards/v1/cards/activations](https://card-sandbox.api.fiservapps.com/cs/cards/v1/cards/activations)

		
	{
		"cardNumber": "4000100020003000"
	}
		

<font size="5">**Response** </font>

HTTP Code: 200

		
	{
		"cardType": "DEBIT",
		"activationRequiredByDate": "2021-10-31",
		"availableForUseDate": "2021-07-26",
		"cardActivationDate": "2021-09-23",
		"cardActivationStatus": "ACTIVATED",
		"lastActivationAttemptDate": "2021-09-23",
		"activationMethod": "OPERATOR\_ACTIVATE",
		"numberOfAttempts": "0",
		"verificationCallerID": "9900020"
	}
		

#### Search for Card Activation Details: Unactivated credit card

This case demonstrates a case when the card is not activated.

<font size="5">**Request** </font>

**HTTP METHOD:** POST

**Target URL:** [https://card-sandbox.api.fiservapps.com/cs/cards/v1/cards/activations/search](https://card-sandbox.api.fiservapps.com/cs/cards/v1/cards/activations/search)

		
	{
		"cardNumber": "4000100020003001"
	}
		

<font size="5">**Response** </font>

HTTP Code: 200
		
	{
		"cardType": "CREDIT",
		"cardActivationStatus": "ACTIVATION\_REQUIRED"
	}
		

#### Search for Card Activation Details: Activated credit card

This case demonstrates a case when the card is activated.

<font size="5">**Request** </font>

**HTTP METHOD:** POST

**Target URL:** [https://card-sandbox.api.fiservapps.com/cs/cards/v1/cards/activations/search](https://card-sandbox.api.fiservapps.com/cs/cards/v1/cards/activations/search)

		
	{
		"cardNumber": "4000200030004001"
	}
		

<font size="5">**Response** </font>

HTTP Code: 200

		
	{
		"cardType": "CREDIT",
		"cardActivationStatus": "NO\_ACTIVATION\_REQUIRED"
	}
		

#### Search for Card Activation Details: Unactivated debit card

This case demonstrates a case when the debit card is unactivated.

<font size="5">**Request** </font>

**HTTP METHOD:** POST

**Target URL:** [https://card-sandbox.api.fiservapps.com/cs/cards/v1/cards/activations/search](https://card-sandbox.api.fiservapps.com/cs/cards/v1/cards/activations/search)

		
	{
		"cardNumber": "4000100020003000"
	}
		

<font size="5">**Response** </font>

HTTP Code: 200

		
	{
		"cardType": "DEBIT",
		"activationRequiredByDate": "2021-10-31",
		"availableForUseDate": "2021-07-26",
		"cardActivationStatus": "NOT\_ACTIVATED",
		"numberOfAttempts": "0"
	}
		

#### Search for Card Activation Details: Activated debit card

This case demonstrates a case when the debit card is activated.

<font size="5">**Request** </font>

**HTTP METHOD:** POST

**Target URL:** [https://card-sandbox.api.fiservapps.com/cs/cards/v1/cards/activations/search](https://card-sandbox.api.fiservapps.com/cs/cards/v1/cards/activations/search)

		
	{
		"cardNumber": "4000200030004000"
	}
		

<font size="5">**Response** </font>

HTTP Code: 200

		
	{
		"cardType": "DEBIT",
		"activationRequiredByDate": "2022-12-31",
		"cardActivationDate": "2021-09-21",
		"cardActivationStatus": "ACTIVATED",
		"lastActivationAttemptDate": "2021-09-21",
		"activationMethod": "OPERATOR\_ACTIVATE",
		"numberOfAttempts": "1"
	}


## Details

This section describes a standard structure of request and response message of Banking Hub RESTful APIs. 

### Cardholder Search with Full Record

Retrieve cardholder information based on other commonly known information

<font size="5">**Request** </font>

**HTTP METHOD:** POST

**Target URL:** [https://card-sandbox.api.fiservapps.com/cs/cards/v1/cardholders/search](https://card-sandbox.api.fiservapps.com/cs/cards/v1/cardholders/search)

	{
		"cardNumber": "4000200030004000",
		"ssnOrTaxid": "987001234",
		"accNumber": "123456789",
		"phone": "0005550001",
		"emailAddress": "alexsmith@email.com",
		"dateOfBirth": "10/1/52",
		"postalCode": "12345",
		"lastFourCardNumber": "4000",
		"lastFourAccNumber": "6789",
		"lastName": "Smith"
	}
		

<font size="5">**Response** </font>

HTTP Code: 200

		
	{
		"cardholderCardsDetails": \[
		{
		"cardholderDetails": {
			"cardholderName": "Alex Smith"
		},
		"cards": \[
			{
			"cardNumber": "4000200030004000",
			"accountNumber": \[
				"123456789"
			\],
			"cardMemberNumber": "001",
			"cardStatus": "NORMAL",
			"cardType": "CREDIT",
			"association": "PRIMARY",
			"postalCode": "12345",
			"phone": "0005550001",
			"dateOfBirth": "10/1/52",
			"emailAddress": "alexsmith@email.com"
			}
		\]
		}
		\]
	}