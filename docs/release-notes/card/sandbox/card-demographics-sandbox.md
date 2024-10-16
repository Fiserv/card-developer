# Test Cases

<span style="color:#ff6600;">**Card API Endpoints**</span>

When testing these endpoints, please use the test cases and test data from the Sandbox.

## Demographics

### Credit Demographics v4: Search using card number

This case retrieves the demographics of a cardholder using a card number.

#### Request

**HTTP Method:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com /cs/cards/v4/cards/cardholders/demographics/search

```
{
      "cardNumber": "4000200030004001"
  }
```

#### Response

**HTTP Code:** 200 OK

```
{
      "cardholderDemographics": [
        {
            "cardNumber": "400020XXXXXX4001",
            "memberNumber": "0",
            "tcpa": [
                {
                    "tcpaType": "ENFACT",
                    "mediaType": "VOICE",
                    "revoked": true,
                    "lastUpdatedDateTime": "2022-09-26T15:50:45Z",
                    "lastUpdatedBy": "Jesse Doe"
                }
            ],
            "contact": {
                "emailAddress": "alexsmith@example.com",
                "homePhone": "1005550001",
                "workPhone": "1005550001",
                "cellPhone": "1005550001",
                "textAddress": "1005550001",
                "enfact": {
                    "languagePreference": "ENGLISH"
                }
            },
            "preferences": {
                "homePhone": {
                    "enfact": {
                        "consentForVoice": true,
                        "consentForText": true
                    },
                    "stepUp": {
                        "consentForVoice": true,
                        "consentForText": true
                    }
                },
                "workPhone": {
                    "enfact": {
                        "consentForVoice": true,
                        "consentForText": true
                    },
                    "stepUp": {
                        "consentForVoice": true,
                        "consentForText": true
                    }
                },
                "cellPhone": {
                    "enfact": {
                        "consentForVoice": true,
                        "consentForText": true
                    },
                    "stepUp": {
                        "consentForVoice": true,
                        "consentForText": true
                    }
                },
                "textAddress": {
                    "enfact": {
                        "consentForText": true
                    },
                    "stepUp": {
                        "consentForText": true
                    }
                },
                "emailAddress": {
                    "enfact": {
                        "consentForEmail": true
                    },
                    "stepUp": {
                        "consentForEmail": true
                    }
                }
            },
            "creditCardholderAddress": [
                {
                    "addressType": "BILLING",
                    "addressLine1": "123 Any Street",
                    "addressLine2": "123 Any Lane",
                    "addressLine3": "123 Any Lane",
                    "addressLine4": "123 Any Lane",
                    "city": "Newark",
                    "stateCode": "NJ",
                    "zipCode": "12345",
                    "countryCode": "USA",
                    "categoryCode": "PERMANENT",
                    "beginDate": "2021-08-03",
                    "endDate": "2021-08-03"
                }
            ]
        }
    ]
  }
```

### Credit Demographics v3: Update cardholder contact information using card number

This case updates the contact information using a card number.

#### Request

**HTTP Method**: PATCH

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v3/cardholders/contact

```
{
       "cardNumber": "4000200030004001",
            "tcpa": [
                {
                    "tcpaType": "ENFACT",
                    "mediaType": "VOICE",
                    "revoked": true
                }
            ],
            "contact": {
                "emailAddress": "alexsmith@example.com",
                "homePhone": "1005550001",
                "workPhone": "1005550001",
                "cellPhone": "1005550001",
                "textAddress": "1005550001",
                "enfact": {
                    "languagePreference": "ENGLISH"
                }
            },
            "preferences": {
                "homePhone": {
                    "enfact": {
                        "consentForVoice": true,
                        "consentForText": true
                    },
                    "stepUp": {
                        "consentForVoice": true,
                        "consentForText": true
                    }
                },
                "workPhone": {
                    "enfact": {
                        "consentForVoice": true,
                        "consentForText": true
                    },
                    "stepUp": {
                        "consentForVoice": true,
                        "consentForText": true
                    }
                },
                "cellPhone": {
                    "enfact": {
                        "consentForVoice": true,
                        "consentForText": true
                    },
                    "stepUp": {
                        "consentForVoice": true,
                        "consentForText": true
                    }
                },
                "textAddress": {
                    "enfact": {
                        "consentForText": true
                    },
                    "stepUp": {
                        "consentForText": true
                    }
                },
                "emailAddress": {
                    "enfact": {
                        "consentForEmail": true
                    },
                    "stepUp": {
                        "consentForEmail": true
                    }
                }
            }
  }
```

#### Response

**HTTP Code:** 204 No Content

### Credit Demographics v3: Update cardholder address using card number

This case updates the address information using a card number.

#### Request

**HTTP Method:** PATCH

**Target URL:** https://card-sandbox.api.fiservapps.com /cs/cards//v3/cardholders/address

```
{
      "cardNumber": "4000200030004001",
      "creditCardholderAddress": [
          {
              "addressType": "PLASTIC",
              "addressLine1": "123 Any Street",
              "addressLine2": "123 Any Lane",
              "addressLine3": "123 Any Lane",
              "addressLine4": "123 Any Lane",
              "city": "Newark",
              "countryCode": "USA",
              "stateCode": "NJ",
              "zipCode": "12345",
              "isValidAddress": "Yes",
              "beginDate": "2023-03-01",
              "endDate": "2023-03-31",
              "categoryCode": "TEMPORARY"
          }
      ]
  }
```

#### Response

**HTTP Code:** 204 No Content

### Debit Demographics v4: Search using card number

This case retrieves the demographics of a cardholder using a card number.

#### Request

**HTTP Method:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v4/cards/cardholders/demographics/search

```
{
      "cardNumber": "4000200030004000",
      "memberNumber": "0"
  }
```

#### Response

**HTTP Code:** 200 OK

      "cardholderDemographics": [
          {
              "cardNumber": "400020XXXXXX4000",
              "nonTransToken": "piUVBJKZGfks4000",
              "memberNumber": "0",
              "tcpa": [
                  {
                      "tcpaType": "ENFACT",
                      "mediaType": "VOICE",
                      "revoked": true,
                      "lastUpdatedDateTime": "2022-09-26T15:50:45Z",
                      "lastUpdatedBy": "Jesse Doe"
                  }
              ],
              "contact": {
                  "emailAddress": "alexsmith@example.com",
                  "homePhone": "1005550001",
                  "workPhone": "1005550001",
                  "cellPhone": "1005550001",
                  "textAddress": "1005550001",
                  "enfact": {
                      "languagePreference": "ENGLISH"
                  }
              },
              "preferences": {
                  "homePhone": {
                      "enfact": {
                          "consentForVoice": true,
                          "consentForText": true
                      },
                      "stepUp": {
                          "consentForVoice": true,
                          "consentForText": true
                      }
                  },
                  "workPhone": {
                      "enfact": {
                          "consentForVoice": true,
                          "consentForText": true
                      },
                      "stepUp": {
                          "consentForVoice": true,
                          "consentForText": true
                      }
                  },
                  "cellPhone": {
                      "enfact": {
                          "consentForVoice": true,
                          "consentForText": true
                      },
                      "stepUp": {
                          "consentForVoice": true,
                          "consentForText": true
                      }
                  },
                  "textAddress": {
                      "enfact": {
                          "consentForText": true
                      },
                      "stepUp": {
                          "consentForText": true
                      }
                  },
                  "emailAddress": {
                      "enfact": {
                          "consentForEmail": true
                      },
                      "stepUp": {
                          "consentForEmail": true
                      }
                  }
              },
              "debitCardholderAddress": [
                  {
                      "addressType": "PRIMARY",
                      "addressLine1": "123 Any Street",
                      "addressLine2": "123 Any Lane",
                      "city": "Newark",
                      "stateCode": "NJ",
                      "zipCode": "12345",
                      "countryCode": "USA",
                      "cardMailerIndicator": true,
                      "pinMailerIndicator": true
                  }
              ]
          }
      ]

### Debit Demographics v4: Search using NTT

This case retrieves the demographics of a cardholder using NTT.

#### Request

**HTTP Method:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v4/cards/cardholders/demographics/search

```
{
      "nonTransToken": "piUVBJKZGfks4000"
  }
```

#### Response

**HTTP Code:** 200 OK

```
{
      "cardholderDemographics": [
          {
              "cardNumber": "400020XXXXXX4000",
              "nonTransToken": "piUVBJKZGfks4000",
              "memberNumber": "0",
              "tcpa": [
                  {
                      "tcpaType": "ENFACT",
                      "mediaType": "VOICE",
                      "revoked": true,
                      "lastUpdatedDateTime": "2022-09-26T15:50:45Z",
                      "lastUpdatedBy": "Jesse Doe"
                  }
              ],
              "contact": {
                  "emailAddress": "alexsmith@example.com",
                  "homePhone": "1005550001",
                  "workPhone": "1005550001",
                  "cellPhone": "1005550001",
                  "textAddress": "1005550001",
                  "enfact": {
                      "languagePreference": "ENGLISH"
                  }
              },
              "preferences": {
                  "homePhone": {
                      "enfact": {
                          "consentForVoice": true,
                          "consentForText": true
                      },
                      "stepUp": {
                          "consentForVoice": true,
                          "consentForText": true
                      }
                  },
                  "workPhone": {
                      "enfact": {
                          "consentForVoice": true,
                          "consentForText": true
                      },
                      "stepUp": {
                          "consentForVoice": true,
                          "consentForText": true
                      }
                  },
                  "cellPhone": {
                      "enfact": {
                          "consentForVoice": true,
                          "consentForText": true
                      },
                      "stepUp": {
                          "consentForVoice": true,
                          "consentForText": true
                      }
                  },
                  "textAddress": {
                      "enfact": {
                          "consentForText": true
                      },
                      "stepUp": {
                          "consentForText": true
                      }
                  },
                  "emailAddress": {
                      "enfact": {
                          "consentForEmail": true
                      },
                      "stepUp": {
                          "consentForEmail": true
                      }
                  }
              },
              "debitCardholderAddress": [
                  {
                      "addressType": "PRIMARY",
                      "addressLine1": "123 Any Street",
                      "addressLine2": "123 Any Lane",
                      "city": "Newark",
                      "stateCode": "NJ",
                      "zipCode": "12345",
                      "countryCode": "USA",
                      "cardMailerIndicator": true,
                      "pinMailerIndicator": true
                  }
              ]
          }
      ]
  }
```

### Debit Demographics v3: Update cardholder contact information using NTT

This case updates the contact information using NTT.

#### Request

**HTTP Method:** PATCH

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v3/cardholders/contact

```
{
      "nonTransToken": "piUVBJKZGfks4000",
      "tcpa": [
          {
              "tcpaType": "ENFACT",
              "mediaType": "VOICE",
              "revoked": true
          }
      ],
      "contact": {
          "homePhone": "1005550001",
          "workPhone": "1005550001",
          "cellPhone": "1005550001",
          "textAddress": "1005550001",
          "enfact": {
              "languagePreference": "ENGLISH"
          }
      },
      "preferences": {
          "homePhone": {
              "enfact": {
                  "consentForVoice": true,
                  "consentForText": true
              },
              "stepUp": {
                  "consentForVoice": true,
                  "consentForText": true
              }
          },
          "workPhone": {
              "enfact": {
                  "consentForVoice": true,
                  "consentForText": true
              },
              "stepUp": {
                  "consentForVoice": true,
                  "consentForText": true
              }
          },
          "cellPhone": {
              "enfact": {
                  "consentForVoice": true,
                  "consentForText": true
              },
              "stepUp": {
                  "consentForVoice": true,
                  "consentForText": true
              }
          },
          "textAddress": {
              "enfact": {
                  "consentForText": true
              },
              "stepUp": {
                  "consentForText": true
              }
          },
          "emailAddress": {
              "enfact": {
                  "consentForEmail": true
              },
              "stepUp": {
                  "consentForEmail": true
              }
          }
      }
  }
```

#### Response

**HTTP Code:** 204 No Content

### Debit Demographics v3: Update cardholder contact information using card number

This case updates the contact information using a card number.

#### Request

**HTTP Method:** PATCH

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v3/cardholders/contact

```
{
    "cardNumber": "4000200030004000",
      "tcpa": [
          {
              "tcpaType": "ENFACT",
              "mediaType": "VOICE",
              "revoked": true
          }
      ],
      "contact": {
          "homePhone": "1005550001",
          "workPhone": "1005550001",
          "cellPhone": "1005550001",
          "textAddress": "1005550001",
          "enfact": {
              "languagePreference": "ENGLISH"
          }
      },
      "preferences": {
          "homePhone": {
              "enfact": {
                  "consentForVoice": true,
                  "consentForText": true
              },
              "stepUp": {
                  "consentForVoice": true,
                  "consentForText": true
              }
          },
          "workPhone": {
              "enfact": {
                  "consentForVoice": true,
                  "consentForText": true
              },
              "stepUp": {
                  "consentForVoice": true,
                  "consentForText": true
              }
          },
          "cellPhone": {
              "enfact": {
                  "consentForVoice": true,
                  "consentForText": true
              },
              "stepUp": {
                  "consentForVoice": true,
                  "consentForText": true
              }
          },
          "textAddress": {
              "enfact": {
                  "consentForText": true
              },
              "stepUp": {
                  "consentForText": true
              }
          },
          "emailAddress": {
              "enfact": {
                  "consentForEmail": true
              },
              "stepUp": {
                  "consentForEmail": true
              }
          }
      }
  }
```

#### Response

**HTTP Code:** 204 No Content

### Debit Demographics v3: Update cardholder address using card number

This case updates the address information using a card number.

#### Request

**HTTP Method:** PATCH

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v3/cardholders/address

```
{
    "cardNumber": "4000200030004000",
      "debitCardholderAddress": [
          {
              "addressType": "PRIMARY",
              "addressLine1": "123 Any Street",
              "addressLine2": "123 Any Lane",
              "city": "Newark",
              "countryCode": "USA",
              "stateCode": "NJ",
              "zipCode": "12345",
              "cardMailerIndicator": true,
              "pinMailerIndicator": false
          }
      ]
  }
```

#### Response

**HTTP Code:** 204 No Content

### Debit Demographics v3: Update cardholder address using NTT

This case updates the address information using NTT.

#### Request

**HTTP Method:** PATCH

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v3/cardholders/address

```
{
      "nonTransToken": "piUVBJKZGfks4000",
      "debitCardholderAddress": [
          {
              "addressType": "PRIMARY",
              "addressLine1": "123 Any Street",
              "addressLine2": "123 Any Lane",
              "city": "Newark",
              "countryCode": "USA",
              "stateCode": "NJ",
              "zipCode": "12345",
              "cardMailerIndicator": true,
              "pinMailerIndicator": false
          }
      ]
  }
```

#### Response

**HTTP Code:** 204 No Content
