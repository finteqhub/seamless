## POST /v1/transactions/{txType}/init

in
```json
{
  "customer": {
    "id": "c41fed51-7b1d-4b8c-89f3-101e26e825f0",
    "name": "name",
    "email": "user@example.com",
    "birthDate": "2020-12-08",
    "countryCode": "AS",
    "phoneNumber": "string",
    "phoneCountryCode": "string",
    "metadata": {}
  },
  "customerAccountId": "d8c60791-7301-441c-98e8-5bea9a162d9b",
  "session": {
    "ip": "255.255.255.255",
    "fingerprint": "stringstringstringstringstringst",
    "device": {
      "type": "string",
      "browser": {
        "platform": "string",
        "acceptHeader": "string",
        "userAgent": "string",
        "javaEnabled": true,
        "language": "string",
        "colorDepth": 0,
        "screenHeight": 0,
        "screenWidth": 0,
        "windowHeight": 0,
        "windowWidth": 0,
        "windowInnerWidth": 0,
        "windowInnerHeight": 0,
        "timeZoneOffset": 0,
        "timeZoneName": "Africa/Abidjan"
      }
    }
  },
  "flow": "direct",
  "integration": "astropay",
  "paymentMethod": "alfabank",
  "formView": "alfabank.deposit"
  "merchantTransactionId": "string",
  "operation": {
    "amount": "100.00",
    "currencyCode": "EUR",
    "failUrl": "http(s)://google.com",
    "successUrl": "http(s)://google.com",
    "merchantOperationId": "string",
    "credentials": {
      "payer": {
        "merchantCustomerId": "john@doe.com",
        "firstName": "John",
        "lastName": "Doe",
        "document": "string",
        "birthDate": "1987-03-22",
        "email": "user@example.com",
        "phoneNumber": 2505550199,
        "phoneCountryCode": "1829"
      },
      "billingAddress": {
        "postalCode": "CA6633",
        "city": "London",
        "state": "US-LA",
        "countryCode": "US",
        "address": "Payer st."
      },
      "shippingAddress": {
        "postalCode": "CA6633",
        "city": "London",
        "state": "US-LA",
        "countryCode": "US",
        "address": "Payer st."
      },
      "card": {
        "tokenId": "07dfef4c-e677-4ce6-87a3-cd348338445f",
        "number": "string",
        "holder": "string",
        "expiryMonth": 0,
        "expiryYear": 0,
        "cvv": "str",
        "tokenize": "true"
      }
    }
  }
}
```

out
```json
{
  "sessionId": "string",
  "operationId": "3051932a-fdd2-48fa-b330-7e7d41535969",
  "transactionId": "75906707-8c31-479c-b354-aa805c4cefbc",
  "customerId": "87d8e330-2878-4742-a86f-dbbb3bf522ac",
  "url": "http://psp-emu.dckr/v1/go/1c6e10a34a7abeb28615ef8a421b9f13d69044ce2f4367429040eb8a074d6100",
  "error": "string"
}
```
