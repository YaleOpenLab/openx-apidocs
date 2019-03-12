---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
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
