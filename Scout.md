# Scout

Endpoints for Versus Scouts

## Add Response

Add a response to a question.


> Endpoint: scout_add_response

> Payload

``` javascript
{
  "cRef": "",
  "qRef": "",
  "sRef": "",
  "response": "",
  "clientRef": ""
}
```

> Result
``` javascript
{
  "response": {
    "campaignRef": "0b3cf5bd-bea9-429b-b374-8f65e5473ed9",
    "questionRef": "c30e78b6-ff88-49a5-91e9-bb7fb46f1455"
    "scoutRef": "ea7ca901-9217-4a04-9af4-3c6c21ccc3a2",
    "response": "response",
    "clientRef": "clientRef"
  }
}
```

## Create Scout

Add a scout - firstName, lastName and phoneNumber are required


> Endpoint: scout_create_scout

> Payload

``` javascript
{
    "firstName": "James",
    "lastName": "Austin",
    "phoneNumber": "+2347023004000",
    "bankName": "Prudential",
    "bankCode": "002",
    "accountNumber": "10-2-200-5",
    "bvn": "bvn",
    "emailAddress": "a@test.com",
    "dob": "2017-12-31",
    "gender": "Female",
    "education": "education",
    "maritalStatus": "maritalStatus",
    "religion": "religion",
    "occupation": "occupation",
    "country": "country",
    "state": "state",
    "language": "English"
}
```

> Result
``` javascript
{
  "scoutRef": "ea7ca901-9217-4a04-9af4-3c6c21ccc3a2"
}
```

## Get Campaigns

Get all campaigns on the system


> Endpoint: scout_get_campaigns

> Payload

``` javascript
{}
```

> Result
``` javascript
{
  "campaigns": [
    {
      "campaignName": "Biq Query",
      "campaignRef": "0b3cf5bd-bea9-429b-b374-8f65e5473ed9",
      "clientName": "The Enterprise",
      "clientRef": "nqaXKB0SzWN6xh7RVyzl",
      "country": "NG",
      "description": "Big query",
      "education": null,
      "endAge": 60,
      "endDate": "2020-10-10 00:00:00",
      "gender": null,
      "maritalStatus": null,
      "occupation": null,
      "religion": null,
      "startAge": 20,
      "startDate": "2000-10-10 00:00:00"
    }
  ]
}
```

## Get DocRef

Get a Scout reference given a phoneNumber.


> Endpoint: scout_get_docref

> Payload

``` javascript
{
  "phoneNumber": "08023004000"
}
```

> Result
``` javascript
{
  "scouts": [
    {
        "firstName": "firstName",
        "lastName": "lastName",
        "phoneNumber": "phoneNumber",
        "bankName": "bankName",
        "bankCode": "bankCode",
        "accountNumber": "accountNumber",
        "bvn": "bvn",
        "emailAddress": "emailAddress",
        "dob": "dob",
        "gender": "gender",
        "education": "education",
        "maritalStatus": "maritalStatus",
        "religion": "religion",
        "occupation": "occupation",
        "country": "country",
        "state": "state",
        "language": "language",
        "scoutRef": "ea7ca901-9217-4a04-9af4-3c6c21ccc3a2",
        "versusCredits": {
            "canCashOut": false,
            "amount": 0
        },
        "verified": false,
        "twoFA": false
    }
  ]
}
```

## Get Questions

Get the questions associated with a campaign.


> Endpoint: scout_get_questions

> Payload

``` javascript
{
  "docRef": "0b3cf5bd-bea9-429b-b374-8f65e5473ed9"
}
```

> Result
``` javascript
{
  "questions": [
    {
      "campaignName": "campaignRef",
      "campaignRef": "0b3cf5bd-bea9-429b-b374-8f65e5473ed9",
      "clientName": "clientName",
      "clientRef": "clientRef",
      "options": "1,2,3",
      "question": "Big question",
      "questionRef": "c30e78b6-ff88-49a5-91e9-bb7fb46f1455"
    }
  ]
}
```

## Get Responses

Get the responses associated with a question.


> Endpoint: scout_get_questions

> Payload

``` javascript
{
  "docRef": "0b3cf5bd-bea9-429b-b374-8f65e5473ed9"
}
```

> Result
``` javascript
{
  "questions": [
    {
      "campaignRef": "0b3cf5bd-bea9-429b-b374-8f65e5473ed9",
      "questionRef": "c30e78b6-ff88-49a5-91e9-bb7fb46f1455"
      "scoutRef": "ea7ca901-9217-4a04-9af4-3c6c21ccc3a2",
      "response": "response",
      "clientRef": "clientRef"
    }
  ]
}
```

## Get Scout

Get a scout given the docRef


> Endpoint: scout_get_scout

> Payload

``` javascript
{
  "docRef": "ea7ca901-9217-4a04-9af4-3c6c21ccc3a2"
}
```

> Result
``` javascript
{
    "firstName": "firstName",
    "lastName": "lastName",
    "phoneNumber": "phoneNumber",
    "bankName": "bankName",
    "bankCode": "bankCode",
    "accountNumber": "accountNumber",
    "bvn": "bvn",
    "emailAddress": "emailAddress",
    "dob": "dob",
    "gender": "gender",
    "education": "education",
    "maritalStatus": "maritalStatus",
    "religion": "religion",
    "occupation": "occupation",
    "country": "country",
    "state": "state",
    "language": "language",
    "scoutRef": "ea7ca901-9217-4a04-9af4-3c6c21ccc3a2",
    "versusCredits": {
        "canCashOut": false,
        "amount": 0
    },
    "verified": false,
    "twoFA": false
}
```

## Create Scout Wallet

Create a Stellar Wallet associated with a Scout.

| Field               | Type   | Description                                                                        |
|---------------------|--------|------------------------------------------------------------------------------------|
| sourceStellarSeed   | string | A Stellar Account funded in XLM to provide the mimimum balance needed for a wallet |
| scoutRef            | string | A unique string to identify a scout, a wallet is created once for each scoutRef    | 

> Endpoint: scout_create_wallet 

> Payload

```json
{
  "sourceStellarSeed": "SCY5QWUU7IGWGVUWYFSPBA2CAYQFYR63QALEIIX3ITYDPLV2AUIY6Q5S",
  "scoutRef": "ea7ca901-9217-4a04-9af4-3c6c21ccc3a2"
}
```

> Result

```json
{
  "walletRef": "FQ0upRkKXT3xdwzzKs6X"
}
```

## Fund a Scout Wallet

Create a Stellar Wallet associated with a Scout.

| Field               | Type   | Description                                                 |
|---------------------|--------|-------------------------------------------------------------|
| sourceStellarSeed   | string | A Stellar Issuing Account to provide at transaction fee     |
| scoutRef            | string | A unique string to used to create a wallet for the scout    | 
| versusCoinCredit    | string | VersusCoin amount formatted as a string to fund the wallet  | 

> Endpoint: scout_fund_wallet

> Payload

```json
{
  "sourceStellarSeed": "SCY5QWUU7IGWGVUWYFSPBA2CAYQFYR63QALEIIX3ITYDPLV2AUIY6Q5S",
  "scoutRef": "ea7ca901-9217-4a04-9af4-3c6c21ccc3a2",
  "versusCoinCredit": "1.05"
}
```

> Result

```json
{
  "status": "ok"
}
```
