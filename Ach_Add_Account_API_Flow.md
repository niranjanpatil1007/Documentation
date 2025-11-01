
---
[![Company Logo](company logo link)]()
# Ach Add Account Flow 
 

# API Document
### _<February 2025>_
&nbsp;
&nbsp; 

### Version: 1.0
#### _Author: Niranjan Patil._
&nbsp;
&nbsp;
---
## AUDIENCE
- Clients
- Internal Users

## STATEMENT OF CONFIDENTIALITY
This document is the proprietary and confidential property of Pvt. Ltd. It is intended solely for use by employees and clients of Pvt. Ltd and shall not be reproduced or disclosed to any other party without the express written consent of Pvt. Ltd. The use, disclosure, reproduction, modification, transfer, or transmittal of this work for any purpose in any form or by any means without the written permission of Pvt. Ltd is strictly prohibited.


## &nbsp;  &nbsp;  &nbsp; &nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp;CONFIDENTIAL, UNPUBLISHED PROPERTY
##  &nbsp; &nbsp;  &nbsp;  &nbsp; &nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp;OF
##  &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp;&nbsp;  &nbsp;  &nbsp; &nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp;&nbsp;&nbsp;PVT. LTD.


&nbsp;
&nbsp;

---

## Revision History
| Version |	&nbsp; &nbsp;&nbsp; &nbsp;&nbsp; &nbsp; Remark | &nbsp; &nbsp;&nbsp; Author | Reviewed By |	&nbsp;  &nbsp; Date |
| --- | --- | --- | --- | --- |
|1.0 | Initial Draft | Niranjan Patil | &nbsp; &nbsp;&nbsp; &nbsp;&nbsp; &nbsp; N.P | 24/10/24 |
|1.1|Adding Services|Niranjan Patil	|&nbsp; &nbsp;&nbsp; &nbsp;&nbsp; &nbsp; N.P |28/10/24|
|1.2|Adding Snapshot|Niranjan Patil	|&nbsp; &nbsp;&nbsp; &nbsp;&nbsp; &nbsp; N.P |11/12/24|

## List of Abbreviations
| Abbreviation | Description |
|---|---|
|  &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; C	| It represents “Conditional” |
|  &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; F	| It represents “Fail” |
|  &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; S	| It represents “Success” |
|  &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; Y | It represents “Yes” |
|  &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;IN | It represents “India” |
|  &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; IUS | It Denotes “ICICI-United State” |
 &nbsp;
 &nbsp;
 &nbsp;
  ----
## Contents
- [Overview](#1)
 - [API Authentication:](#2)
 - [Transport Method:](#3)
 - [Request Method](#4)
 - [Content Type](#5)
 - [Base URL:](#6)
 - [Common Request Format:](#7)
 - [Section-I: Ach Add account Flow](#8)
 1. [Validate-Routing-Number](#8.1)
 2. [Add-Ach-Bank-Accounts](#8.2)
 3. [Ach-Account-Lists](#8.3)
 4. [Ach-Account-Details](#8.4)
 5. [Modify-Ach-Account](#8.5)
 6. [Delete-Ach-Account](#8.6)
 7. [Sub-Dollar-Verify](#8.7)

- [Error Code Handling](#9)

- ---
## Overview
The Financial Application API allows developers to integrate financial data and services into their applications. This API provides access to account information, transaction history, market data, and more. The following documentation outlines the available endpoints, request formats, and response structures
## API Authentication:
Authentication is the process of verifying the identity of a user or system. It ensures that individuals accessing a resource are who they claim to be. This process typically involves the use of credentials, such as usernames and passwords, biometric data, or authentication tokens.
In a digital context, authentication is crucial for securing sensitive information and preventing unauthorized access. It can take various forms, including:
- Basic Authentication: Involves a simple username and password combination.
- Two-Factor Authentication (2FA): Requires two forms of verification, such as a password and a code sent to a mobile device.
- OAuth: A protocol that allows third-party applications to access user data without sharing passwords.
Effective authentication enhances security and helps protect against identity theft, data breaches,
## Transport Method: 
Secured restful APIs over HTTPS
## Request Method: 
GET, DELETE, POST, PATCH, PUT
## Content Type: 
”application/json”
## Base URL:
https://{qaone.remit.in}/services
## Common Request Format:
|Header|  |   | 
|---| --- | --- | 
|Content-Type|Mandatory|	application/json|
Accept	|Mandatory	|application/json|
X-Api-Key|	Mandatory|	White’s will provide when setting up the customer to use the service|
---

## Section-I: Ach Add account Flow
### 1. Validate-Routing-Number

**HTTP Method: POST**
**Endpoint:** validate-routing-number
**URL:**`https://{URL}/services/usr/acc/validate-routing-number`

**Request Example**
```
{
    "requestId": "154222",
    "requestType": "RoutingNumberData",
    "channelId": "WEB",
    "clientId": "IUS",
    "groupId": "IUS",
    "sessionId": "5RC0BY7ckyCV9JL0_xgg_HCkwMmUQUSsvzjYPzRk",
    "ipAddress": "127.0.0.1",
    "countryCode": "US",
    "routingNumber": "000300258"
}
``` 
**Request Attributes**
| Parameter       | Parameter Type | Mandatory | Length   | Description                                                  | Sample Value        |
|-----------------|----------------|-----------|----------|--------------------------------------------------------------|---------------------|
| requestId       | String         | Y         | 4-20     | A unique request ID generated at Front-end's end             | 154222              |
| requestType     | String         | Y         | 5-30     | The same value mentioned in the sample request must be used  | RoutingNumberData   |
| channelId       | String         | Y         | 4-20     | A unique request ID generated at Front-end's end             | WEB                 |
| clientId        | String         | Y         | 5-20     | IUS for US instance, IUS for United States instance          | "IUS"               |
| groupId         | String         | Y         | 5-20     | IUS for US instance, IUS for United States instance          | "IUS"               |
| sessionId       | String         | Y         | 5-20     | Unique session ID generated at Front-end's end               | 5RC0BY7ckyCV9       |
|                 |                |           |          |                                                              | JL0_xgg_HCkwMm      |
|                 |                |           |          |                                                              | UQUSsvzjYPzRk       |
| ipAddress       | String         | Y         | 5-60     | IP of the remitter                                           | 127.0.0.1           |
| countryCode     | String         | C         | 2        | Country code                                                 | “US”                |
| routingNumber   | String         |           |          | Routing Number                                               | "000300258"         |

**Response**
```
{
    "responseId": "504173",
    "requestId": "154222",
    "responseType": "ROUTINGNUMBERDATA",
    "groupId": "IUS",
    "token": null,
    "status": "S",
    "message": "Valid Routing Number",
    "errorCode": null,
    "errorMessage": null,
    "errorList": null,
    "userRefIdInfo": null,
    "bankName": "Test Bank",
    "branchName": "",
    "isYodleeSupported": "Y"
}
```
 
**Response Attributes**

| Parameter        | Parameter Type | Mandatory | Length      | Description                                                                 | Sample Value                        |
|------------------|----------------|-----------|-------------|-----------------------------------------------------------------------------|-------------------------------------|
| responseId       | String         | Y         | 5 - 20      | A unique ID to identify the Response                                        | null                                |
| requestId        | String         | Y         | 4 - 20      | A unique ID to identify the Request                                         | null                                |
| responseType     | String         | Y         | 5 - 30      | Value to identify the type of response. (Provided in the response sample)   | null                                |
| groupId          | String         | Y         | 5 - 20      | A Unique ID to identify the Corridor. Eg: “IUS”                             | null                                |
| token            | String         | N         | 5 - 128     | This is a unique Id for token number                                        | null                                |
| status           | String         | Y         | 1           | S - Registration successful. Call Login API, F - Registration unsuccessful. Ask the remitter to register again. | "S"                                 |
| message          | String         | Y         | Up to 100   | This will denote the message after the response. If status is “S”, the message will have the value | RIB data Added Successfully        |
| errorCode        | String         | C         | Up to 100   | This will denote the error code if any error occurs in the response. If status is “F” the error code will have the value. | null                                |
| errorMessage     | String         | C         | Up to 100   | This will denote the error message if any error occurs in the response. If status is “F” the error message will have the value. | null                                |
| errorList        | Array          | C         | Up to 100   | This will denote the list of errors                                          | null                                |
| userRefIdInfo    | String         |           |             |                                                                             | null                                |
| bankName         | String         | C         | 2 - 100     | This denotes the bank name                                                  | Test Bank                           |
| branchName       | String         |           |             |                                                                             |                                     |
| isYodleeSupported| String         |           |             |                                                                             | “Y”                                 |
&nbsp;
&nbsp;
&nbsp;
&nbsp;
---
## Error Response
```

```

## Error Response Attributes

| Parameter       | Parameter Type | Description |
|-----------------|----------------|-------------|
|                 |                |             |
|                 |                |             |
|                 |                |             |
|                 |                |             |
|                 |                |             |
|                 |                |             |
|                 |                |             |
|                 |                |             |

---
### 2. Add-Ach-Bank-Accounts

**HTTP Method: POST**
**Endpoint:** add-ach-bank-accounts
**URL:**`https://{URL}/services/usr/acc/add-ach-bank-account`

**Request Example**
```
{
    "requestId": "15403",
    "requestType": "ADDACHACCOUNT",
    "sessionId": "5RC0BY7ckyCV9JL0_xgg_HCkwMmUQUSsvzjYPzRk",
    "ipAddress": "192.168.14.187",
    "channelId": "WEB",
    "clientId": "IUS",
    "groupId": "IUS",
    "userId": "{{userId}}",
    "routingNumber": "000300258",
    "nickname": "myach_test3",
    "accountHolder": "Rahul Inajmuri",
    "bankName": "Test Bank",
    "accountNo": "10156654622",
    "accountType": "C",
    "countryCode": "US",
    "currencyCode": "USD"
}

``` 
**Request Attributes**
| Parameter        | Parameter Type | Mandatory | Length  | Description                                                          | Sample Value     |
|------------------|----------------|-----------|---------|----------------------------------------------------------------------|------------------|
| requestId        | String         | Y         | 4-20    | A unique request ID generated at Front-end' end                       | 15403            |
| requestType      | String         | Y         | 5 - 30  | The same value mentioned in the sample request must be used            | ADDACHACCOUNT    |
| sessionId        | String         | Y         | 5 - 20  | Unique session ID generated at Front-end' end                         | 5RC0BY7ckyCV9JL0 |
| _xgg_HCkwMmUQ    |                |           |         |                                                                      | USsvzjYPzRk      |
| ipAddress        | String         | Y         | 5 - 60  | IP of the remitter                                                   | 192.168.14.187  |
| channelId        | String         | Y         | 4-20    | A unique request ID generated at Front-end' end                       | WEB              |
| clientId         | String         | Y         | 5 - 20  | IUS for US instance, IUS for Unites State instance                    | "IUS"            |
| groupId          | String         | Y         | 5 - 20  | IUS for US instance, IUS for Unites State instance                    | "IUS"            |
| userId           | String         | Y         | 8-19    | User Id is the unique identifier of the remitter in ORP. This must be used in all subsequent post login API’s |                  |
| routingNumber    | String         |           |         | Routing Number                                                       | "000300258"      |
| nickname         | String         | Y         | 3-20    | Nickname entered by the remitter                                      | myach_test3      |
| accountHolder    |                |           |         |                                                                      | Rahul Inajmuri   |
| bankName         | String         | C         | 2-100   | This denotes the bank name                                            | Test Bank        |
| accountNo        | String         | Y         | 5-30    | This denotes the account number                                       | 10156654622      |
| accountType      |                |           |         |                                                                      | C                |
| countryCode      | String         | C         | 2       | This denotes the country code                                         | US               |
| currencyCode     | String         | Y         | 3       | This denotes the currencyCode                                         | USD              |

**Response**
```
{
    "responseId": "510390",
    "requestId": "15403",
    "responseType": "ADDACHACCOUNT",
    "groupId": "IUS",
    "token": null,
    "status": "S",
    "message": "Accounts added successfully",
    "errorCode": null,
    "errorMessage": null,
    "errorList": null,
    "userRefIdInfo": null,
    "processType": "YODLEE",
    "achaccId": "119566"
}

```
 
**Response Attributes**

| Parameter        | Parameter Type | Mandatory | Length  | Description                                                          | Sample Value          |
|------------------|----------------|-----------|---------|----------------------------------------------------------------------|-----------------------|
| responseId       | String         | Y         | 5 - 20  | A unique ID to identify the response                                  | 510390                |
| requestId        | String         | Y         | 4-20    | A unique ID to identify the Request                                   | 15403                 |
| responseType     | String         | Y         | 5 - 30  | Value to identify the type of response. (Provided in the response sample) | ADDACHACCOUNT        |
| groupId          | String         | Y         | 5 - 20  | A Unique ID to identify the Corridor. Eg: “IUS”                       | IUS                   |
| token            | String         | N         | 5 - 128 | This is a unique Id for token number                                  | null                  |
| status           | String         | Y         | 1       | S- Registration successful. Call Login API F-Registration unsuccessful. Ask the remitter to register again. | "S"                  |
| message          | String         | Y         | Up to 100| This will denote the message after the response. If status is “S” the message will have the value | Accounts added successfully |
| errorCode        | String         | C         | Up to 100| This will denote the error code if any error occurs in the response. If status is “F” the error code will have the value. | null                  |
| errorMessage     | String         | C         | Up to 100| This will denote the error message if any error occurs in the response. If status is “F” the error message will have the value. | null                  |
| errorList        | Array          | C         | Up to 100| This will denote the list of errors                                   | null                  |
| userRefIdInfo    |                |           |         |                                                                      | null                  |
| ProcessType      |                |           |         |                                                                      | YODLEE                |
| achaccId         |                |           |         |                                                                      | 119566                |
&nbsp;

---
## Error Response
```

```

## Error Response Attributes

| Parameter       | Parameter Type | Description |
|-----------------|----------------|-------------|
|                 |                |             |
|                 |                |             |
|                 |                |             |
|                 |                |             |
|                 |                |             |
|                 |                |             |
|                 |                |             |
|                 |                |             |
---
### 3. Ach-Account-Lists

**HTTP Method: POST**
**Endpoint:** ach-account-lists
**URL:** `https://{URL}/services/usr/acc/ach-account-lists`


**Request Example**
```
{
    "requestId": "15403",
    "requestType": "ACHACCOUNTLIST",
    "sessionId": "5RC0BY7ckyCV9JL0_xgg_HCkwMmUQUSsvzjYPzRk",
    "ipAddress": "192.168.14.187",
    "channelId": "WEB",
    "clientId": "IUS",
    "groupId": "IUS",
    "userId": "{{userId}}",
    "countryCode": "US",
    "recvNickName": "",
    "startIndex": "0",
    "statusFlag": "",
    "recordsPerRequest": "100",
    "isSameBank": ""
}
``` 
**Request Attributes**
| Parameter        | Parameter Type | Mandatory | Length  | Description                                                          | Sample Value          |
|------------------|----------------|-----------|---------|----------------------------------------------------------------------|-----------------------|
| requestId        | String         | Y         | 4-20    | A unique request ID generated at Front-end' end                       | 15403                 |
| requestType      | String         | Y         | 5 - 30  | The same value mentioned in the sample request must be used           | ACHACCOUNTLIST        |
| sessionId        | String         | Y         | 5 - 20  | Unique session ID generated at Front-end' end                         | 5RC0BY7ckyCV9JL0      |
| _xgg_HCkwMmU     |                |           |         |                                                                      | QUSsvzjYPzRk          |
| ipAddress        | String         | Y         | 5 - 60  | IP of the remitter                                                   | 192.168.14.187        |
| channelId        | String         | Y         | 4-20    | A unique request ID generated at Front-end' end                       | WEB                   |
| clientId         | String         | Y         | 5 - 20  | IUS for US instance, IUS for Unites State instance                    | IUS                   |
| groupId          | String         | Y         | 5 - 20  | IUS for US instance, IUS for Unites State instance                    | IUS                   |
| userId           | String         | Y         | 8-19    | User Id is the unique identifier of the remitter in ORP. This must be used in all subsequent post login API’s |                       |
| countryCode      | String         | C         | 2       | This denotes the country code                                         | US                    |
| recvNickName     | String         | Y         | 3-20    | If the API is being called on the Send Money screen, then recvNickName should be newbene_sp if it is an ORP BACKEND beneficiary or it should be newbene if it is a non ORP BACKEND beneficiary. If the API is being called after beneficiary selection then you must pass the beneficiary nickname. |                       |
| startIndex       | String         | N         | 1-5     | This denotes the start index                                          |                       |
| statusFlag       |                |           |         |                                                                      |                       |
| recordsPerRequest|                |           |         |                                                                      |                       |
| isSameBank       |                |           |         |                                                                      |                       |


**Response**
```
{
    "responseId": "510391",
    "requestId": "15403",
    "responseType": "ACHACCOUNTLIST",
    "groupId": "IUS",
    "token": null,
    "status": "S",
    "message": "Success",
    "errorCode": null,
    "errorMessage": null,
    "errorList": null,
    "userRefIdInfo": null,
    "responseData": [
        {
            "instaReceiver": "N",
            "recordToken": "0D6F952F278F347D4387880142DB2A9C32142F61E3BFBE1AAAA157F026FAD72D",
            "aCHAccId": "119566",
            "nickName": "MYACH_TEST4",
            "isSameBank": "N",
            "accountType": "C",
            "createdDateTZ": "2025-02-04 21:37:25.11",
            "bankName": "Test Bank",
            "viaIdPayment": "",
            "sendCountry": "US-USD",
            "accountHolderName": "RAHUL INAJMURI",
            "instaTransfer": "N",
            "routingNumber": "********0258",
            "recordStatus": "P",
            "createdDate": "2025-02-05 08:07:25.11",
            "accountNo": "********4622",
            "isLoginRequired": "",
            "vendorAccountId": "",
            "vendorAccessToken": ""
        },
        {
            "instaReceiver": "N",
            "recordToken": "0D6F952F278F347D4387880142DB2A9C8E0278E3722498141051057107117933",
            "aCHAccId": "119565",
            "nickName": "MYACH_TEST3",
            "isSameBank": "N",
            "accountType": "C",
            "createdDateTZ": "2025-02-03 22:12:11.02",
            "bankName": "Test Bank",
            "viaIdPayment": "",
            "sendCountry": "US-USD",
            "accountHolderName": "RAHUL INAJMURI",
            "instaTransfer": "N",
            "routingNumber": "********0258",
            "recordStatus": "R",
            "createdDate": "2025-02-04 08:42:11.02",
            "accountNo": "********6546",
            "isLoginRequired": "",
            "vendorAccountId": "",
            "vendorAccessToken": ""
        },
        {
            "instaReceiver": "N",
            "recordToken": "D07FC04B9A0721E08027318168EAC0B36FD93F1C34CA4B30C2E4484BB208BC68",
            "aCHAccId": "119545",
            "nickName": "MYACH_TEST2",
            "isSameBank": "N",
            "accountType": "C",
            "createdDateTZ": "2025-01-09 01:28:52.76",
            "bankName": "Test Bank",
            "viaIdPayment": "",
            "sendCountry": "US-USD",
            "accountHolderName": "RAHUL INAJMURI",
            "instaTransfer": "N",
            "routingNumber": "********0258",
            "recordStatus": "P",
            "createdDate": "2025-01-09 11:58:52.76",
            "accountNo": "********6545",
            "isLoginRequired": "",
            "vendorAccountId": "",
            "vendorAccessToken": ""
        },
        {
            "instaReceiver": "N",
            "recordToken": "D07FC04B9A0721E08027318168EAC0B30F0440AC79F1489EC090FD614AF27DA0",
            "aCHAccId": "119544",
            "nickName": "MYACH_TEST",
            "isSameBank": "N",
            "accountType": "C",
            "createdDateTZ": "2025-01-09 01:17:55.133",
            "bankName": "Test Bank",
            "viaIdPayment": "",
            "sendCountry": "US-USD",
            "accountHolderName": "RAHUL INAJMURI",
            "instaTransfer": "N",
            "routingNumber": "********0258",
            "recordStatus": "P",
            "createdDate": "2025-01-09 11:47:55.133",
            "accountNo": "********7032",
            "isLoginRequired": "",
            "vendorAccountId": "",
            "vendorAccessToken": ""
        },
        {
            "instaReceiver": "N",
            "recordToken": "D07FC04B9A0721E08027318168EAC0B3B2591D3058FA029CD3668C63BA7AA03F",
            "aCHAccId": "119542",
            "nickName": "MYACH",
            "isSameBank": "N",
            "accountType": "C",
            "createdDateTZ": "2025-01-08 01:41:35.727",
            "bankName": "Test Bank",
            "viaIdPayment": "",
            "sendCountry": "US-USD",
            "accountHolderName": "RAHUL INAJMURI",
            "instaTransfer": "N",
            "routingNumber": "********0258",
            "recordStatus": "P",
            "createdDate": "2025-01-08 12:11:35.727",
            "accountNo": "********2224",
            "isLoginRequired": "",
            "vendorAccountId": "",
            "vendorAccessToken": ""
        },
        {
            "instaReceiver": "N",
            "recordToken": "458D81BD1BD473774DC636C4EC6F945BD99BE4898960B521B6B7714B6E0EDED8",
            "aCHAccId": "12555",
            "nickName": "DARSH1",
            "isSameBank": "Y",
            "accountType": "C",
            "createdDateTZ": "2024-11-06 03:01:34.24",
            "bankName": "ICICI BANK US",
            "viaIdPayment": "",
            "sendCountry": "US-USD",
            "accountHolderName": "DARSHANA NINAWE",
            "instaTransfer": "N",
            "routingNumber": "********3243",
            "recordStatus": "Y",
            "createdDate": "2024-11-06 13:31:34.24",
            "accountNo": "********2493",
            "isLoginRequired": "",
            "vendorAccountId": "",
            "vendorAccessToken": ""
        }
    ],
    "hasNext": "0"
}

```
 
**Response Attributes**

| Parameter        | Parameter Type | Mandatory | Length  | Description                                                          | Sample Value          |
|------------------|----------------|-----------|---------|----------------------------------------------------------------------|-----------------------|
| responseId       | String         | Y         | 5 - 20  | A unique ID to identify the response                                  | null                  |
| requestId        | String         | Y         | 4-20    | A unique ID to identify the Request                                   | null                  |
| responseType     | String         | Y         | 5 - 30  | Value to identify the type of response. (Provided in the response sample) | null                  |
| groupId          | String         | Y         | 5 - 20  | A Unique ID to identify the Corridor. Eg: “IUS”                       | null                  |
| token            | String         | N         | 5 - 128 | This is a unique Id for token number                                  | null                  |
| status           | String         | Y         | 1       | S- Registration successful. Call Login API F-Registration unsuccessful. Ask the remitter to register again. | "S"                  |
| message          | String         | Y         | Up to 100| This will denote the message after the response. If status is “S” the message will have the value | RIB data Added Successfully |
| errorCode        | String         | C         | Up to 100| This will denote the error code if any error occurs in the response. If status is “F” the error code will have the value. | null                  |
| errorMessage     | String         | C         | Up to 100| This will denote the error message if any error occurs in the response. If status is “F” the error message will have the value. | null                  |
| errorList        | Array          | C         | Up to 100| This will denote the list of errors                                   | null                  |
| userRefIdInfo    |                |           |         |                                                                      | null                  |
| responseData     |                |           |         |                                                                      |                       |

&nbsp;

---
## Error Response
```

```

## Error Response Attributes

| Parameter       | Parameter Type | Description |
|-----------------|----------------|-------------|
|                 |                |             |
|                 |                |             |
|                 |                |             |
|                 |                |             |
|                 |                |             |
|                 |                |             |
|                 |                |             |
|                 |                |             |
---
### 4. Ach-Account-Details

**HTTP Method: POST**
**Endpoint:** ach-account-details
**URL:**`https://{URL}/services/usr/acc/ach-account-details`

**Request Example**
```
{
    "requestId": "15403",
    "requestType": "ACHAccountDetails",
    "sessionId": "5RC0BY7ckyCV9JL0_xgg_HCkwMmUQUSsvzjYPzRk",
    "ipAddress": "192.168.14.187",
    "channelId": "WEB",
    "clientId": "IUS",
    "groupId": "IUS",
    "userId": "{{userId}}",
    " achAccId ": "119542",
    "recordToken": "D07FC04B9A0721E08027318168EAC0B3B2591D3058FA029CD3668C63BA7AA03F"
}


``` 
**Request Attributes**
| Parameter      | Parameter Type | Mandatory | Length | Description                                                | Sample Value         |
|----------------|----------------|-----------|--------|------------------------------------------------------------|----------------------|
| requestId      | String         | Y         | 4-20   | A unique request ID generated at Front-end' end             | 15403                |
| requestType    | String         | Y         | 5-30   | The same value mentioned in the sample request must be used | ACHACCOUNTLIST       |
| sessionId      | String         | Y         | 5-20   | Unique session ID generated at Front-end' end               | 5RC0BY7ckyCV9JL0_xgg_HCkwMmUQUSsvzjYPzRk |
| ipAddress      | String         | Y         | 5-60   | IP of the remitter                                          | 192.168.14.187       |
| channelId      | String         | Y         | 4-20   | A unique request ID generated at Front-end' end             | WEB                  |
| clientId       | String         | Y         | 5-20   | IUS for US instance, IUS for United States instance         | IUS                  |
| groupId        | String         | Y         | 5-20   | IUS for US instance, IUS for United States instance         | IUS                  |
| userId         | String         | Y         | 8-19   | User ID is the unique identifier of the remitter in ORP     | {{userId}}           |
| achAccId       | String         |           |        | ACH account ID                                              | 119542               |
| recordToken    | String         |           |        | Token used to track the record                             | D07FC04B9A0721E08027318168EAC0B3B2591D3058FA029CD3668C63BA7AA03F |


**Response**
```
{
    "responseId": "510393",
    "requestId": "15403",
    "responseType": "ACHACCOUNTDETAILS",
    "groupId": "IUS",
    "token": null,
    "status": "S",
    "message": "Success",
    "errorCode": null,
    "errorMessage": null,
    "errorList": null,
    "userRefIdInfo": null,
    "countryCode": "US",
    "currencyCode": "USD",
    "accountHolderName": "RAHUL INAJMURI",
    "accountNo": "********2224",
    "bankName": "Test Bank",
    "accountType": "C",
    "routingNumber": "********0258",
    "recordStatus": "P",
    "createdDate": "2025-01-08 12:11:35",
    "nickName": "MYACH",
    "vendorAccountId": "",
    "vendorAccessToken": ""
}

```
 
**Response Attributes**

| Parameter           | Parameter Type | Mandatory | Length | Description                                                       | Sample Value         |
|---------------------|----------------|-----------|--------|-------------------------------------------------------------------|----------------------|
| responseId          | String         | Y         | 4-20   | A unique request ID generated at Front-end' end                    | 510393               |
| requestId           | String         | Y         | 5-30   | The same value mentioned in the sample request must be used        | 15403                |
| responseType        | String         | Y         | 5-20   | Unique session ID generated at Front-end' end                      | ACHACCOUNTDETAILS    |
| groupId             | String         | Y         | 5-60   | IP of the remitter                                                | IUS                  |
| token               | Null           | Y         | 4-20   | A unique request ID generated at Front-end' end                    | null                 |
| status              | String         | Y         | 5-20   | IUS for US instance, IUS for United States instance                | S                    |
| message             | String         | Y         | 5-20   | IUS for US instance, IUS for United States instance                | Success              |
| errorCode           | Null           | Y         | 8-19   | User ID is the unique identifier of the remitter in ORP. This must be used in all subsequent post-login API's | null                 |
| errorMessage        | String         | C         | Up to 100 | Denotes the error message if any error occurs in the response     | null                 |
| errorList           | Array          | C         | Up to 100 | Denotes the list of errors                                         | null                 |
| userRefIdInfo       | String         |           |        | Additional user reference information                              | null                 |
| countryCode         | String         | C         | 2      | Denotes country code                                              | US                   |
| currencyCode        | String         | Y         | 3      | Denotes the currency code                                          | USD                  |
| accountHolderName   | String         |           |        | The name of the account holder                                     | RAHUL INAJMURI       |
| accountNo           | String         | Y         | 5-30   | The account number                                                 | ********2224         |
| bankName            | String         | C         | 2-100  | Denotes the bank name                                              | Test Bank            |
| accountType         | String         |           |        | Type of the account (e.g., checking, savings)                     | C                    |
| routingNumber       | String         |           |        | Denotes the routing number                                         | ********0258         |
| recordStatus        | String         |           |        | Status of the account record                                       | P                    |
| createdDate         | String         |           |        | Date when the account was created                                  | 08-01-2025 12:11     |
| nickName            | String         | Y         | 3-20   | Nickname entered by the remitter                                   | MYACH                |
| vendorAccountId     | String         |           |        | Vendor account ID                                                  | (empty)              |
| vendorAccessToken   | String         |           |        | Vendor access token                                                | (empty)              |

&nbsp;

---
### Error Response
```

```

### Error Response Attributes

| Parameter       | Parameter Type | Description |
|-----------------|----------------|-------------|
|                 |                |             |
|                 |                |             |
|                 |                |             |
|                 |                |             |
|                 |                |             |
|                 |                |             |
|                 |                |             |
|                 |                |             |
---
### 5.	Modify-Ach-Account

**HTTP Method: POST**
**Endpoint:** modify-ach-account
**URL:**`https://{URL}/services/usr/acc/modify-ach-account`

**Request Example**
```
{
    "requestId": "15403",
    "requestType": "ModifyACHAccount",
    "sessionId": "5RC0BY7ckyCV9JL0_xgg_HCkwMmUQUSsvzjYPzRk",
    "ipAddress": "192.168.14.187",
    "channelId": "WEB",
    "clientId": "IUS",
    "groupId": "IUS",
    "userId": "{{userId}}",
    "achAccId": "119542",
    "routingNumber": "000300258",
    "nickname": "myach",
    "accountHolder": "Rahul Inajmuri",
    "bankName": "Test Bank",
    "accountNo": "63336692224",
    "accountType": "C",
    "countryCode": "US",
    "currencyCode": "USD",
    "recordToken": "D07FC04B9A0721E08027318168EAC0B3B2591D3058FA029CD3668C63BA7AA03F"
}

``` 
**Request Attributes**
| Parameter        | Parameter Type | Mandatory | Length   | Description                                                       | Sample Value         |
|------------------|----------------|-----------|----------|-------------------------------------------------------------------|----------------------|
| requestId        | String         | Y         | 4-20     | A unique request ID generated at Front-end' end                    | 15403                |
| requestType      | String         | Y         | 5-30     | The same value mentioned in the sample request must be used        | ModifyACHAccount       |
| sessionId        | String         | Y         | 5-20     | Unique session ID generated at Front-end' end                      | 5RC0BY7ckyCV9JL0_xgg_HCkwMmUQUSsvzjYPzRk |
| ipAddress        | String         | Y         | 5-60     | IP of the remitter                                                | 192.168.14.187       |
| channelId        | String         | Y         | 4-20     | A unique request ID generated at Front-end' end                    | WEB                  |
| clientId         | String         | Y         | 5-20     | IUS for US instance, IUS for United States instance                | IUS                  |
| groupId          | String         | Y         | 5-20     | IUS for US instance, IUS for United States instance                | IUS                  |
| userId           | String         | Y         | 8-19     | User ID is the unique identifier of the remitter in ORP. This must be used in all subsequent post-login API’s | [userId]             |
| achAccId         | String         |           |          | ACH account ID associated with the remitter                        | 119542               |
| routingNumber    | String         |           |          | The routing number of the bank account                             | 000300258            |
| nickname         | String         |           |          | The nickname entered by the remitter                               | myach                |
| accountHolder    | String         |           |          | Name of the account holder                                         | Rahul Inajmuri       |
| bankName         | String         |           | 2-100    | Name of the bank                                                   | Test Bank            |
| accountNo        | String         |           | 5-30     | The account number                                                 | 63336692224          |
| accountType      | String         |           |          | Type of the bank account (e.g., checking, savings)                 | C                    |
| countryCode      | String         |           | 2        | The country code                                                   | US                   |
| currencyCode     | String         |           | 3        | Currency code for the account                                      | USD                  |
| recordToken      | String         |           |          | Token for identifying the record                                   | D07FC04B9A0721E08027318168EAC0B3B2591D3058FA029CD3668C63BA7AA03F |

**Response**
```
{
    "responseId": "510468",
    "requestId": "15403",
    "responseType": "MODIFYACHACCOUNT",
    "groupId": "IUS",
    "status": "S",
    "message": "Record Modified Successfully",
    "errorCode": null,
    "errorMessage": null,
    "errorList": null,
    "userRefIdInfo": null,
    "processType": null,
    "achaccId": null
}


```
 
**Response Attributes**

| Parameter        | Parameter Type | Mandatory | Length   | Description                                                      | Sample Value               |
|------------------|----------------|-----------|----------|------------------------------------------------------------------|----------------------------|
| responseId       | String         | Y         | 4-20     | Unique identifier for the response.                              | 510468                     |
| requestId        | String         | Y         | 5 - 30   | Unique identifier for the request.                               | 15403                      |
| responseType     | String         | Y         | 5 - 20   | Type of the response.                                            | MODIFYACHACCOUNT           |
| groupId          | String         | Y         | 5 - 60   | The group identifier associated with the request.                | IUS                        |
| status           | String         | Y         | 4-20     | The status of the response (e.g., success or failure).           | S                          |
| message          | String         | Y         | 5 - 20   | The message describing the result of the operation.              | Record Modified Successfully |
| errorCode        | Null           | Y         | 5 - 20   | Code indicating an error (null if no error).                     | null                       |
| errorMessage     | Null           | Y         | 8-19     | Error message (null if no error).                                 | null                       |
| errorList        | Null           | C         | Up to 100| List of errors, if any (null if no errors).                      | null                       |
| userRefIdInfo    | Null           | C         | Up to 100| Reference information for the user, if provided.                | null                       |
| processType      | Null           |           |          | Process type (if applicable).                                    | null                       |
| achaccId         | Null           |           |          | ACH account ID associated with the request.                      | null                       |

&nbsp;

---
## Error Response
```

```

## Error Response Attributes

| Parameter       | Parameter Type | Description |
|-----------------|----------------|-------------|
|                 |                |             |
|                 |                |             |
|                 |                |             |
|                 |                |             |
|                 |                |             |
|                 |                |             |
|                 |                |             |
|                 |                |             |
---
### 6. Delete-Ach-Account

**HTTP Method: POST**
**Endpoint:** delete-ach-account
**URL:** `https://{URL} /services/usr/acc/delete-ach-account`

**Request Example**
```
{
    "requestId": "15403",
    "requestType": "DeleteACHAccount",
    "sessionId": "5RC0BY7ckyCV9JL0_xgg_HCkwMmUQUSsvzjYPzRk",
    "ipAddress": "192.168.14.187",
    "channelId": "WEB",
    "clientId": "IUS",
    "groupId": "IUS",
    "userId": "{{userId}}",
    "achAccId": "119542",
    "recordToken": "D07FC04B9A0721E08027318168EAC0B3B2591D3058FA029CD3668C63BA7AA03F"
}

``` 
**Request Attributes**
| Parameter      | Parameter Type | Mandatory | Length   | Description                                                      | Sample Value               |
|----------------|----------------|-----------|----------|------------------------------------------------------------------|----------------------------|
| requestId      | String         | Y         | 4-20     | A unique request ID generated at Front-end' end                  | 15403                      |
| requestType    | String         | Y         | 5 - 30   | The same value mentioned in the sample request must be used      | DeleteACHAccount           |
| sessionId      | String         | Y         | 5 - 20   | Unique session ID generated at Front-end' end                    | 5RC0BY7ckyCV9JL0_xgg_HCkwMmUQUSsvzjYPzRk |
| ipAddress      | String         | Y         | 5 - 60   | IP address of the remitter                                       | 192.168.14.187             |
| channelId      | String         | Y         | 4-20     | A unique request ID generated at Front-end' end                  | WEB                        |
| clientId       | String         | Y         | 5 - 20   | IUS for US instance, IUS for United States instance              | IUS                        |
| groupId        | String         | Y         | 5 - 20   | IUS for US instance, IUS for United States instance              | IUS                        |
| userId         | String         | Y         | 8-19     | User Id is the unique identifier of the remitter in ORP.         | (unique remitter id)       |
| achAccId       | String         | Y         |          | ACH Account ID to be deleted                                     | 119542                     |
| recordToken    | String         | Y         |          | A unique identifier for the record                              | D07FC04B9A0721E08027318168EAC0B3B2591D3058FA029CD3668C63BA7AA03F |

**Response**
```
{
    "responseId": "510486",
    "requestId": "15403",
    "responseType": "DELETEACHACCOUNT",
    "groupId": "IUS",
    "token": null,
    "status": "S",
    "message": "Record Deleted Successfully",
    "errorCode": null,
    "errorMessage": null,
    "errorList": null,
    "userRefIdInfo": null
}

```
 
**Response Attributes**

| Parameter      | Parameter Type | Mandatory | Length   | Description                                                          | Sample Value                    |
|----------------|----------------|-----------|----------|----------------------------------------------------------------------|---------------------------------|
| responseId     | String         | Y         | 4-20     | Unique identifier for the response.                                   | 510468                          |
| requestId      | String         | Y         | 5 - 30   | Unique identifier for the request.                                    | 15403                           |
| responseType   | String         | Y         | 5 - 20   | Type of the response.                                                 | MODIFYACHACCOUNT                |
| groupId        | String         | Y         | 5 - 60   | The group identifier associated with the request.                     | IUS                             |
| status         | String         | Y         | 4-20     | The status of the response (e.g., success or failure).                | S                               |
| message        | String         | Y         | 5 - 20   | The message describing the result of the operation.                   | Record Modified Successfully    |
| errorCode      | String         | Y         | 5 - 20   | Code indicating an error (null if no error).                          | null                            |
| errorMessage   | String         | Y         | 8-19     | Error message (null if no error).                                     | null                            |
| errorList      | String         | C         | Up to 100| List of errors, if any (null if no errors).                           | null                            |
| userRefIdInfo  | String         | C         | Up to 100| Reference information for the user, if provided.                     | null                            |


&nbsp;

---
## Error Response
```

```

## Error Response Attributes

| Parameter       | Parameter Type | Description |
|-----------------|----------------|-------------|
|                 |                |             |
|                 |                |             |
|                 |                |             |
|                 |                |             |
|                 |                |             |
|                 |                |             |
|                 |                |             |
|                 |                |             |
---		
### 7. Sub-Dollar-Verify

**HTTP Method: POST**
**Endpoint:** sub-dollar-verify
**URL:**` https://{URL}/services/usr/acc/sub-dollar-verify`

**Request Example**
```
{
    "requestId": "154222",
    "requestType": "SUBDOLLARVERIFY",
    "channelId": "WEB",
    "clientId": "IUS",
    "groupId": "IUS",
    "sessionId": "5RC0BY7ckyCV9JL0_xgg_HCkwMmUQUSsvzjYPzRk",
    "ipAddress": "127.0.0.1",
    "userId": "{{userId}}",
    "achAccId": "119565",
    "creditValue1": "0.80",
    "creditValue2": "0.22",
    "creditValue3": "0.00"
}


``` 
**Request Attributes**
| Parameter      | Parameter Type | Mandatory | Length   | Description                                                          | Sample Value                    |
|----------------|----------------|-----------|----------|----------------------------------------------------------------------|---------------------------------|
| requestId      | String         | Y         | 4-20     | A unique request ID generated at the Front-end's end.                 | 154222                          |
| requestType    | String         | Y         | 5 - 30   | The same value mentioned in the sample request must be used.          | SUBDOLLARVERIFY                 |
| channelId      | String         | Y         | 4-20     | A unique request ID generated at the Front-end's end.                 | WEB                             |
| clientId       | String         | Y         | 5 - 20   | IUS for US instance, IUS for United States instance.                  | IUS                             |
| groupId        | String         | Y         | 5 - 20   | IUS for US instance, IUS for United States instance.                  | IUS                             |
| sessionId      | String         | Y         | 5 - 20   | Unique session ID generated at the Front-end's end.                   | 5RC0BY7ckyCV9JL0_xgg_HCkwMmUQUSsvzjYPzRk |
| ipAddress      | String         | Y         | 5 - 60   | IP address of the remitter.                                           | 127.0.0.1                       |
| userId         | String         | Y         | 8-19     | User ID is the unique identifier of the remitter in ORP.              | (User ID to be provided)        |
| achAccId       | String         | Y         |          | ACH account ID.                                                       | 119565                          |
| creditValue1   | String         | Y         |          | Credit value 1 to be associated with the account.                     | 0.80                            |
| creditValue2   | String         | Y         |          | Credit value 2 to be associated with the account.                     | 0.22                            |
| creditValue3   | String         | Y         |          | Credit value 3 to be associated with the account.                     | 0.00                            |


**Response**
```
{
    "responseId": "510496",
    "requestId": "154222",
    "responseType": "SUBDOLLARVERIFY",
    "groupId": "IUS",
    "token": null,
    "status": "F",
    "message": null,
    "errorCode": "4704",
    "errorMessage": "You have entered incorrect amount(s) and have 2 more attempts remaining to enter the right amount(s). Please re-confirm the two amount(s) of less than 1 dollar credited to your accounts. Do not enter the debited amount.",
    "errorList": null,
    "userRefIdInfo": null
}


```
 
**Response Attributes**
| Parameter      | Parameter Type | Mandatory | Length   | Description                                                          | Sample Value                    |
|----------------|----------------|-----------|----------|----------------------------------------------------------------------|---------------------------------|
| responseId     | String         | Y         | 4-20     | Unique identifier for the response.                                   | 510496                          |
| requestId      | String         | Y         | 5 - 30   | Unique identifier for the request.                                    | 154222                          |
| responseType   | String         | Y         | 5 - 20   | Type of the response.                                                 | SUBDOLLARVERIFY                 |
| groupId        | String         | Y         | 5 - 60   | The group identifier associated with the request.                     | IUS                             |
| status         | String         | Y         | 4-20     | The status of the response (e.g., success or failure).                | S                               |
| message        | String         | Y         | 5 - 20   | The message describing the result of the operation.                   | Record Modified Successfully    |
| errorCode      | String         | Y         | 5 - 20   | Code indicating an error (null if no error).                          | null                            |
| errorMessage   | String         | Y         | 8-19     | Error message (null if no error).                                     | null                            |
| errorList      | String         | C         | Up to 100| List of errors, if any (null if no errors).                           | null                            |
| userRefIdInfo  | String         | C         | Up to 100| Reference information for the user, if provided.                     | null                            |

&nbsp;

---
## Error Response
```

```

## Error Response Attributes

| Parameter       | Parameter Type | Description |
|-----------------|----------------|-------------|
|                 |                |             |
|                 |                |             |
|                 |                |             |
|                 |                |             |
|                 |                |             |
|                 |                |             |
|                 |                |             |
|                 |                |             |
---		
# Error Code Handling
| Sr. No. | Error Code | Error Code Description                                                    | Error Reason                                                        |
|---------|------------|---------------------------------------------------------------------------|----------------------------------------------------------------------|
| 1       | 400        | "Bad Request", The server cannot process the request due to client error. | Check your request body and parameters for correctness.             |
| 2       | 401        | "One or more transport item types specified within the Freight is invalid."| One Or More Transport Item Types Is Invalid, Invalid Authentication |
| 3       | 403        | "The server understands the request but refuses to authorize it."         | Check permissions and ensure you have access to the resource.       |
| 4       | 404        | "The requested resource could not be found on the server."                | Verify the URL and endpoint you are trying to access.               |
| 5       | 405        | The request method is known by the server but is not supported by the target resource.| Ensure you are using the correct HTTP method (GET, POST, PUT, DELETE). |
| 6       | 409        | "Conflict", The request could not be completed due to a conflict with the current state of the resource.| Check for conflicts with existing data (e.g., trying to create a duplicate). |
| 7       | 500        | "Internal Server Error"                                                   | The server has encountered a situation it does not know how to handle. |




