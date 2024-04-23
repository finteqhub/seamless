## POST /v1/{txType}/payment-options

in
```json
{
"currencyCode": "EUR",
"customer": {
    "id": "c41fed51-7b1d-4b8c-89f3-101e26e825f0",
    "countryCode": "AS",
    "metadata": {}
  },
  "session": {
    "ip": "255.255.255.255"
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
        {"id": "uuid", "integrationAccountId": "kek@bek.com", info: {} },
        {"id": "uuid", "integrationAccountId": "bek@kek.com", info: {} },
      ]
    }
  }
}
```
