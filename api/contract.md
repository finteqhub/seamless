## GET /v1/contract

Сборка информации из DSL в виде JSON, где представлены разные варианты использования доступных на проекте платёжных методов.

1. Платёжные методы.
2. Интеграции, через которые они доступны.
3. Формы (наборы полей), необходимые для каждой из доступных интеграций.


out
```json
{
    "contract": {
        "paymentMethods": [
            {
                "id": "card-acquirer",
                "title": "card-acquirer",
                "type": "card-acquirer",
                "logo": "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRgwp1dAaa6BkjK-OXbxG8Rovpmxiq5qwnl899xRYJ0i1zqzlb3hagBCfmZQkEbgBIsN5c&usqp=CAU",
                "credentials": {
                    "deposit": {
                        "firstName": {
                            "ref": "$commonParameters.firstName",
                            "type": "string",
                            "minLength": 4,
                            "maxLength": 50,
                            "options": [],
                            "title": "First Name",
                            "description": "First Name",
                            "i18nId": "firstName",
                            "example": "string",
                            "obfuscate": "true"
                        }
                    }
                },
                "forms": [
                    {
                        "id": "card-acquirer.deposit",
                        "fields": [
                            {
                                "id": "firstName",
                                "minLength": 4,
                                "maxLength": 100,
                                "flags": [
                                    "required"
                                ]
                            }
                            
                                ]
                            }
                        ]
                    }
                ],
        "integrations": [
            {
                "id": "emerchantpay",
                "title": "Emerchantpay",
                "logo": "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRgwp1dAaa6BkjK-OXbxG8Rovpmxiq5qwnl899xRYJ0i1zqzlb3hagBCfmZQkEbgBIsN5c&usqp=CAU",
                "limits": {
                    "rateLimit": [],
                    "httpTimeout": {
                        "*": "35s"
                    }
                },
                "deposit": [
                    {
                        "id": "$ref.paymentMethods.card-acquirer",
                        "capabilities": [
                            "charge"
                        ],
                        "timeouts": {
                            "paymentPageTimeout": "60m",
                            "redirectUrlLifetime": "60m",
                            "expireTimeout": "60m",
                            "cancellationTimeout": "60m"
                        },
                        "forms": {
                            "default": "$ref.forms.card-acquirer.deposit",
                            "conditional": [
                                {
                                    "when": [
                                        {
                                            "sessionCountry": [
                                                "AT",
                                                "CH",
                                                "FR"
                                            ],
                                            "currency": [
                                                "EUR",
                                                "CHF"
                                            ]
                                        },
                                        {
                                            "sessionCountry": [
                                                "ES"
                                            ],
                                            "currency": [
                                                "EUR"
                                            ]
                                        }
                                    ],
                                    "form": "$ref.forms.card-acquirer.deposit.de"
                                }
                            ]
                        },
                        "paymentInstruments": [
                            {
                                "when": [
                                    {
                                        "sessionCountry": [
                                            "DE"
                                        ]
                                    }
                                ],
                                "list": [
                                    {
                                        "id": "deutsche-bank",
                                        "title": "Deutsche Bank",
                                        "logo": "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRgwp1dAaa6BkjK-OXbxG8Rovpmxiq5qwnl899xRYJ0i1zqzlb3hagBCfmZQkEbgBIsN5c&usqp=CAU",
                                        "form": "$ref.forms.card-acquirer.deposit.de"
                                    },
                                    {
                                        "id": "unicredit",
                                        "title": "UniCredit",
                                        "logo": "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRgwp1dAaa6BkjK-OXbxG8Rovpmxiq5qwnl899xRYJ0i1zqzlb3hagBCfmZQkEbgBIsN5c&usqp=CAU",
                                        "form": "$ref.forms.card-acquirer.deposit.de"
                                    }
                                ]
                            }
                        ]
                    }
                ]
            }
        ],
        "formats": {
            "email": {
                "maxLength": "50",
                "minLength": "4",
                "type": "string",
                "jsRegex": "^[a-zA-Z0-9._%+-]{4,47}@[a-zA-Z0-9.-]+\\\\.[a-zA-Z]{2,}$",
                "goRegex": "^[a-zA-Z0-9._%+-]{4,47}@[a-zA-Z0-9.-]+\\\\.[a-zA-Z]{2,}$",
                "pyRegex": "^[a-zA-Z0-9._%+-]{4,47}@[a-zA-Z0-9.-]+\\.[a-zA-Z]{2,}$",
                "rbRegex": "^[a-zA-Z0-9._%+-]{4,47}@[a-zA-Z0-9.-]+\\.[a-zA-Z]{2,}$",
                "javaRegex": "^[a-zA-Z0-9._%+-]{4,47}@[a-zA-Z0-9.-]+\\\\.[a-zA-Z]{2,}$"
            },
            "phoneNumber": {
                "maxLength": "15",
                "minLength": "5",
                "type": "string",
                "jsRegex": "\\d{5,15}"
            },
            "phoneCountryCode": {
                "type": "enum",
                "options": [
                    1,
                    7,
                    20
                ]
            }
        },
        "commonParameters": {
            "email": {
                "ref": "$formats.email",
                "title": "Email",
                "i18nId": "email",
                "example": "example@com"
            },
            "account": {
                "ref": "$formats.email",
                "title": "Account",
                "i18n": "account",
                "example": "example@com"
            },
            "birthDate": {
                "ref": "$formats.date",
                "title": "Birth Date",
                "i18nId": "birthDate"
            },
            "countryCode": {
                "ref": "$formats.countryCode",
                "example": "DE",
                "title": "Country",
                "i18nId": "countryCode"
            },
            "phoneNumber": {
                "type": "struct",
                "parameters": {
                    "phoneCountryCode": {
                        "ref": "$formats.phoneCountryCode",
                        "title": "Phone Code",
                        "i18nId": "phoneCountryCode",
                        "example": 62
                    },
                    "phoneNumber": {
                        "ref": "$formats.phoneNumber",
                        "title": "Phone Number",
                        "i18nId": "phoneNumber",
                        "example": 715151918
                    }
                }
            }
        }
    }    
}
```
