## POST /v1/sessions/{UUID}

out
```json
{
    "customer": {
        "accounts": [],
        "countryCode": "",
        "id": "01850bd3-1599-89f8-3a06-56e1433a7659",
        "merchantCustomerId": "7792348c-da1a-44c5-9930-6de938603cca",
        "name": "",
        "projectId": "0184197d-a80a-c175-b34d-4c9ebd8f235b"
    },
    "initCredentials": {
        "billingAddress": {
            "address": "Ulica",
            "city": "Moscow",
            "countryCode": "US",
            "postalCode": "123456",
            "state": "US"
        },
        "card": {
            "cardData": "AZ4VYhUEMASikriz4MS/nQzcm8c6d1mv6tZkyy4q9Gpq/pRbfTZW02Y3zoNcJxW70YJwMi7eS6Yl66UsiSbKPhPIjiKy3KmXdrUnP7ZxI/pDJMNf7HrSqzpMjNeyr6dkNxPXDe2+9iSOIySwjluZXIaiCp+LgnjSh3uaglj2eBoYoD0KWePkA3rV//lTsS8ho1cGwgKP/Okt8QaWDBiB7DilZa5VuQkLwHOqiuEM25NEW1ovu6SH9RFTbzY73UNj1pKF50YtvWY92fjQ4auZWZwNOh2OzvF0kKx6xdc1Fl0oB6nNUD2O5DFTqX5SI9W2B9cSIIfpOtoPQqAG7l3oH8Krt3ZPkWY5MQ==",
            "cvv": null,
            "keyId": "01850af1-5d03-60d3-abb4-fc5a18ca15d2",
            "mask": "401200******0085",
            "tokenId": null,
            "tokenize": true
        },
        "payer": {
            "birthDate": "1996-10-03",
            "email": "kek@bek.com",
            "firstName": "Boris Britva",
            "lastName": "10",
            "merchantCustomerId": "",
            "phoneCountryCode": "1",
            "phoneNumber": "297776655"
        },
        "shippingAddress": {
            "address": "Ulica",
            "city": "Moscow",
            "country": "US",
            "postalCode": "123456",
            "state": "US"
        }
    },
    "operation": {
        "amount": "0.3",
        "currencyCode": "EUR",
        "failUrl": "https://pgw.today?status=fail",
        "integration": "emerchantpay",
        "operationId": "01850bd3-16c2-86b9-65fe-22a2bc09ecef",
        "paymentMethod": "card-acquirer",
        "projectId": "0184197d-a80a-c175-b34d-4c9ebd8f235b",
        "successUrl": "https://pgw.today?status=ok",
        "transactionId": "01850bd3-16c2-ed6c-866a-2ddbbcb5f4d8",
        "transactionType": "deposit"
    },
    "session": {
        "createdAt": "2022-12-13T14:11:01.522092646Z",
        "ttl": 86400
    }
}
```
