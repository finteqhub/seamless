## POST /v1/payment-options

in
```json
{
  "customer": {
    "id": "c41fed51-7b1d-4b8c-89f3-101e26e825f0",
    "name": "name",
    "email": "user@example.com",
    "phoneNumber": "string",
    "birthDate": "2020-12-08",
    "country": "AS",
    "billingAddress": {
      "line1": "string",
      "line2": "string",
      "city": "string",
      "state": "string",
      "countryCode": "AS",
      "phone": "string",
      "postalCode": "string"
    }
  }
}
```

out
```json
{
  "methods": {
    "bank-transfer": {
      "integrations": ["noda"],
      "accounts": [
        {"id": "uuid", "integrationAccountId": "kek@bek.com"},
        {"id": "uuid", "integrationAccountId": "bek@kek.com"},
      ]
    }
  }
}
```