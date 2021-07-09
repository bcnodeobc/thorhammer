Getting Started
---------------

Authorization Token
===================

1. Sign in into https://thankslogin.okbc.my/auth to receive token from Thanks Economy and https://integrationhub.okwave.global/api/v2/registerToken to receive token for internal.

Example::

    eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCIsImtpZCI6ImRpcUZ3QnVVVVFRWlZsNW96SUgtSmNIZTBiMkN6aDRUOGswNHNxTUlHekkifQ.eyJzdWIiOiJoaXNlbWFraXNlMzUxNEBnbWFpbC5jb20iLCJhdF9oYXNoIjoiSW5neVRGVW9nUHlFVWhnTGdta1BDZyIsImF1ZCI6IjRNcjViYTIyWnV5TjVWVlBMd0ZoZCIsImV4cCI6MTYwOTkwMTgwOCwiaWF0IjoxNjA5ODk4MjA4LCJpc3MiOiJodHRwczovL3RoYW5rc2F1dGgub2tiYy5teSJ9.PeIqWbM_HB40YirABFao-VFXBcSCebhcrB-zXI2qA4SvEl_aRWSOdKAfn-5Z0H_QSIevKyiu8-_i2kBSS7-4wVNTFYAE1PRse3d4XY91zWEi53qr7o2WdBVag1ZqKutkOIJmyOxMmT8Jbb2YNH5l9Fil05E7d030HPV-YTtKtRswsdDIGM3r2-9drLDYYLjBoUccYTJsyB2EAFtAICNikmlXXgUQhwESm__keXVl8tkdGLrUvvyy_bUGSHMofYuL7jTXauiMB3F37L2p1gTDiUNPSX3zJeUgKpqUgS6jIVTK2vsv9WBfb1BO1bXCo_08vQElLOBM46SIaMFklcJlxQ

2. Change header value under Authorization's key with token value from previous step.

.. note::  Use 'OBC <token>' for internal token


Request API
===========

---
BTC
---

1. Request API using **POST** method with url https://integrationhub.okwave.global/api/v2/ and body data ::

    {
        "version": 2,
        "blockchain": "BTC",
        "payload": {
            "method": "getblockcount",
            "parameter": {},
            "webhook": <User Webhook API>,
            "Id": <Unique ID>
        }
    } 

   1. **version** : Thorhammer's version.
   2. **blockchain** : Blockchain ( BTC/THORS/ETH ).
   3. **payload** : Contains of requested function and body data.
   4. **method** : Function API based on the node.
   5. **parameter** : Body for function called.
   6. **webhook** : Webhook API serve by user/developer to receive API response.
   7. **Id** : Unique Id for identification for user/developer task.

2. User/developer will received 'success' message after request and the result will be sent to the webhook API mentioned ::

    {
        "payload": {
        "method": "getblockcount",
        "parameter": {},
        "webhook": <User Webhook API>,
        "Id": <Unique ID>
        },
        "result": 690086
    }


--------
ETHEREUM
--------

1. Request API using **POST** method with url https://integrationhub.okwave.global/api/v2/ and body data ::

    {
        "version": 2,
        "blockchain": "ETH",
        "payload": {
            "class": "web3.eth",
            "method": "getBalance",
            "parameter": 
            {

            },
            "webhook": <User Webhook API>,
            "Id": <Unique ID>
        }
    } 

   1. **version** : Thorhammer's version.
   2. **blockchain** : Blockchain ( BTC/THORS/ETH ).
   3. **payload** : Contains of requested function and body data.
   4. **method** : Function API based on the node.
   5. **parameter** : Body for function called.
   6. **webhook** : Webhook API serve by user/developer to receive API response.
   7. **Id** : Unique Id for identification for user/developer task.

2. User/developer will received 'success' message after request and the result will be sent to the webhook API mentioned ::

    {
        "payload": {
            "method": "getBalance",
            "parameter":
            {
                "address": "0xceb21b8ce14e287a106bd01f5c92dac970c1efd3"
            },
            "webhook": <User Webhook API>,
            "Id": <Unique ID>
        },
        "result": "0"
    }


Authors
=======

* Aizu Zuyyin
* Mohamad Fazuan
* Shahrizal
* Ridzuan
* Hisham

.. note::  TEAM BLOCKCHAIN