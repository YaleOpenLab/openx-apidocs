---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell

toc_footers:
  - <a href='https://github.com/lord/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

# Users

## Register User

```shell
curl -X
  GET -H "Content-Type: application/x-www-form-urlencoded"
  -H "Origin: localhost"
  -H "Cache-Control: no-cache"
  "http://localhost:8080/user/register?name=myName&username=spy&pwd=p&seedpwd=x"
```

| Parameter | Description                   |
| --------- | ----------------------------- |
| name      | The name of the user          |
| username  | The username of the user      |
| pwd       | The password of the user      |
| seedpwd   | The seed password of the user |

## Validate User

```shell
curl -X
  GET
  -H "Content-Type: application/x-www-form-urlencoded"
  -H "Origin: localhost"
  -H "Cache-Control: no-cache"
  "http://localhost:8080/user/validate?username=martin&pwhash=9a768ace36ff3d1771d5c145a544de3d68343b2e76093cb7b2a8ea89ac7f1a20c852e6fc1d71275b43abffefac381c5b906f55c3bcff4225353d02f1d3498758"
```

This endpoint retrieves all users.

### URL Parameters

| Parameter | Description                                  |
| --------- | -------------------------------------------- |
| username  | The username of the user                     |
| pwhash    | The 512byte sha3 hash of the user's password |

## Get All Balances

```shell
curl -X
  GET
  -H "Content-Type: application/x-www-form-urlencoded"
  -H "Origin: localhost"
  -H "Cache-Control: no-cache"
  "http://localhost:8080/user/balances?username=john&pwhash=9a768ace36ff3d1771d5c145a544de3d68343b2e76093cb7b2a8ea89ac7f1a20c852e6fc1d71275b43abffefac381c5b906f55c3bcff4225353d02f1d3498758"
```

This endpoint retrieves all user balances

| Parameter | Description                                  |
| --------- | -------------------------------------------- |
| username  | The username of the user                     |
| pwhash    | The 512byte sha3 hash of the user's password |

## Get XLM Balance

```shell
curl -X
  GET
  -H "Content-Type: application/x-www-form-urlencoded"
  -H "Origin: localhost"
  -H "Cache-Control: no-cache"
  "http://localhost:8080/user/balance/xlm?username=john&pwhash=9a768ace36ff3d1771d5c145a544de3d68343b2e76093cb7b2a8ea89ac7f1a20c852e6fc1d71275b43abffefac381c5b906f55c3bcff4225353d02f1d3498758"
```

This endpoint retrieves the XLM balance associated with the particular user

## Get Asset Balance

```shell
curl -X
  GET -H "Content-Type: application/x-www-form-urlencoded"
  -H "Origin: localhost"
  -H "Cache-Control: no-cache"
  "http://localhost:8080/user/balance/asset?username=john&pwhash=9a768ace36ff3d1771d5c145a544de3d68343b2e76093cb7b2a8ea89ac7f1a20c852e6fc1d71275b43abffefac381c5b906f55c3bcff4225353d02f1d3498758&asset=STABLEUSD"
```

| Parameter | Description                                            |
| --------- | ------------------------------------------------------ |
| username  | The username of the user                               |
| pwhash    | The 512byte sha3 hash of the user's password           |
| asset     | The name of the asset whose balance one wants to query |

## Get ipfs hash

```shell
curl -X
  GET -H "Content-Type: application/x-www-form-urlencoded"
  -H "Origin: localhost"
  -H "Cache-Control: no-cache"
  "http://localhost:8080/ipfs/hash?username=john&pwhash=9a768ace36ff3d1771d5c145a544de3d68343b2e76093cb7b2a8ea89ac7f1a20c852e6fc1d71275b43abffefac381c5b906f55c3bcff4225353d02f1d3498758&string=blah"
```

| Parameter | Description                                  |
| --------- | -------------------------------------------- |
| username  | The username of the user                     |
| pwhash    | The 512byte sha3 hash of the user's password |
| string    | The string whose ipfs hash one wants to get  |

## Send XLM to another user

```shell
  curl -X
  GET -H "Content-Type: application/x-www-form-urlencoded"
  -H "Origin: localhost"
  -H "Cache-Control: no-cache"
  "http://localhost:8080/user/sendxlm?username=john&pwhash=9a768ace36ff3d1771d5c145a544de3d68343b2e76093cb7b2a8ea89ac7f1a20c852e6fc1d71275b43abffefac381c5b906f55c3bcff4225353d02f1d3498758&seedpwd=x&amount=1&destination=GCHKX52XNXJ4PWG4TJYR7SEHFBBVDJWRGA22ELSISYLMRCDRSBLSL3MH"
```

| Parameter   | Description                                             |
| ----------- | ------------------------------------------------------- |
| username    | The username of the user                                |
| pwhash      | The 512byte sha3 hash of the user's password            |
| seedpwd     | The seedpwd of the source account                       |
| destination | The destination that the caller wishes to send funds to |
| amount      | The amount the caller wishes to send                    |

## View all users with kyc

```shell
curl -X
  GET -H "Content-Type: application/x-www-form-urlencoded"
  -H "Origin: localhost"
  -H "Cache-Control: no-cache"
  "http://localhost:8080/user/notkycview?username=john&pwhash=9a768ace36ff3d1771d5c145a544de3d68343b2e76093cb7b2a8ea89ac7f1a20c852e6fc1d71275b43abffefac381c5b906f55c3bcff4225353d02f1d3498758"
```

| Parameter | Description                                  |
| --------- | -------------------------------------------- |
| username  | The username of the user                     |
| pwhash    | The 512byte sha3 hash of the user's password |

## View all users without kyc

```shell
curl -X
  GET -H "Content-Type: application/x-www-form-urlencoded"
  -H "Origin: localhost"
  -H "Cache-Control: no-cache"
  "http://localhost:8080/user/kycview?username=john&pwhash=9a768ace36ff3d1771d5c145a544de3d68343b2e76093cb7b2a8ea89ac7f1a20c852e6fc1d71275b43abffefac381c5b906f55c3bcff4225353d02f1d3498758"
```

| Parameter | Description                                  |
| --------- | -------------------------------------------- |
| username  | The username of the user                     |
| pwhash    | The 512byte sha3 hash of the user's password |

## Get XLM from testnet faucet

```shell
curl -X
  GET -H "Content-Type: application/x-www-form-urlencoded"
  -H "Origin: localhost"
  -H "Cache-Control: no-cache"
  "http://localhost:8080/user/askxlm?username=john&pwhash=9a768ace36ff3d1771d5c145a544de3d68343b2e76093cb7b2a8ea89ac7f1a20c852e6fc1d71275b43abffefac381c5b906f55c3bcff4225353d02f1d3498758"
```

| Parameter | Description                                  |
| --------- | -------------------------------------------- |
| username  | The username of the user                     |
| pwhash    | The 512byte sha3 hash of the user's password |

## Trust Asset

```shell
curl -X
  GET -H "Content-Type: application/x-www-form-urlencoded"
  -H "Origin: localhost"
  -H "Cache-Control: no-cache"
  "http://localhost:8080/user/trustasset?username=martin&pwhash=9a768ace36ff3d1771d5c145a544de3d68343b2e76093cb7b2a8ea89ac7f1a20c852e6fc1d71275b43abffefac381c5b906f55c3bcff4225353d02f1d3498758&assetCode=STABELUSD&assetIssuer=GCSMRNO2NBLVULZAIAHA7PAPMFXXLFMLMEAZ23XPNGWMNSY2RL6GJYZR&limit=100&seedpwd=x"
```

| Parameter   | Description                                       |
| ----------- | ------------------------------------------------- |
| username    | The username of the user                          |
| pwhash      | The 512byte sha3 hash of the user's password      |
| seedpwd     | The seedpwd of the source account                 |
| assetCode   | The Code of the asset                             |
| assetIssuer | The issuer of the asset the caller wants to trust |

## Get platform email

```shell
curl -X
  GET -H "Content-Type: application/x-www-form-urlencoded"
  -H "Origin: localhost"
  -H "Cache-Control: no-cache"
  "http://localhost:8080/platformemail?username=martin&pwhash=9a768ace36ff3d1771d5c145a544de3d68343b2e76093cb7b2a8ea89ac7f1a20c852e6fc1d71275b43abffefac381c5b906f55c3bcff4225353d02f1d3498758"
```

| Parameter | Description                                  |
| --------- | -------------------------------------------- |
| username  | The username of the user                     |
| pwhash    | The 512byte sha3 hash of the user's password |

## Increase Trust Limit (Investor)

```shell
curl -X
  GET -H "Content-Type: application/x-www-form-urlencoded"
  -H "Origin: localhost"
  -H "Cache-Control: no-cache"
  "http://localhost:8080/user/increasetrustlimit?username=john&pwhash=9a768ace36ff3d1771d5c145a544de3d68343b2e76093cb7b2a8ea89ac7f1a20c852e6fc1d71275b43abffefac381c5b906f55c3bcff4225353d02f1d3498758&trust=10&seedpwd=x"
```

| Parameter | Description                                      |
| --------- | ------------------------------------------------ |
| username  | The username of the user                         |
| pwhash    | The 512byte sha3 hash of the user's password     |
| seedpwd   | The seedpwd of the source account                |
| trust     | The amount that the trust has to be increased by |

## Send Recovery Secrets

```shell
curl -X
  GET -H "Content-Type: application/x-www-form-urlencoded"
  -H "Origin: localhost"
  -H "Cache-Control: no-cache"
  "http://localhost:8080/user/sendrecovery?username=samuel&pwhash=9a768ace36ff3d1771d5c145a544de3d68343b2e76093cb7b2a8ea89ac7f1a20c852e6fc1d71275b43abffefac381c5b906f55c3bcff4225353d02f1d3498758&email1=varunramganesh@gmail.com&email2=varunramganesh@gmail.com&email3=varunramganesh@gmail.com"
```

| Parameter | Description                                  |
| --------- | -------------------------------------------- |
| username  | The username of the user                     |
| pwhash    | The 512byte sha3 hash of the user's password |
| email1    | The email of the first trusted entity        |
| email2    | The email of the second trusted entity       |
| email3    | The email of the third trusted entity        |

## Recover Seed from secrets

```shell
curl -X
  GET -H "Content-Type: application/x-www-form-urlencoded"
  -H "Origin: localhost"
  -H "Cache-Control: no-cache"
  "http://localhost:8080/user/seedrecovery?username=samuel&pwhash=9a768ace36ff3d1771d5c145a544de3d68343b2e76093cb7b2a8ea89ac7f1a20c852e6fc1d71275b43abffefac381c5b906f55c3bcff4225353d02f1d3498758&secret1=Z0Y8ojGOFs1hw_yNjpbI2jARd1VXjxe9Z1ZjWVN5Li0&secret2=gVRQbkIv4bA6MyazZMpx8MzaijiaQuqPwX-yMU8Ztzw"
```

| Parameter | Description                                           |
| --------- | ----------------------------------------------------- |
| username  | The username of the user                              |
| pwhash    | The 512byte sha3 hash of the user's password          |
| secret1   | The secret from any one of the three trusted entities |
| secret2   | The secret from any one of the three trusted entities |

## Generate New Secrets

```shell
curl -X
  GET -H "Content-Type: application/x-www-form-urlencoded"
  -H "Origin: localhost"
  -H "Cache-Control: no-cache"
  "http://localhost:8080/user/newsecrets?username=samuel&pwhash=9a768ace36ff3d1771d5c145a544de3d68343b2e76093cb7b2a8ea89ac7f1a20c852e6fc1d71275b43abffefac381c5b906f55c3bcff4225353d02f1d3498758&email1=varunramganesh@gmail.com&email2=varunramganesh@gmail.com&email3=varunramganesh@gmail.com&seedpwd=x"
```

| Parameter | Description                                  |
| --------- | -------------------------------------------- |
| username  | The username of the user                     |
| pwhash    | The 512byte sha3 hash of the user's password |
| email1    | The email of the first trusted entity        |
| email2    | The email of the second trusted entity       |
| email3    | The email of the third trusted entity        |

## Reset Password

```shell
curl -X
  GET -H "Content-Type: application/x-www-form-urlencoded"
  -H "Origin: localhost"
  -H "Cache-Control: no-cache"
  "http://localhost:8080/user/resetpwd?email=varunramganesh@gmail.com&seedpwd=x"
```

| Parameter | Description                   |
| --------- | ----------------------------- |
| email     | The email id of the user      |
| seedpwd   | The seed password of the user |

## Set New Password

```shell
curl -X
  GET -H "Content-Type: application/x-www-form-urlencoded"
  -H "Origin: localhost"
  -H "Cache-Control: no-cache"
  "http://localhost:8080/user/pwdreset?verificationCode=YYfyyffCmWxHjoEt&pwhash=9a768ace36ff3d1771d5c145a544de3d68343b2e76093cb7b2a8ea89ac7f1a20c852e6fc1d71275b43abffefac381c5b906f55c3bcff4225353d02f1d3498758&email=varunramganesh@gmail.com&seedpwd=x"
```

| Parameter        | Description                                    |
| ---------------- | ---------------------------------------------- |
| email            | The email id of the user                       |
| verificationCode | The verification code sent to the user's email |
| seedpwd          | The seed password of the user                  |

## Sweep XLM

```shell
curl -X
  GET -H "Content-Type: application/x-www-form-urlencoded"
  -H "Origin: localhost"
  -H "Cache-Control: no-cache"
  "http://localhost:8080/user/sweep?username=john&pwhash=9a768ace36ff3d1771d5c145a544de3d68343b2e76093cb7b2a8ea89ac7f1a20c852e6fc1d71275b43abffefac381c5b906f55c3bcff4225353d02f1d3498758&seedpwd=x&destination=GC6NOHUN7FWCBPOLG7KNYUO6VKNJGCO5PQ5ZENG4L6FXIUTJ6VQ3C7NZ"
```

| Parameter   | Description                                            |
| ----------- | ------------------------------------------------------ |
| username    | The username of the user                               |
| pwhash      | The 512byte sha3 hash of the user's password           |
| seedpwd     | The seed password of the user                          |
| destination | The  destination that the user wants to sweep funds to |

## Sweep Asset

```shell
curl -X
  GET -H "Content-Type: application/x-www-form-urlencoded"
  -H "Origin: localhost"
  -H "Cache-Control: no-cache"
  "http://localhost:8080/user/sweepasset?username=john&pwhash=9a768ace36ff3d1771d5c145a544de3d68343b2e76093cb7b2a8ea89ac7f1a20c852e6fc1d71275b43abffefac381c5b906f55c3bcff4225353d02f1d3498758&seedpwd=x&destination=GC6NOHUN7FWCBPOLG7KNYUO6VKNJGCO5PQ5ZENG4L6FXIUTJ6VQ3C7NZ&assetName=STABLEUSD&issuerPubkey=GCSMRNO2NBLVULZAIAHA7PAPMFXXLFMLMEAZ23XPNGWMNSY2RL6GJYZR"
```

| Parameter    | Description                                              |
| ------------ | -------------------------------------------------------- |
| username     | The username of the user                                 |
| pwhash       | The 512byte sha3 hash of the user's password             |
| seedpwd      | The seed password of the user                            |
| destination  | The  destination that the user wants to sweep funds to   |
| issuerPubkey | The issuer of the specific asset the user wants to sweep |
| assetName    | The asset that the user wants to sweep                   |

## Update User

```shell
curl -X
  GET -H "Cache-Control: no-cache"
  "http://localhost:8080/user/validate?username=john&pwhash=9a768ace36ff3d1771d5c145a544de3d68343b2e76093cb7b2a8ea89ac7f1a20c852e6fc1d71275b43abffefac381c5b906f55c3bcff4225353d02f1d3498758&zipcode=blah"
```

| Parameter                | Description                                               |
| ------------------------ | --------------------------------------------------------- |
| username                 | The username of the user                                  |
| pwhash                   | The 512byte sha3 hash of the user's password              |
| name (optional)          | The name of the user                                      |
| zipcode (optional)       | The zipcode that the user's residence is in               |
| country (optional)       | The country of residence of the user                      |
| recoveryphone (optional) | The recovery phone number of the user                     |
| address (optional)       | The address of the user                                   |
| description (optional)   | The description of the user                               |
| email (optional)         | The email that the user wants to receive notifications at |
| notification (optional)  | The notification settings toggle of the user              |

# Investors

## Register Investor

```shell
curl -X
  GET -H "Content-Type: application/x-www-form-urlencoded"
  -H "Origin: localhost"
  -H "Cache-Control: no-cache"
  "http://localhost:8080/investor/register?name=myName&username=spy1&pwd=p&seedpwd=x"
```

| Parameter | Description                   |
| --------- | ----------------------------- |
| name      | The name of the user          |
| username  | The username of the user      |
| pwd       | The password of the user      |
| seedpwd   | The seed password of the user |

## Validate Investor

```shell
curl -X
  GET -H "Cache-Control: no-cache"
  "http://localhost:8080/investor/validate?username=john&pwhash=9a768ace36ff3d1771d5c145a544de3d68343b2e76093cb7b2a8ea89ac7f1a20c852e6fc1d71275b43abffefac381c5b906f55c3bcff4225353d02f1d3498758"
```

| Parameter | Description                                  |
| --------- | -------------------------------------------- |
| username  | The username of the user                     |
| pwhash    | The 512byte sha3 hash of the user's password |

## Get All Investors

```shell
curl -X
  GET -H "Content-Type: application/x-www-form-urlencoded"
  -H "Origin: localhost"
  -H "Cache-Control: no-cache"
  "http://localhost:8080/investor/all"
```

## Invest in a Project

```shell
curl -X
  GET -H "Cache-Control: no-cache"
  "http://localhost:8080/investor/invest?username=john&pwhash=9a768ace36ff3d1771d5c145a544de3d68343b2e76093cb7b2a8ea89ac7f1a20c852e6fc1d71275b43abffefac381c5b906f55c3bcff4225353d02f1d3498758&seedpwd=x&projIndex=1&amount=100"
```

| Parameter | Description                                  |
| --------- | -------------------------------------------- |
| username  | The username of the user                     |
| pwhash    | The 512byte sha3 hash of the user's password |
| seedpwd   | The seed password of the user                |
| projIndex | The project index to invest in               |
| amount    | The amount to invest                         |

## Change Investor Reputation

```shell
curl -X
  GET -H "Cache-Control: no-cache"
  "http://localhost:8080/investor/reputation?username=john&pwhash=9a768ace36ff3d1771d5c145a544de3d68343b2e76093cb7b2a8ea89ac7f1a20c852e6fc1d71275b43abffefac381c5b906f55c3bcff4225353d02f1d3498758&reputation=1"
```

| Parameter  | Description                                      |
| ---------- | ------------------------------------------------ |
| username   | The username of the user                         |
| pwhash     | The 512byte sha3 hash of the user's password     |
| reputation | The amount of reputation to increase or decrease |

## Vote towards a project

```shell
curl -X
  GET -H "Cache-Control: no-cache"
  "http://localhost:8080/investor/vote?username=john&pwhash=9a768ace36ff3d1771d5c145a544de3d68343b2e76093cb7b2a8ea89ac7f1a20c852e6fc1d71275b43abffefac381c5b906f55c3bcff4225353d02f1d3498758&votes=10&projIndex=1"
```

| Parameter | Description                                       |
| --------- | ------------------------------------------------- |
| username  | The username of the user                          |
| pwhash    | The 512byte sha3 hash of the user's password      |
| votes     | The amount of votes to assign towards the project |
| projIndex | The project to vote towards                       |

## Create local asset

```shell
curl -X
  GET -H "Cache-Control: no-cache"
  "http://localhost:8080/investor/localasset?username=john&pwhash=9a768ace36ff3d1771d5c145a544de3d68343b2e76093cb7b2a8ea89ac7f1a20c852e6fc1d71275b43abffefac381c5b906f55c3bcff4225353d02f1d3498758&assetName=testasset"
```

| Parameter | Description                                             |
| --------- | ------------------------------------------------------- |
| username  | The username of the user                                |
| pwhash    | The 512byte sha3 hash of the user's password            |
| assetName | The name of the asset that the investor wants to create |

## Send Email to another entity

```shell
curl -X
  GET -H "Cache-Control: no-cache"
  "http://localhost:8080/investor/sendemail?username=john&pwhash=9a768ace36ff3d1771d5c145a544de3d68343b2e76093cb7b2a8ea89ac7f1a20c852e6fc1d71275b43abffefac381c5b906f55c3bcff4225353d02f1d3498758&message=hi&to=varunramganesh@gmail.com"
```

| Parameter | Description                                                   |
| --------- | ------------------------------------------------------------- |
| username  | The username of the user                                      |
| pwhash    | The 512byte sha3 hash of the user's password                  |
| message   | The message that the investor wants to convey to the receiver |
| to        | The email address of the receiver                             |

# Recipients

## Register Recipient

```shell
curl -X
  GET -H "Content-Type: application/x-www-form-urlencoded"
  -H "Origin: localhost"
  -H "Cache-Control: no-cache"
  "http://localhost:8080/recipient/register?name=myName&username=spy2&pwd=p&seedpwd=x"
```

| Parameter | Description                   |
| --------- | ----------------------------- |
| name      | The name of the user          |
| username  | The username of the user      |
| pwd       | The password of the user      |
| seedpwd   | The seed password of the user |

## Validate Recipient

```shell
curl -X
  GET -H "Cache-Control: no-cache"
  "http://localhost:8080/recipient/validate?username=martin&pwhash=9a768ace36ff3d1771d5c145a544de3d68343b2e76093cb7b2a8ea89ac7f1a20c852e6fc1d71275b43abffefac381c5b906f55c3bcff4225353d02f1d3498758"
```

| Parameter | Description                                  |
| --------- | -------------------------------------------- |
| username  | The username of the user                     |
| pwhash    | The 512byte sha3 hash of the user's password |

## Payback

```shell
curl -X
  GET -H "Cache-Control: no-cache"
  "http://localhost:8080/recipient/payback?username=martin&pwhash=9a768ace36ff3d1771d5c145a544de3d68343b2e76093cb7b2a8ea89ac7f1a20c852e6fc1d71275b43abffefac381c5b906f55c3bcff4225353d02f1d3498758&assetName=OXA21932324a&seedpwd=x&amount=120&projIndex=1"
```

| Parameter | Description                                                          |
| --------- | -------------------------------------------------------------------- |
| username  | The username of the user                                             |
| pwhash    | The 512byte sha3 hash of the user's password                         |
| assetName | The debt asset name owed by the recipient                            |
| seedpwd   | The seed password of the user                                        |
| amount    | The amount in stableUS that the user wants to payback                |
| projIndex | The index of the project that the recipient wants to payback towards |

## Store Device Id

```shell
curl -X
  GET -H "Cache-Control: no-cache"
  "http://localhost:8080/recipient/deviceId?username=martin&pwhash=9a768ace36ff3d1771d5c145a544de3d68343b2e76093cb7b2a8ea89ac7f1a20c852e6fc1d71275b43abffefac381c5b906f55c3bcff4225353d02f1d3498758&deviceid=blah"
```

| Parameter | Description                                                    |
| --------- | -------------------------------------------------------------- |
| username  | The username of the user                                       |
| pwhash    | The 512byte sha3 hash of the user's password                   |
| deviceId  | The deviceId (of the teller) that the recipient wants to store |

## Store Start time of teller

```shell
curl -X
  GET -H "Cache-Control: no-cache"
  "http://localhost:8080/recipient/startdevice?username=martin&pwhash=9a768ace36ff3d1771d5c145a544de3d68343b2e76093cb7b2a8ea89ac7f1a20c852e6fc1d71275b43abffefac381c5b906f55c3bcff4225353d02f1d3498758&start=blah"
```

| Parameter | Description                                                      |
| --------- | ---------------------------------------------------------------- |
| username  | The username of the user                                         |
| pwhash    | The 512byte sha3 hash of the user's password                     |
| start     | The start time (of the teller) that the recipient wants to store |

## Store location of the teller

```shell
curl -X
  GET -H "Cache-Control: no-cache"
  "http://localhost:8080/recipient/storelocation?username=martin&pwhash=9a768ace36ff3d1771d5c145a544de3d68343b2e76093cb7b2a8ea89ac7f1a20c852e6fc1d71275b43abffefac381c5b906f55c3bcff4225353d02f1d3498758&location=blah"
```

| Parameter | Description                                                    |
| --------- | -------------------------------------------------------------- |
| username  | The username of the user                                       |
| pwhash    | The 512byte sha3 hash of the user's password                   |
| location  | The location (of the teller) that the recipient wants to store |

## Change Recipient Reputation

```shell
curl -X
  GET -H "Cache-Control: no-cache"
  "http://localhost:8080/recipient/reputation?username=martin&pwhash=9a768ace36ff3d1771d5c145a544de3d68343b2e76093cb7b2a8ea89ac7f1a20c852e6fc1d71275b43abffefac381c5b906f55c3bcff4225353d02f1d3498758&reputation=10"
```

| Parameter  | Description                                                 |
| ---------- | ----------------------------------------------------------- |
| username   | The username of the user                                    |
| pwhash     | The 512byte sha3 hash of the user's password                |
| reputation | The reputation that needs to be increased for the recipient |

## Choose blind auction

```shell
curl -X
  GET -H "Cache-Control: no-cache"
  "http://localhost:8080/recipient/auction/choose/blind?username=martin&pwhash=9a768ace36ff3d1771d5c145a544de3d68343b2e76093cb7b2a8ea89ac7f1a20c852e6fc1d71275b43abffefac381c5b906f55c3bcff4225353d02f1d3498758"
```

| Parameter | Description                                  |
| --------- | -------------------------------------------- |
| username  | The username of the user                     |
| pwhash    | The 512byte sha3 hash of the user's password |

## Choose vickrey auction

```shell
curl -X
  GET -H "Cache-Control: no-cache"
  "http://localhost:8080/recipient/auction/choose/vickrey?username=martin&pwhash=9a768ace36ff3d1771d5c145a544de3d68343b2e76093cb7b2a8ea89ac7f1a20c852e6fc1d71275b43abffefac381c5b906f55c3bcff4225353d02f1d3498758"
```

| Parameter | Description                                  |
| --------- | -------------------------------------------- |
| username  | The username of the user                     |
| pwhash    | The 512byte sha3 hash of the user's password |

## Choose time auction

```shell
curl -X
  GET -H "Cache-Control: no-cache"
  "http://localhost:8080/recipient/auction/choose/time?username=martin&pwhash=9a768ace36ff3d1771d5c145a544de3d68343b2e76093cb7b2a8ea89ac7f1a20c852e6fc1d71275b43abffefac381c5b906f55c3bcff4225353d02f1d3498758"
```

| Parameter | Description                                  |
| --------- | -------------------------------------------- |
| username  | The username of the user                     |
| pwhash    | The 512byte sha3 hash of the user's password |

## Unlock Project

```shell
curl -X
  GET -H "Cache-Control: no-cache"
  "http://localhost:8080/unlock/opensolar/time?username=martin&pwhash=9a768ace36ff3d1771d5c145a544de3d68343b2e76093cb7b2a8ea89ac7f1a20c852e6fc1d71275b43abffefac381c5b906f55c3bcff4225353d02f1d3498758&seedpwd=x"
```

| Parameter | Description                                  |
| --------- | -------------------------------------------- |
| username  | The username of the user                     |
| pwhash    | The 512byte sha3 hash of the user's password |
| seedpwd   | The seed password of the user                |

## Add email address

```shell
curl -X
  GET -H "Cache-Control: no-cache"
  "http://localhost:8080/recipient/addemail?username=martin&pwhash=9a768ace36ff3d1771d5c145a544de3d68343b2e76093cb7b2a8ea89ac7f1a20c852e6fc1d71275b43abffefac381c5b906f55c3bcff4225353d02f1d3498758&email=varunramganesh@gmail.com"
```

| Parameter | Description                                                    |
| --------- | -------------------------------------------------------------- |
| username  | The username of the user                                       |
| pwhash    | The 512byte sha3 hash of the user's password                   |
| email     | The email address that hte user wishes to add to their profile |

## Finalize a particular project

```shell
curl -X
  GET -H "Cache-Control: no-cache"
  "http://localhost:8080/recipient/finalize?username=martin&pwhash=9a768ace36ff3d1771d5c145a544de3d68343b2e76093cb7b2a8ea89ac7f1a20c852e6fc1d71275b43abffefac381c5b906f55c3bcff4225353d02f1d3498758&projIndex=1"
```

| Parameter | Description                                       |
| --------- | ------------------------------------------------- |
| username  | The username of the user                          |
| pwhash    | The 512byte sha3 hash of the user's password      |
| projIndex | The index of the project that has to be finalized |

## Increase Trust Limit (Recipient)

```shell
curl -X
  GET -H "Content-Type: application/x-www-form-urlencoded"
  -H "Origin: localhost"
  -H "Cache-Control: no-cache"
  "http://localhost:8080/user/increasetrustlimit?username=john&pwhash=9a768ace36ff3d1771d5c145a544de3d68343b2e76093cb7b2a8ea89ac7f1a20c852e6fc1d71275b43abffefac381c5b906f55c3bcff4225353d02f1d3498758&trust=10&seedpwd=x"
```

| Parameter | Description                                      |
| --------- | ------------------------------------------------ |
| username  | The username of the user                         |
| pwhash    | The 512byte sha3 hash of the user's password     |
| seedpwd   | The seedpwd of the source account                |
| trust     | The amount that the trust has to be increased by |

## Store State Hash

```shell
curl -X
  GET -H "Cache-Control: no-cache"
  "http://localhost:8080/recipient/ssh?username=martin&pwhash=9a768ace36ff3d1771d5c145a544de3d68343b2e76093cb7b2a8ea89ac7f1a20c852e6fc1d71275b43abffefac381c5b906f55c3bcff4225353d02f1d3498758&hash=blah"
```

| Parameter | Description                                  |
| --------- | -------------------------------------------- |
| username  | The username of the user                     |
| pwhash    | The 512byte sha3 hash of the user's password |
| hash      | The state hash that the user wishes to store |

# Projects

## Get All Projects

```shell
curl -X
  GET
  -H "Content-Type: application/x-www-form-urlencoded"
  -H "Origin: localhost"
  -H "Cache-Control: no-cache"
  "http://localhost:8080/project/all"
```

This endpoint retrieves the list of all opensolar projects associated with the platform

## Get Specific Project

```shell
curl -X
  GET
  -H "Content-Type: application/x-www-form-urlencoded"
  -H "Origin: localhost"
  -H "Cache-Control: no-cache"
  "http://localhost:8080/project/get?index=1"
```

This endpoint retrieves a specific opensolar project

| Parameter | Description                                             |
| --------- | ------------------------------------------------------- |
| index     | The index of the project that we would like to retrieve |

## Get Projects at a particular stage

```shell
curl -X GET -H "Cache-Control: no-cache" "http://localhost:8080/projects?index=2"
```

| Parameter | Description                                                     |
| --------- | --------------------------------------------------------------- |
| index     | The stage at which we would like to see how many projects exist |

# Public

## Get Name

```shell
curl -X
  GET -H "Content-Type: application/x-www-form-urlencoded"
  -H "Origin: localhost"
  -H "Cache-Control: no-cache"
  "http://localhost:8080/public/user?index=50"
```

| Parameter | Description               |
| --------- | ------------------------- |
| index     | The user inex of the user |

## Get All Investors

```shell
curl -X
  GET -H "Content-Type: application/x-www-form-urlencoded"
  -H "Origin: localhost"
  -H "Cache-Control: no-cache"
  "http://localhost:8080/public/investor/all"
```

## Get All Recipients

```shell
curl -X
  GET -H "Content-Type: application/x-www-form-urlencoded"
  -H "Origin: localhost"
  -H "Cache-Control: no-cache"
  "http://localhost:8080/public/recipient/all"
```

## Get Top Reputed Users

```shell
curl -X
  GET -H "Content-Type: application/x-www-form-urlencoded"
  -H "Origin: localhost"
  -H "Cache-Control: no-cache"
  "http://localhost:8080/public/reputation/top"
```

## Get Top Reputed Investors

```shell
curl -X
  GET -H "Content-Type: application/x-www-form-urlencoded"
  -H "Origin: localhost"
  -H "Cache-Control: no-cache"
  "http://localhost:8080/public/investor/reputation/top"
```

## Get Top Reputed Recipients

```shell
curl -X
  GET -H "Content-Type: application/x-www-form-urlencoded"
  -H "Origin: localhost"
  -H "Cache-Control: no-cache"
  "http://localhost:8080/public/recipient/reputation/top"
```

# Stablecoin

## Get Stablecoin

```shell
curl -X
  GET -H "Cache-Control: no-cache"
  "http://localhost:8080/stablecoin/get?seed=SA5DXUTRWHQXOHPISTRLPH55NIUOSV2GB5NDTOSZ7H33KOK2TYYU556O&amount=1&pwhash=9a768ace36ff3d1771d5c145a544de3d68343b2e76093cb7b2a8ea89ac7f1a20c852e6fc1d71275b43abffefac381c5b906f55c3bcff4225353d02f1d3498758&username=john"
```

| Parameter | Description                                                                                 |
| --------- | ------------------------------------------------------------------------------------------- |
| username  | The username of the user                                                                    |
| pwhash    | The 512byte sha3 hash of the user's password                                                |
| seed      | The seed of the account that requires stablecoin / is willing to exchange xlm for stableusd |
| amount    | The amount of xlm that the user wishes to exchange for STABLEUSD                            |

# Stages

## Get All Stages

```shell
curl -X
  GET -H "Cache-Control: no-cache" "http://localhost:8080/stages/all"
```

## Get a specific stage

```shell
curl -X
  GET -H "Cache-Control: no-cache" "http://localhost:8080/stages?index=1"
```

## Promote stages

```shell
curl -X
  GET -H "Cache-Control: no-cache" "http://localhost:8080/stages/promote?index=2"
```

# Particle

## Get All Devices

```shell
curl -X
  GET -H "Cache-Control: no-cache"
"http://localhost:8080/particle/devices?username=john&pwhash=9a768ace36ff3d1771d5c145a544de3d68343b2e76093cb7b2a8ea89ac7f1a20c852e6fc1d71275b43abffefac381c5b906f55c3bcff4225353d02f1d3498758&accessToken=blah&productInfo=blah"
```

| Parameter   | Description                                  |
| ----------- | -------------------------------------------- |
| username    | The username of the user                     |
| pwhash      | The 512byte sha3 hash of the user's password |
| accessToken | The access token of the particle endpoint    |
| productInfo | The information associated with the product  |

## Get Product Info

```shell
curl -X
  GET -H "Cache-Control: no-cache"
  "http://localhost:8080/particle/productinfo?username=john&pwhash=9a768ace36ff3d1771d5c145a544de3d68343b2e76093cb7b2a8ea89ac7f1a20c852e6fc1d71275b43abffefac381c5b906f55c3bcff4225353d02f1d3498758&accessToken=blah&productInfo=blah"
```

| Parameter   | Description                                  |
| ----------- | -------------------------------------------- |
| username    | The username of the user                     |
| pwhash      | The 512byte sha3 hash of the user's password |
| accessToken | The access token of the particle endpoint    |
| productInfo | The information associated with the product  |

## Ping Device

```shell
curl -X
  GET -H "Cache-Control: no-cache"
  "http://localhost:8080/particle/deviceping?username=john&pwhash=9a768ace36ff3d1771d5c145a544de3d68343b2e76093cb7b2a8ea89ac7f1a20c852e6fc1d71275b43abffefac381c5b906f55c3bcff4225353d02f1d3498758&accessToken=blah&deviceId=blah"
```

| Parameter   | Description                                  |
| ----------- | -------------------------------------------- |
| username    | The username of the user                     |
| pwhash      | The 512byte sha3 hash of the user's password |
| accessToken | The access token of the particle endpoint    |

## Turn Signal on

```shell
curl -X
  GET -H "Cache-Control: no-cache"
  "http://localhost:8080/particle/devicesignal?username=john&pwhash=9a768ace36ff3d1771d5c145a544de3d68343b2e76093cb7b2a8ea89ac7f1a20c852e6fc1d71275b43abffefac381c5b906f55c3bcff4225353d02f1d3498758&accessToken=blah&deviceId=blah&signal=on"
```

| Parameter   | Description                                  |
| ----------- | -------------------------------------------- |
| username    | The username of the user                     |
| pwhash      | The 512byte sha3 hash of the user's password |
| accessToken | The access token of the particle endpoint    |
| signal      | Boolean value to turn on / off the signal    |

## Get Device Id

```shell
curl -X
  GET -H "Cache-Control: no-cache"
  "http://localhost:8080/particle/getdeviceid?username=john&pwhash=9a768ace36ff3d1771d5c145a544de3d68343b2e76093cb7b2a8ea89ac7f1a20c852e6fc1d71275b43abffefac381c5b906f55c3bcff4225353d02f1d3498758&accessToken=blah&serialNumber=blah"
```

| Parameter    | Description                                  |
| ------------ | -------------------------------------------- |
| username     | The username of the user                     |
| pwhash       | The 512byte sha3 hash of the user's password |
| serialNumber | The serial number of the device              |

## Get last diagnostic report

```shell
curl -X
  GET -H "Cache-Control: no-cache"
  "http://localhost:8080/particle/diag/last?username=john&pwhash=9a768ace36ff3d1771d5c145a544de3d68343b2e76093cb7b2a8ea89ac7f1a20c852e6fc1d71275b43abffefac381c5b906f55c3bcff4225353d02f1d3498758&accessToken=blah&deviceId=blah"
```

| Parameter   | Description                                  |
| ----------- | -------------------------------------------- |
| username    | The username of the user                     |
| pwhash      | The 512byte sha3 hash of the user's password |
| accessToken | The access token of the particle endpoint    |
| deviceId    | The deviceId of the installed device         |

## Get all diagnostic reports

```shell
curl -X
  GET -H "Cache-Control: no-cache"
  "http://localhost:8080/particle/diag/all?username=john&pwhash=9a768ace36ff3d1771d5c145a544de3d68343b2e76093cb7b2a8ea89ac7f1a20c852e6fc1d71275b43abffefac381c5b906f55c3bcff4225353d02f1d3498758&accessToken=blah&deviceId=blah"
```

| Parameter   | Description                                  |
| ----------- | -------------------------------------------- |
| username    | The username of the user                     |
| pwhash      | The 512byte sha3 hash of the user's password |
| accessToken | The access token of the particle endpoint    |
| deviceId    | The deviceId of the installed device         |

## Get user info

```shell
curl -X
  GET -H "Cache-Control: no-cache"
  "http://localhost:8080/particle/user/info?username=john&pwhash=9a768ace36ff3d1771d5c145a544de3d68343b2e76093cb7b2a8ea89ac7f1a20c852e6fc1d71275b43abffefac381c5b906f55c3bcff4225353d02f1d3498758&accessToken=blah"
```

| Parameter   | Description                                  |
| ----------- | -------------------------------------------- |
| username    | The username of the user                     |
| pwhash      | The 512byte sha3 hash of the user's password |
| accessToken | The access token of the particle endpoint    |

## Get installed sim card data

```shell
curl -X
  GET -H "Cache-Control: no-cache"
  "http://localhost:8080/particle/sims?username=john&pwhash=9a768ace36ff3d1771d5c145a544de3d68343b2e76093cb7b2a8ea89ac7f1a20c852e6fc1d71275b43abffefac381c5b906f55c3bcff4225353d02f1d3498758&accessToken=blah"
```

| Parameter   | Description                                  |
| ----------- | -------------------------------------------- |
| username    | The username of the user                     |
| pwhash      | The 512byte sha3 hash of the user's password |
| accessToken | The access token of the particle endpoint    |

# Platform

## Ping the platform

```shell
curl -X GET -H "Cache-Control: no-cache" "http://localhost:8080/ping"
```
