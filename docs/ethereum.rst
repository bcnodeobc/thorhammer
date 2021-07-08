========
Ethereum
========

All RPC included are based on web3. 

Request URL : http://integrationhub.okwave.global/api/v2/

.. note::  Make sure to enter received token in headers using key 'Authorization'.

------------------------------------------------------------------------------

getTransaction
==============

The transaction matching that given transaction hash.

Headers
--------
Need to set headers::

    Key             Value

    Content-Type    application/json

    Authorization   OBC eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYW1lIjoib2JjIiwiaWF0IjoxNjAzMTU3NjMzLCJleHAiOjE2MDM3NjI0MzN9.71my1T-2IxQNJhNNu-aRX7N3TLo9BqAczyGWX1ph2vA

Parameters
--------
Need parameters::

    TransactionHash     The transaction hash.
                        {
                            "transactionHash": "0x9fc76417374aa880d4449a1f7f31ec597f00b1f6f3dd2d66f4c9c6c445836d8b§234"
                        }

Example
--------
Example JSON body::
    
    {
        "version": 2,
        "blockchain": "ETH",
        "payload": {
            "method": "getTransaction",
            "parameter":
            {
                "transactionHash": "0x9fc76417374aa880d4449a1f7f31ec597f00b1f6f3dd2d66f4c9c6c445836d8b§234"
            },
            "webhook": <User Webhook API>,
            "Id": <Unique ID>
        }
    }

Response
--------
Results::

    {
        "status": 200,
        "values":  {
            "hash": "0x9fc76417374aa880d4449a1f7f31ec597f00b1f6f3dd2d66f4c9c6c445836d8b",
            "nonce": 2,
            "blockHash": "0xef95f2f1ed3ca60b048b4bf67cde2195961e0bba6f70bcbea9a2c4e133e34b46",
            "blockNumber": 3,
            "transactionIndex": 0,
            "from": "0xa94f5374fce5edbc8e2a8697c15331677e6ebf0b",
            "to": "0x6295ee1b4f6dd65047762f924ecd367c17eabf8f",
            "value": '123450000000000000',
            "gas": 314159,
            "gasPrice": '2000000000000',
            "input": "0x57cb2fc4"
        }
    }

------------------------------------------------------------------------------

getTransactionCount
===================

The number of transactions sent from this address.

Headers
--------
Need to set headers::

    Key             Value

    Content-Type    application/json

    Authorization   OBC eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYW1lIjoib2JjIiwiaWF0IjoxNjAzMTU3NjMzLCJleHAiOjE2MDM3NjI0MzN9.71my1T-2IxQNJhNNu-aRX7N3TLo9BqAczyGWX1ph2vA

Parameters
--------
Need parameters::

    Address     The address to get the numbers of transactions from
                {
                    "address": "0xceb21b8ce14e287a106bd01f5c92dac970c1efd3"
                }

Example
--------
Example JSON body::
    
    {
        "version": 2,
        "blockchain": "ETH",
        "payload": {
            "method": "getTransactionCount",
            "parameter":
            {
                "address": "0xceb21b8ce14e287a106bd01f5c92dac970c1efd3"
            },
            "webhook": <User Webhook API>,
            "Id": <Unique ID>
        }
    }

Response
--------
Results::

    {
        "status": 200,
        "values": 0
    }

------------------------------------------------------------------------------

getTransactionFromBlock
=======================

The transaction based on a block hash or number and the transaction’s index position.

Headers
--------
Need to set headers::

    Key             Value

    Content-Type    application/json

    Authorization   OBC eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYW1lIjoib2JjIiwiaWF0IjoxNjAzMTU3NjMzLCJleHAiOjE2MDM3NjI0MzN9.71my1T-2IxQNJhNNu-aRX7N3TLo9BqAczyGWX1ph2vA

Parameters
--------
Need parameters::

    HashString          Block number or hash and the transaction’s index position
    indexNumber         {
                            "hashString": "0xef95f2f1ed3ca60b048b4bf67cde2195961e0bba6f70bcbea9a2c4e133e34b46",
                            "indexNumber": "0"
                        }

Example
--------
Example JSON body::
    
    {
        "version": 2,
        "blockchain": "ETH",
        "payload": {
            "method": "getTransactionFromBlock",
            "parameter":
            {
                "hashString": "0xef95f2f1ed3ca60b048b4bf67cde2195961e0bba6f70bcbea9a2c4e133e34b46",
                "indexNumber": "0"
            },
            "webhook": <User Webhook API>,
            "Id": <Unique ID>
        }
    }

Response
--------
Results::

    {
        "status": 200,
        "values":  {
            "hash": "0x9fc76417374aa880d4449a1f7f31ec597f00b1f6f3dd2d66f4c9c6c445836d8b",
            "nonce": 2,
            "blockHash": "0xef95f2f1ed3ca60b048b4bf67cde2195961e0bba6f70bcbea9a2c4e133e34b46",
            "blockNumber": 3,
            "transactionIndex": 0,
            "from": "0xa94f5374fce5edbc8e2a8697c15331677e6ebf0b",
            "to": "0x6295ee1b4f6dd65047762f924ecd367c17eabf8f",
            "value": '123450000000000000',
            "gas": 314159,
            "gasPrice": '2000000000000',
            "input": "0x57cb2fc4"
        }
    }

------------------------------------------------------------------------------

getTransactionReceipt
=====================

The receipt of a transaction by transaction hash.

Headers
--------
Need to set headers::

    Key             Value

    Content-Type    application/json

    Authorization   OBC eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYW1lIjoib2JjIiwiaWF0IjoxNjAzMTU3NjMzLCJleHAiOjE2MDM3NjI0MzN9.71my1T-2IxQNJhNNu-aRX7N3TLo9BqAczyGWX1ph2vA

Parameters
--------
Need parameters::

    Transaction         Transaction ID after initiated transaction
    hash                {
                            "hash": "0xc919e0b9dec70ae9fac16af491928806210581a82eca8e25e490ebacee324b68"
                        }

Example
--------
Example JSON body::
    
    {
        "version": 2,
        "blockchain": "ETH",
        "payload": {
            "method": "getTransactionReceipt",
            "parameter":
            {
                "hash": "0xc919e0b9dec70ae9fac16af491928806210581a82eca8e25e490ebacee324b68"
            },
            "webhook": <User Webhook API>,
            "Id": <Unique ID>
        }
    }

Response
--------
Results::

    {
        "status": 200,
        "values": {
            "blockHash": "0xa5a25e2dc550ec4fe59ffd906fd8e9619a23f07220664993579188e8f9f33dc5",
            "blockNumber": 1381308,
            "contractAddress": null,
            "cumulativeGasUsed": 27261,
            "from": "0xce9bfd1c0c1ba565f9f380342ab1114ad6c40f63",
            "gasUsed": 27261,
            "logs": [],
            "logsBloom": "0x00000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000",
            "status": false,
            "to": "0xff3821a29c484c42dfa245b842c05154e4baab8a",
            "transactionHash": "0x703d53f6b10ec97ac1670f6283ccdb7dc64496a5061c317444ea33573a9e71fb",
            "transactionIndex": 0
        }
        
    }

------------------------------------------------------------------------------

sendSignedTransaction
=====================

Sends an already signed transaction.

Headers
--------
Need to set headers::

    Key             Value

    Content-Type    application/json

    Authorization   OBC eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYW1lIjoib2JjIiwiaWF0IjoxNjAzMTU3NjMzLCJleHAiOjE2MDM3NjI0MzN9.71my1T-2IxQNJhNNu-aRX7N3TLo9BqAczyGWX1ph2vA

Parameters
--------
Need parameters::

    Serialize hash      Signed transaction data in HEX format
                        {
                            "serializedTx": "0xf86c04853e660b780082520894b43f7f7af34c4b214456bd98d468d533865fbb458806f05b59d3b20000801ca00de040fe31ea5a8a275fc704e7fc8f7cdbaa6a44a770027c421773bfa7fd6099a07b0452c6a223b50fe8c4a1280f7782470b1ea277eda4ab18ac2ce20e9f08f342"
                        }

Example
--------
Example JSON body::
    
    {
        "version": 2,
        "blockchain": "ETH",
        "payload": {
            "method": "sendSignedTransaction",
            "parameter":
            {
                "serializedTx": "0xf86c04853e660b780082520894b43f7f7af34c4b214456bd98d468d533865fbb458806f05b59d3b20000801ca00de040fe31ea5a8a275fc704e7fc8f7cdbaa6a44a770027c421773bfa7fd6099a07b0452c6a223b50fe8c4a1280f7782470b1ea277eda4ab18ac2ce20e9f08f342"
            },
            "webhook": <User Webhook API>,
            "Id": <Unique ID>
        }
    }

Response
--------
Results::

    {
        "status": 200,
        "values":"0xc1520ebfe0a225e6971e81953221c60ac1bfcd528e2cc17080b3f9b357003e34"
    }

------------------------------------------------------------------------------

getBalance
==========

Get the balance of an address at a given block.

Headers
--------
Need to set headers::

    Key             Value

    Content-Type    application/json

    Authorization   OBC eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYW1lIjoib2JjIiwiaWF0IjoxNjAzMTU3NjMzLCJleHAiOjE2MDM3NjI0MzN9.71my1T-2IxQNJhNNu-aRX7N3TLo9BqAczyGWX1ph2vA

Parameters
--------
Need parameters::

    address         The address to get the balance of
                    {
                        "address": "0xceb21b8ce14e287a106bd01f5c92dac970c1efd3"
                    }

Example
--------
Example JSON body::

    {
        "version": 2,
        "blockchain": "ETH",
        "payload": {
            "method": "getBalance",
            "parameter":
            {
                "address": "0xceb21b8ce14e287a106bd01f5c92dac970c1efd3"
            },
            "webhook": <User Webhook API>,
            "Id": <Unique ID>
        }
    }

Response
--------
Results::

    {
        "status": 200,
        "values": "0"
    }

------------------------------------------------------------------------------

getBlock
========

The block matching the block number or block hash.

Headers
--------
Need to set headers::

    Key             Value

    Content-Type    application/json

    Authorization   OBC eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYW1lIjoib2JjIiwiaWF0IjoxNjAzMTU3NjMzLCJleHAiOjE2MDM3NjI0MzN9.71my1T-2IxQNJhNNu-aRX7N3TLo9BqAczyGWX1ph2vA

Parameters
--------
Need parameters::

    BlockNumber     The block number or block hash
                    {
                        "blockNumber":"latest" 
                    }

Example
--------
Example JSON body::

    {
        "version": 2,
        "blockchain": "ETH",
        "payload": {
            "method": "getBlock",
            "parameter":
            {
                "blockNumber":"latest" 
            },
            "webhook": <User Webhook API>,
            "Id": <Unique ID>
        }
    }

Response
--------
Results::

    {
        "status": 200,
        "values": {
            "difficulty": "3283105782578062",
            "extraData": "0x6574682d70726f2d687a6f2d74303035",
            "gasLimit": 12474811,
            "gasUsed": 12458310,
            "hash": "0x304ae091240c163d6bba3c185a231561e652b288323fe025c423a4b689355e03",
            "logsBloom": "0x4460218c55406620444026c1904510208071a2a4d41ac610580917820088034500d4010310c04b82f125eaa8522201d8927b441e0b48000b2c4dcf8435282c005b8860c09b405930cc043a2a540119b090c229165363349423e28321820470101c603f8456688400d060e7d400645a93a22920022c082e262028033c60ae854228ca95212acd2cd086c909c40a98081201b49b57b5a0902b0159c043e4196f880afe45ad1e646e448ce0088048149c4902030690e48202896c5b10ae02c04228b7298c9a080a18480a9fc5005042814d30413603530f819fc52a5112c180a208523260c321183044000b24c4112162278530aac4463c935ad030fb838aa09224",
            "miner": "0x5A0b54D5dc17e0AadC383d2db43B0a0D3E029c4c",
            "mixHash": "0xb1033124f5b12a340850ff39994c02fc7d9f35155610db382ea7983e8dc77423",
            "nonce": "0xf6085d174470b114",
            "number": 11106835,
            "parentHash": "0xfd5141b7f3468de3ffa050d4521de95f79a79dbf988e47fc4800a29a1165590e",
            "receiptsRoot": "0xa8f0069588af87ae5b42e121b5baa91cf2df4d60791309e83f9db277bfd2da7b",
            "sha3Uncles": "0x1dcc4de8dec75d7aab85b567b6ccd41ad312451b948a7413f0a142fd40d49347",
            "size": 25928,
            "stateRoot": "0x2867691f276a6bf750d6eb336170b28efb9f412c85fbcf08e342623f0ebecda7",
            "timestamp": 1603380975,
            "totalDifficulty": "18201459894245119072846",
            "transactions": [
                "0x4e9f3ec2efc14d4641cbde5dd60a8df18a9cf27c6ce96bd446a907f5dbff8038",
                "0x501822209a669595531ae18044b95fdcd9809aaff87e163a53f726978cf3052b",
                "0x9ba57c78effeed2246148bba42394f6206df2bfba3d151c7ba1fa3b4226f1efa"
            ],
            "transactionsRoot": "0xf07a0da121dc485459eb59b3818bcb607ca2c909ea12062d767090687645d3dd",
            "uncles": []
        }
    }

------------------------------------------------------------------------------

getBlockNumber
==============

The number of the most recent block.

Headers
--------
Need to set headers::

    Key             Value

    Content-Type    application/json

    Authorization   OBC eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYW1lIjoib2JjIiwiaWF0IjoxNjAzMTU3NjMzLCJleHAiOjE2MDM3NjI0MzN9.71my1T-2IxQNJhNNu-aRX7N3TLo9BqAczyGWX1ph2vA

Parameters
--------
No need parameters::

Example
--------
Example JSON body::

    {
        "version": 2,
        "blockchain": "ETH",
        "payload": {
            "method": "getBlockNumber",
            "parameter":{},
            "webhook": <User Webhook API>,
            "Id": <Unique ID>
        }
    }

Response
--------
Results::

    {
        "status": 200,
        "values": 11090988
    }

------------------------------------------------------------------------------

getBlockTransactionCount
========================

The number of transaction in a given block.

Headers
--------
Need to set headers::

    Key             Value

    Content-Type    application/json

    Authorization   OBC eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYW1lIjoib2JjIiwiaWF0IjoxNjAzMTU3NjMzLCJleHAiOjE2MDM3NjI0MzN9.71my1T-2IxQNJhNNu-aRX7N3TLo9BqAczyGWX1ph2vA

Parameters
--------
Need parameters::

    BlockNumber     Get the latest block
                    {
                        blockNumber":"latest"
                    }

Example
--------
Example JSON body::
    
    {
        "version": 2,
        "blockchain": "ETH",
        "payload": {
            "method": "getBlockTransactionCount",
            "parameter":
            {
                "blockNumber":"latest" 
            },
            "webhook": <User Webhook API>,
            "Id": <Unique ID>
        }
    }

Response
--------
Results::

    {
        "status": 200,
        "values": 248
    }

------------------------------------------------------------------------------

getBlockUncleCount
==================

The number of uncles in a block from a block matching the given block hash.

Headers
--------
Need to set headers::

    Key             Value

    Content-Type    application/json

    Authorization   OBC eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYW1lIjoib2JjIiwiaWF0IjoxNjAzMTU3NjMzLCJleHAiOjE2MDM3NjI0MzN9.71my1T-2IxQNJhNNu-aRX7N3TLo9BqAczyGWX1ph2vA

Parameters
--------
Need parameters::

    BlockNumber     The block number or hash
                    {
                        "blockNumber":"latest"
                    }

Example
--------
Example JSON body::
    
    {
        "version": 2,
        "blockchain": "ETH",
        "payload": {
            "method": "getBlockUncleCount",
            "parameter":
            {
                "blockNumber":"latest" 
            },
            "webhook": <User Webhook API>,
            "Id": <Unique ID>
        }
    }

Response
--------
Results::

    {
        "status": 200,
        "values": 1
    }

------------------------------------------------------------------------------

getCode
========

Get the code at a specific contract address.

Headers
--------
Need to set headers::

    Key             Value

    Content-Type    application/json

    Authorization   OBC eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYW1lIjoib2JjIiwiaWF0IjoxNjAzMTU3NjMzLCJleHAiOjE2MDM3NjI0MzN9.71my1T-2IxQNJhNNu-aRX7N3TLo9BqAczyGWX1ph2vA

Parameters
--------
Need parameters::

    Address     The address to get the code from
                {
                    "address": "0x407d73d8a49eeb85d32cf465507dd71d507100c1"
                }

Example
--------
Example JSON body::

    {
        "version": 2,
        "blockchain": "ETH",
        "payload": {
            "method": "getCode",
            "parameter":
            {
                "address": "0x407d73d8a49eeb85d32cf465507dd71d507100c1"
            },
            "webhook": <User Webhook API>,
            "Id": <Unique ID>
        }
    }

Response
--------
Results::

    {
        "status": 200,
        "values": "0x"
    }

------------------------------------------------------------------------------

getGasPrice
===========

The current gas price oracle. The gas price is determined by the last few blocks median gas price.

Headers
--------
Need to set headers::

    Key             Value

    Content-Type    application/json

    Authorization   OBC eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYW1lIjoib2JjIiwiaWF0IjoxNjAzMTU3NjMzLCJleHAiOjE2MDM3NjI0MzN9.71my1T-2IxQNJhNNu-aRX7N3TLo9BqAczyGWX1ph2vA

Parameters
--------
No need parameters::

Example
--------
Example JSON body::

    {
        "version": 2,
        "blockchain": "ETH",
        "payload": {
            "method": "getGasPrice",
            "parameter":{},
            "webhook": <User Webhook API>,
            "Id": <Unique ID>
        }
    }

Response
--------
Results::

    {
        "status": 200,
        "values": "20000001459" //in wei
    }

------------------------------------------------------------------------------

getHashrate
===========

The number of hashes per second that the node is mining with.

Headers
--------
Need to set headers::

    Key             Value

    Content-Type    application/json

    Authorization   OBC eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYW1lIjoib2JjIiwiaWF0IjoxNjAzMTU3NjMzLCJleHAiOjE2MDM3NjI0MzN9.71my1T-2IxQNJhNNu-aRX7N3TLo9BqAczyGWX1ph2vA

Parameters
--------
No need parameters::

Example
--------
Example JSON body::

    {
        "version": 2,
        "blockchain": "ETH",
        "payload": {
            "method": "getHashrate",
            "parameter":{},
            "webhook": <User Webhook API>,
            "Id": <Unique ID>
        }
    }

Response
--------
Results::

    {
        "status": 200,
        "values": 0
    }

------------------------------------------------------------------------------

getPeerCount
============

The number of peers connected to.

Headers
--------
Need to set headers::

    Key             Value

    Content-Type    application/json

    Authorization   OBC eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYW1lIjoib2JjIiwiaWF0IjoxNjAzMTU3NjMzLCJleHAiOjE2MDM3NjI0MzN9.71my1T-2IxQNJhNNu-aRX7N3TLo9BqAczyGWX1ph2vA

Parameters
--------
No need parameters::

Example
--------
Example JSON body::
    
    {
        "version": 2,
        "blockchain": "ETH",
        "payload": {
            "method": "getPeerCount",
            "parameter":{},
            "webhook": <User Webhook API>,
            "Id": <Unique ID>
        }
    }

Response
--------
Results::

    {
        "status": 200,
        "values": 14
    }

------------------------------------------------------------------------------

transactionConfirmationBlocks
=============================

This rpc is used over HTTP connections. It defines the number of blocks it requires until a transaction is considered confirmed.

Headers
--------
Need to set headers::

    Key             Value

    Content-Type    application/json

    Authorization   OBC eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYW1lIjoib2JjIiwiaWF0IjoxNjAzMTU3NjMzLCJleHAiOjE2MDM3NjI0MzN9.71my1T-2IxQNJhNNu-aRX7N3TLo9BqAczyGWX1ph2vA

Parameters
--------
No need parameters::

Example
--------
Example JSON body::

    {
        "version": 2,
        "blockchain": "ETH",
        "payload": {
            "method": "transactionConfirmationBlocks",
            "parameter":{},
            "webhook": <User Webhook API>,
            "Id": <Unique ID>
        }
    }

Response
--------
Results::

    {
        "status": 200,
        "values": 50
    }

------------------------------------------------------------------------------

getAccounts
===========

This rpc is used over HTTP connections. It returns a list of accounts the node controls.

Headers
--------
Need to set headers::

    Key             Value

    Content-Type    application/json

    Authorization   OBC eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYW1lIjoib2JjIiwiaWF0IjoxNjAzMTU3NjMzLCJleHAiOjE2MDM3NjI0MzN9.71my1T-2IxQNJhNNu-aRX7N3TLo9BqAczyGWX1ph2vA

Parameters
--------
No need parameters::

Example
--------
Example JSON body::

    {
        "version": 2,
        "blockchain": "ETH",
        "payload": {
            "method": "getAccounts",
            "parameter":{},
            "webhook": <User Webhook API>,
            "Id": <Unique ID>
        }
    }

Response
--------
Results::

    {
        "status": 200,
        "values": false
    }

------------------------------------------------------------------------------

getChainId
==========

This rpc is used over HTTP connections. It return the chain ID of the current connected node as described in the EIP-695.

Headers
--------
Need to set headers::

    Key             Value

    Content-Type    application/json

    Authorization   OBC eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYW1lIjoib2JjIiwiaWF0IjoxNjAzMTU3NjMzLCJleHAiOjE2MDM3NjI0MzN9.71my1T-2IxQNJhNNu-aRX7N3TLo9BqAczyGWX1ph2vA

Parameters
--------
No need parameters::

Example
--------
Example JSON body::

    {
        "version": 2,
        "blockchain": "ETH",
        "payload": {
            "method": "getChainId",
            "parameter":{},
            "webhook": <User Webhook API>,
            "Id": <Unique ID>
        }
    }

Response
--------
Results::

    {
        "status": 200,
        "values": 1
    }

------------------------------------------------------------------------------

getId
======

The current network ID.

Headers
--------
Need to set headers::

    Key             Value

    Content-Type    application/json

    Authorization   OBC eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYW1lIjoib2JjIiwiaWF0IjoxNjAzMTU3NjMzLCJleHAiOjE2MDM3NjI0MzN9.71my1T-2IxQNJhNNu-aRX7N3TLo9BqAczyGWX1ph2vA

Parameters
--------
No need parameters::

Example
--------
Example JSON body::
    
    {
        "version": 2,
        "blockchain": "ETH",
        "payload": {
            "method": "getId",
            "parameter":{},
            "webhook": <User Webhook API>,
            "Id": <Unique ID>
        }
    }

Response
--------
Results::

    {
        "status": 200,
        "values": 1
    }

------------------------------------------------------------------------------

getNodeInfo
===========

The current client version.

Headers
--------
Need to set headers::

    Key             Value

    Content-Type    application/json

    Authorization   OBC eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYW1lIjoib2JjIiwiaWF0IjoxNjAzMTU3NjMzLCJleHAiOjE2MDM3NjI0MzN9.71my1T-2IxQNJhNNu-aRX7N3TLo9BqAczyGWX1ph2vA

Parameters
--------
No need parameters::

Example
--------
Example JSON body::
    
    {
        "version": 2,
        "blockchain": "ETH",
        "payload": {
            "method": "getNodeInfo",
            "parameter":{},
            "webhook": <User Webhook API>,
            "Id": <Unique ID>
        }
    }

Response
--------
Results::

    {
        "status": 200,
        "values": "Geth/v1.9.10-stable-58cf5686/linux-amd64/go1.13.6"
    }

------------------------------------------------------------------------------

getPastLogs
===========

Gets past logs, matching the given options.

Headers
--------
Need to set headers::

    Key             Value

    Content-Type    application/json

    Authorization   OBC eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYW1lIjoib2JjIiwiaWF0IjoxNjAzMTU3NjMzLCJleHAiOjE2MDM3NjI0MzN9.71my1T-2IxQNJhNNu-aRX7N3TLo9BqAczyGWX1ph2vA

Parameters
--------
Need parameters::

    Address         An address or a list of addresses to only get logs from particular account(s) and an array of values which must each appear in the log entries
    topic           {
                        "address": "0x11f4d0A3c12e86B4b5F39B213F7E19D048276DAe",
                        "topics": [
                            "0x033456732123ffff2342342dd12342434324234234fd234fd23fd4f23d4234"
                        ]
                    }

Example
--------
Example JSON body::
    
    {
        "version": 2,
        "blockchain": "ETH",
        "payload": {
            "method": "getNodeInfo",
            "parameter":
            {
                "address": "0x11f4d0A3c12e86B4b5F39B213F7E19D048276DAe",
                "topics": [
                    "0x033456732123ffff2342342dd12342434324234234fd234fd23fd4f23d4234"
                ]
            ,
            "webhook": <User Webhook API>,
            "Id": <Unique ID>
        }
    }

Response
--------
Results::

    {
        "status": 200,
        "values": [
            {
                "address": "0xC02aaA39b223FE8D0A0e5C4F27eAD9083C756Cc2",
                "topics": [
                    "0xddf252ad1be2c89b69c2b068fc378daa952ba7f163c4a11628f55a4df523b3ef",
                    "0x000000000000000000000000d3661f906ea1cdc3a3689ed9ecf10544aada79f0",
                    "0x00000000000000000000000091a5db96b660811fe38761b4bd7887efd16820cb"
                ],
                "data": "0x00000000000000000000000000000000000000000000000018ee7d3c7614f000",
                "blockNumber": 11273048,
                "transactionHash": "0xcdda2314f89eb5e0c33cf9459b3257ea0bc91a48e4b7d70444d8db9d5554387b",
                "transactionIndex": 0,
                "blockHash": "0xd1cc61264f1c46621713f0afccc3225c2d8cf35f873f02d60abed1682a632121",
                "logIndex": 0,
                "removed": false,
                "id": "log_e3fe376f"
            },
            {
                "address": "0x5ac13261c181a9c3938BfE1b649E65D10F98566B",
                "topics": [
                    "0xd78ad95fa46c994b6551d0da85fc275fe613ce37657fb8d5e3d130840159d822",
                    "0x0000000000000000000000007a250d5630b4cf539739df2c5dacb4c659f2488d",
                    "0x000000000000000000000000ca372920485da699a42006b6b4abc166b226ba16"
                ],
                "data": "0x000000000000000000000000000000000000000000000002179a18af9318952b0000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000089ee67d",
                "blockNumber": 11273048,
                "transactionHash": "0x509a254b254971c443fc0006f09aed2d7ee985e85af0e34fdea96f20fa464983",
                "transactionIndex": 224,
                "blockHash": "0xd1cc61264f1c46621713f0afccc3225c2d8cf35f873f02d60abed1682a632121",
                "logIndex": 299,
                "removed": false,
                "id": "log_97aeea7d"
            }
        ]
    }

------------------------------------------------------------------------------

getProtocolVersion
==================

The ethereum protocol version of the node.

Headers
--------
Need to set headers::

    Key             Value

    Content-Type    application/json

    Authorization   OBC eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYW1lIjoib2JjIiwiaWF0IjoxNjAzMTU3NjMzLCJleHAiOjE2MDM3NjI0MzN9.71my1T-2IxQNJhNNu-aRX7N3TLo9BqAczyGWX1ph2vA

Parameters
--------
No need parameters::

Example
--------
Example JSON body::
    
    {
        "version": 2,
        "blockchain": "ETH",
        "payload": {
            "method": "getProtocolVersion",
            "parameter":{},
            "webhook": <User Webhook API>,
            "Id": <Unique ID>
        }
    }

Response
--------
Results::

    {
        "status": 200,
        "values": "0x40"
    }

------------------------------------------------------------------------------

getStorageAt
============

Get the storage at a specific position of an address.

Headers
--------
Need to set headers::

    Key             Value

    Content-Type    application/json

    Authorization   OBC eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYW1lIjoib2JjIiwiaWF0IjoxNjAzMTU3NjMzLCJleHAiOjE2MDM3NjI0MzN9.71my1T-2IxQNJhNNu-aRX7N3TLo9BqAczyGWX1ph2vA

Parameters
--------
Need parameters::

    Address         The address to get storage and the index position of the storage
    position        {
                        "address": "0x407d73d8a49eeb85d32cf465507dd71d507100c1",
                        "position": 0
                    } 

Example
--------
Example JSON body::

    {
        "version": 2,
        "blockchain": "ETH",
        "payload": {
            "method": "getStorageAt",
            "parameter":
            {
                "address": "0x407d73d8a49eeb85d32cf465507dd71d507100c1",
                "position": 0
            },
            "webhook": <User Webhook API>,
            "Id": <Unique ID>
        }
    }

Response
--------
Results::

    {
        "status": 200,
        "values": "0x0000000000000000000000000000000000000000000000000000000000000000"
    }

------------------------------------------------------------------------------

isListening
===========

Checks if the node is listening for peers.

Headers
--------
Need to set headers::

    Key             Value

    Content-Type    application/json

    Authorization   OBC eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYW1lIjoib2JjIiwiaWF0IjoxNjAzMTU3NjMzLCJleHAiOjE2MDM3NjI0MzN9.71my1T-2IxQNJhNNu-aRX7N3TLo9BqAczyGWX1ph2vA

Parameters
--------
No need parameters::

Example
--------
Example JSON body::
    
    {
        "version": 2,
        "blockchain": "ETH",
        "payload": {
            "method": "isListening",
            "parameter":{},
            "webhook": <User Webhook API>,
            "Id": <Unique ID>
        }
    }

Response
--------
Results::

    {
        "status": 200,
        "values": true
    }

------------------------------------------------------------------------------

isSyncing
=========

Checks if the node is currently syncing and returns either a syncing object.

Headers
--------
Need to set headers::

    Key             Value

    Content-Type    application/json

    Authorization   OBC eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYW1lIjoib2JjIiwiaWF0IjoxNjAzMTU3NjMzLCJleHAiOjE2MDM3NjI0MzN9.71my1T-2IxQNJhNNu-aRX7N3TLo9BqAczyGWX1ph2vA

Parameters
--------
No need parameters::

Example
--------
Example JSON body::
    
    {
        "version": 2,
        "blockchain": "ETH",
        "payload": {
            "method": "isSyncing",
            "parameter":{},
            "webhook": <User Webhook API>,
            "Id": <Unique ID>
        }
    }

Response
--------
Results::

    {
        "status": 200,
        "values": false
    }

------------------------------------------------------------------------------

deploySCHex
============

Deploy smart contract using hex string.

Headers
--------
Need to set headers::

    Key             Value

    Content-Type    application/json

    Authorization   OBC eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYW1lIjoib2JjIiwiaWF0IjoxNjAzMTU3NjMzLCJleHAiOjE2MDM3NjI0MzN9.71my1T-2IxQNJhNNu-aRX7N3TLo9BqAczyGWX1ph2vA

Parameters
--------
Need parameters::

    Serialize hex to deploy         Serialize data for specific account        
    smart contract        
                                    {
                                    "txHashOnly": "false", //boolean, true or false
                                    "serializedTx": "f9012a8214c90386082f79cd900094ff3821a29c484c42dfa245b842c05154e4baab8a80b8c40fb375090000000000000000000000000000000000000000000000000000000000000040000000000000000000000000000000000000000000000000000000000000008000000000000000000000000000000000000000000000000000000000000000084a6f686e20446f6500000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000010000000000000000000000000449859a071f6b654fde713074728c4fc22f04fe1ba0ba3f2233b7ba38c319435755caa19e31a7bae007c898569bb0950aec35eabe32a0617931ea02dcb97ad421c4dbd8eafc7d96447be5d75c17d7019b205fe015ff75"
                                    }

Example
--------
Example JSON body::

    {
        "version": 2,
        "blockchain": "ETH",
        "payload": {
            "method": "deploySCHex",
            "parameter":
            {
                "txHashOnly": "false", //boolean, true or false
                "serializedTx": "f9012a8214c90386082f79cd900094ff3821a29c484c42dfa245b842c05154e4baab8a80b8c40fb375090000000000000000000000000000000000000000000000000000000000000040000000000000000000000000000000000000000000000000000000000000008000000000000000000000000000000000000000000000000000000000000000084a6f686e20446f6500000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000010000000000000000000000000449859a071f6b654fde713074728c4fc22f04fe1ba0ba3f2233b7ba38c319435755caa19e31a7bae007c898569bb0950aec35eabe32a0617931ea02dcb97ad421c4dbd8eafc7d96447be5d75c17d7019b205fe015ff75"
            },
            "webhook": <User Webhook API>,
            "Id": <Unique ID>
        }
    }

Response
--------
Results::

    if false, // Tx receipt
    {
        "status": 200,
        "values": {
        "blockHash": "0x7592f548a5af5799d7ef6e94e7ad75709bbe6c93de3c007f4fe8b264ecea37cf",
        "blockNumber": 1882387,
        "contractAddress": "0x9E9A86391CbcA2f47c87b371F0fA65ee10e18103",
        "cumulativeGasUsed": 1972238,
        "from": "0xce9bfd1c0c1ba565f9f380342ab1114ad6c40f63",
        "gasUsed": 1972238,
        "logs": [],
        "logsBloom": "0x00000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000",
        "status": true,
        "to": null,
        "transactionHash": "0x7c684eaada704933fc3cd0675e133c66bfa2975960af1b811fe1ed446f2071bc",
        "transactionIndex": 0
        }
    }

    if true, // Tx Hash
    {
        "status":200,
        "value": "0x9fc76417374aa880d4449a1f7f31ec597f00b1f6f3dd2d66f4c9c6c445836d8b§234"
    }

------------------------------------------------------------------------------

callSC
=======

Call smart contract function.

Headers
--------
Need to set headers::

    Key             Value

    Content-Type    application/json

    Authorization   OBC eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYW1lIjoib2JjIiwiaWF0IjoxNjAzMTU3NjMzLCJleHAiOjE2MDM3NjI0MzN9.71my1T-2IxQNJhNNu-aRX7N3TLo9BqAczyGWX1ph2vA

Parameters
--------
Need parameters::

    JSON object         Body to call function in smart contract
                        {
                            "contractAddress": "0x3A758280ee8Dc0Ecb5A5C811AF9A001983DC4079",
                            "method": "getVoteDetails",
                            "param": [],
                            "abi": [...]
                        }

Example
--------
Example JSON body::

    {
        "version": 2,
        "blockchain": "ETH",
        "payload": {
            "method": "callSC",
            "parameter":
            {
                "contractAddress": "0x3A758280ee8Dc0Ecb5A5C811AF9A001983DC4079",
                "method": "getVoteDetails",
                "param": [],
                "abi": [...]
            },
            "webhook": <User Webhook API>,
            "Id": <Unique ID>
        }
    }

Response
--------
Results::

    {
        "status": 200,
        "values": {
            "0": "test",
            "1": "test 1",
            "2": "1601520317",
            "3": "1701520317",
            "4": "1606183002",
            "5": [
                "hmmm"
            ],
            "6": [
                "hm22"
            ],
            "7": [
                "0x0449859A071F6b654FDe713074728C4FC22F04Fe"
            ],
            "voteName_": "test",
            "voteDesc_": "test 1",
            "startDate_": "1601520317",
            "endDate_": "1701520317",
            "time_": "1606183002",
            "optionName_": [
                "hmmm"
            ],
            "optionDesc_": [
                "hm22"
            ],
            "optionAddress_": [
                "0x0449859A071F6b654FDe713074728C4FC22F04Fe"
            ]
        }
    }

------------------------------------------------------------------------------

encodeABISC
===========

Encodes the ABI for deploying smart contract. This can be used to encode smart contract bytecode, ABI and arguments for deploying new smart contract.

Headers
--------
Need to set headers::

    Key             Value

    Content-Type    application/json

    Authorization   OBC eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYW1lIjoib2JjIiwiaWF0IjoxNjAzMTU3NjMzLCJleHAiOjE2MDM3NjI0MzN9.71my1T-2IxQNJhNNu-aRX7N3TLo9BqAczyGWX1ph2vA

Parameters
--------
Need parameters::

    JSON object         Body to encodeABI for deploying smart contract
                        {
                            "argument": ["test", "test 1", "1601520317", "1701520317", ["hmmm"], ["hm22"],["0x0449859A071F6b654FDe713074728C4FC22F04Fe"]],
                            "abi" : [...],
                            "bytecode" : "..."
                        }

Example
--------
Example JSON body::

    {
        "version": 2,
        "blockchain": "ETH",
        "payload": {
            "method": "encodeABISC",
            "parameter":
            {
                "argument": ["test", "test 1", "1601520317", "1701520317", ["hmmm"], ["hm22"],["0x0449859A071F6b654FDe713074728C4FC22F04Fe"]],
                "abi" : [...],
                "bytecode" : "..."
            },
            "webhook": <User Webhook API>,
            "Id": <Unique ID>
        }
    }

Response
--------
Results::

    {
        "status": 200,
        "values": "0x60806040523480156200001157600080fd5b5060405162001e5438038062001e54833981810160405281019062000037919062000675565b866000800190805190602001906200005192919062000432565b5085600060010190805190602001906200006d92919062000432565b50846000600201819055508360006003018190555033600960006101000a81548173ffffffffffffffffffffffffffffffffffffffff021916908373ffffffffffffffffffffffffffffffffffffffff16021790555060008090505b815181101562000424576060825167ffffffffffffffff81118015620000ee57600080fd5b506040519080825280602002602001820160405280156200011e5781602001602082028036833780820191505090505b5090506040518060a00160405280600f5481526020018484815181106200014157fe5b602002602001015173ffffffffffffffffffffffffffffffffffffffff1681526020018684815181106200017157fe5b602002602001015181526020018584815181106200018b57fe5b60200260200101518152602001600081525060116000858581518110620001ae57fe5b602002602001015173ffffffffffffffffffffffffffffffffffffffff1673ffffffffffffffffffffffffffffffffffffffff1681526020019081526020016000206000820151816000015560208201518160010160006101000a81548173ffffffffffffffffffffffffffffffffffffffff021916908373ffffffffffffffffffffffffffffffffffffffff16021790555060408201518160020190805190602001906200025f92919062000432565b5060608201518160030190805190602001906200027e92919062000432565b50608082015181600401559050508282815181106200029957fe5b6020026020010151818381518110620002ae57fe5b602002602001019073ffffffffffffffffffffffffffffffffffffffff16908173ffffffffffffffffffffffffffffffffffffffff1681525050600b838381518110620002f757fe5b60200260200101519080600181540180825580915050600190039060005260206000200160009091909190916101000a81548173ffffffffffffffffffffffffffffffffffffffff021916908373ffffffffffffffffffffffffffffffffffffffff160217905550600c8583815181106200036e57fe5b6020026020010151908060018154018082558091505060019003906000526020600020016000909190919091509080519060200190620003b092919062000432565b50600d848381518110620003c057fe5b60200260200101519080600181540180825580915050600190039060005260206000200160009091909190915090805190602001906200040292919062000432565b50600f60008154809291906001019190505550508080600101915050620000c9565b5050505050505050620008f4565b828054600181600116156101000203166002900490600052602060002090601f016020900481019282601f106200047557805160ff1916838001178555620004a6565b82800160010185558215620004a6579182015b82811115620004a557825182559160200191906001019062000488565b5b509050620004b59190620004b9565b5090565b620004de91905b80821115620004da576000816000905550600101620004c0565b5090565b90565b600081519050620004f281620008c0565b92915050565b600082601f8301126200050a57600080fd5b8151620005216200051b82620007cd565b6200079f565b915081818352602084019350602081019050838560208402820111156200054757600080fd5b60005b838110156200057b5781620005608882620004e1565b8452602084019350602083019250506001810190506200054a565b5050505092915050565b600082601f8301126200059757600080fd5b8151620005ae620005a882620007f6565b6200079f565b9150818183526020840193506020810190508360005b83811015620005f85781518601620005dd888262000602565b845260208401935060208301925050600181019050620005c4565b5050505092915050565b600082601f8301126200061457600080fd5b81516200062b62000625826200081f565b6200079f565b915080825260208301602083018583830111156200064857600080fd5b620006558382846200088a565b50505092915050565b6000815190506200066f81620008da565b92915050565b600080600080600080600060e0888a0312156200069157600080fd5b600088015167ffffffffffffffff811115620006ac57600080fd5b620006ba8a828b0162000602565b975050602088015167ffffffffffffffff811115620006d857600080fd5b620006e68a828b0162000602565b9650506040620006f98a828b016200065e565b95505060606200070c8a828b016200065e565b945050608088015167ffffffffffffffff8111156200072a57600080fd5b620007388a828b0162000585565b93505060a088015167ffffffffffffffff8111156200075657600080fd5b620007648a828b0162000585565b92505060c088015167ffffffffffffffff8111156200078257600080fd5b620007908a828b01620004f8565b91505092959891949750929550565b6000604051905081810181811067ffffffffffffffff82111715620007c357600080fd5b8060405250919050565b600067ffffffffffffffff821115620007e557600080fd5b602082029050602081019050919050565b600067ffffffffffffffff8211156200080e57600080fd5b602082029050602081019050919050565b600067ffffffffffffffff8211156200083757600080fd5b601f19601f8301169050602081019050919050565b6000620008598262000860565b9050919050565b600073ffffffffffffffffffffffffffffffffffffffff82169050919050565b6000819050919050565b60005b83811015620008aa5780820151818401526020810190506200088d565b83811115620008ba576000848401525b50505050565b620008cb816200084c565b8114620008d757600080fd5b50565b620008e58162000880565b8114620008f157600080fd5b50565b61155080620009046000396000f3fe608060405234801561001057600080fd5b50600436106100cf5760003560e01c80636fb26c4a1161008c578063aaebeffc11610066578063aaebeffc14610243578063aef2c9fe14610273578063b28d92ae146102a3578063f10ba0fe146102c1576100cf565b80636fb26c4a146101d75780638da5cb5b146101f5578063a2a8d2ae14610213576100cf565b80630fb37509146100d4578063134c39cc14610104578063281995051461012957806330006281146101475780633a88251a146101775780636d7f9724146101a7575b600080fd5b6100ee60048036038101906100e99190610ea6565b6102df565b6040516100fb91906111ed565b60405180910390f35b61010c6104bd565b60405161012098979695949392919061122a565b60405180910390f35b610131610886565b60405161013e919061130b565b60405180910390f35b610161600480360381019061015c9190610f12565b61088c565b60405161016e9190611208565b60405180910390f35b610191600480360381019061018c9190610f12565b610945565b60405161019e91906111b0565b60405180910390f35b6101c160048036038101906101bc9190610f12565b610981565b6040516101ce9190611208565b60405180910390f35b6101df610a3a565b6040516101ec919061130b565b60405180910390f35b6101fd610a40565b60405161020a91906111b0565b60405180910390f35b61022d60048036038101906102289190610e65565b610a66565b60405161023a91906111ed565b60405180910390f35b61025d60048036038101906102589190610f12565b610a9e565b60405161026a9190611208565b60405180910390f35b61028d60048036038101906102889190610e3c565b610b57565b60405161029a919061130b565b60405180910390f35b6102ab610ba3565b6040516102b891906111cb565b60405180910390f35b6102c9610c8c565b6040516102d6919061130b565b60405180910390f35b60008060020154421180156102f8575060006003015442105b80156103365750600015156012846040516103139190611199565b908152602001604051809103902060000160009054906101000a900460ff161515145b610375576040517f08c379a000000000000000000000000000000000000000000000000000000000815260040161036c906112cb565b60405180910390fd5b60106000815480929190600101919050555060016012846040516103999190611199565b908152602001604051809103902060000160006101000a81548160ff021916908315150217905550600e839080600181540180825580915050600190039060005260206000200160009091909190915090805190602001906103fc929190610c96565b5060008090505b825181101561047d5760016011600085848151811061041e57fe5b602002602001015173ffffffffffffffffffffffffffffffffffffffff1673ffffffffffffffffffffffffffffffffffffffff168152602001908152602001600020600401600082825401925050819055508080600101915050610403565b507f41304facd9323d75b11bcdd609cb38effffdb05710f7caf0e9b16c6d9d709f506040516104ab906112eb565b60405180910390a16001905092915050565b6060806000806000606080606060008001600060010160006002015460006003015442600c600d600b878054600181600116156101000203166002900480601f01602080910402602001604051908101604052809291908181526020018280546001816001161561010002031660029004801561057b5780601f106105505761010080835404028352916020019161057b565b820191906000526020600020905b81548152906001019060200180831161055e57829003601f168201915b50505050509750868054600181600116156101000203166002900480601f0160208091040260200160405190810160405280929190818152602001828054600181600116156101000203166002900480156106175780601f106105ec57610100808354040283529160200191610617565b820191906000526020600020905b8154815290600101906020018083116105fa57829003601f168201915b5050505050965082805480602002602001604051908101604052809291908181526020016000905b828210156106fb578382906000526020600020018054600181600116156101000203166002900480601f0160208091040260200160405190810160405280929190818152602001828054600181600116156101000203166002900480156106e75780601f106106bc576101008083540402835291602001916106e7565b820191906000526020600020905b8154815290600101906020018083116106ca57829003601f168201915b50505050508152602001906001019061063f565b50505050925081805480602002602001604051908101604052809291908181526020016000905b828210156107de578382906000526020600020018054600181600116156101000203166002900480601f0160208091040260200160405190810160405280929190818152602001828054600181600116156101000203166002900480156107ca5780601f1061079f576101008083540402835291602001916107ca565b820191906000526020600020905b8154815290600101906020018083116107ad57829003601f168201915b505050505081526020019060010190610722565b5050505091508080548060200260200160405190810160405280929190818152602001828054801561086557602002820191906000526020600020905b8160009054906101000a900473ffffffffffffffffffffffffffffffffffffffff1673ffffffffffffffffffffffffffffffffffffffff168152602001906001019080831161081b575b50505050509050975097509750975097509750975097509091929394959697565b600f5481565b600c818154811061089957fe5b906000526020600020016000915090508054600181600116156101000203166002900480601f01602080910402602001604051908101604052809291908181526020018280546001816001161561010002031660029004801561093d5780601f106109125761010080835404028352916020019161093d565b820191906000526020600020905b81548152906001019060200180831161092057829003601f168201915b505050505081565b600b818154811061095257fe5b906000526020600020016000915054906101000a900473ffffffffffffffffffffffffffffffffffffffff1681565b600d818154811061098e57fe5b906000526020600020016000915090508054600181600116156101000203166002900480601f016020809104026020016040519081016040528092919081815260200182805460018160011615610100020316600290048015610a325780601f10610a0757610100808354040283529160200191610a32565b820191906000526020600020905b815481529060010190602001808311610a1557829003601f168201915b505050505081565b60105481565b600960009054906101000a900473ffffffffffffffffffffffffffffffffffffffff1681565b6000601282604051610a789190611199565b908152602001604051809103902060000160009054906101000a900460ff169050919050565b600e8181548110610aab57fe5b906000526020600020016000915090508054600181600116156101000203166002900480601f016020809104026020016040519081016040528092919081815260200182805460018160011615610100020316600290048015610b4f5780601f10610b2457610100808354040283529160200191610b4f565b820191906000526020600020905b815481529060010190602001808311610b3257829003601f168201915b505050505081565b6000601160008373ffffffffffffffffffffffffffffffffffffffff1673ffffffffffffffffffffffffffffffffffffffff168152602001908152602001600020600401549050919050565b6060600e805480602002602001604051908101604052809291908181526020016000905b82821015610c83578382906000526020600020018054600181600116156101000203166002900480601f016020809104026020016040519081016040528092919081815260200182805460018160011615610100020316600290048015610c6f5780601f10610c4457610100808354040283529160200191610c6f565b820191906000526020600020905b815481529060010190602001808311610c5257829003601f168201915b505050505081526020019060010190610bc7565b50505050905090565b6000601054905090565b828054600181600116156101000203166002900490600052602060002090601f016020900481019282601f10610cd757805160ff1916838001178555610d05565b82800160010185558215610d05579182015b82811115610d04578251825591602001919060010190610ce9565b5b509050610d129190610d16565b5090565b610d3891905b80821115610d34576000816000905550600101610d1c565b5090565b90565b600081359050610d4a816114ec565b92915050565b600082601f830112610d6157600080fd5b8135610d74610d6f82611353565b611326565b91508181835260208401935060208101905083856020840282011115610d9957600080fd5b60005b83811015610dc95781610daf8882610d3b565b845260208401935060208301925050600181019050610d9c565b5050505092915050565b600082601f830112610de457600080fd5b8135610df7610df28261137b565b611326565b91508082526020830160208301858383011115610e1357600080fd5b610e1e838284611499565b50505092915050565b600081359050610e3681611503565b92915050565b600060208284031215610e4e57600080fd5b6000610e5c84828501610d3b565b91505092915050565b600060208284031215610e7757600080fd5b600082013567ffffffffffffffff811115610e9157600080fd5b610e9d84828501610dd3565b91505092915050565b60008060408385031215610eb957600080fd5b600083013567ffffffffffffffff811115610ed357600080fd5b610edf85828601610dd3565b925050602083013567ffffffffffffffff811115610efc57600080fd5b610f0885828601610d50565b9150509250929050565b600060208284031215610f2457600080fd5b6000610f3284828501610e27565b91505092915050565b6000610f478383610f67565b60208301905092915050565b6000610f5f8383611067565b905092915050565b610f7081611451565b82525050565b610f7f81611451565b82525050565b6000610f90826113c7565b610f9a8185611402565b9350610fa5836113a7565b8060005b83811015610fd6578151610fbd8882610f3b565b9750610fc8836113e8565b925050600181019050610fa9565b5085935050505092915050565b6000610fee826113d2565b610ff88185611413565b93508360208202850161100a856113b7565b8060005b8581101561104657848403895281516110278582610f53565b9450611032836113f5565b925060208a0199505060018101905061100e565b50829750879550505050505092915050565b61106181611463565b82525050565b6000611072826113dd565b61107c8185611424565b935061108c8185602086016114a8565b611095816114db565b840191505092915050565b60006110ab826113dd565b6110b58185611435565b93506110c58185602086016114a8565b6110ce816114db565b840191505092915050565b60006110e4826113dd565b6110ee8185611446565b93506110fe8185602086016114a8565b80840191505092915050565b6000611117601383611435565b91507f496e76616c6964206461746520696e70757421000000000000000000000000006000830152602082019050919050565b6000611157600a83611435565b91507f446f6e6520766f746521000000000000000000000000000000000000000000006000830152602082019050919050565b6111938161148f565b82525050565b60006111a582846110d9565b915081905092915050565b60006020820190506111c56000830184610f76565b92915050565b600060208201905081810360008301526111e58184610fe3565b905092915050565b60006020820190506112026000830184611058565b92915050565b6000602082019050818103600083015261122281846110a0565b905092915050565b6000610100820190508181036000830152611245818b6110a0565b90508181036020830152611259818a6110a0565b9050611268604083018961118a565b611275606083018861118a565b611282608083018761118a565b81810360a08301526112948186610fe3565b905081810360c08301526112a88185610fe3565b905081810360e08301526112bc8184610f85565b90509998505050505050505050565b600060208201905081810360008301526112e48161110a565b9050919050565b600060208201905081810360008301526113048161114a565b9050919050565b6000602082019050611320600083018461118a565b92915050565b6000604051905081810181811067ffffffffffffffff8211171561134957600080fd5b8060405250919050565b600067ffffffffffffffff82111561136a57600080fd5b602082029050602081019050919050565b600067ffffffffffffffff82111561139257600080fd5b601f19601f8301169050602081019050919050565b6000819050602082019050919050565b6000819050602082019050919050565b600081519050919050565b600081519050919050565b600081519050919050565b6000602082019050919050565b6000602082019050919050565b600082825260208201905092915050565b600082825260208201905092915050565b600082825260208201905092915050565b600082825260208201905092915050565b600081905092915050565b600061145c8261146f565b9050919050565b60008115159050919050565b600073ffffffffffffffffffffffffffffffffffffffff82169050919050565b6000819050919050565b82818337600083830152505050565b60005b838110156114c65780820151818401526020810190506114ab565b838111156114d5576000848401525b50505050565b6000601f19601f8301169050919050565b6114f581611451565b811461150057600080fd5b50565b61150c8161148f565b811461151757600080fd5b5056fea2646970667358221220d59954f17c474cfe8b5d302880e1ce60305e6e39db549508116a1d8f28a6dd3064736f6c6343000606003300000000000000000000000000000000000000000000000000000000000000e00000000000000000000000000000000000000000000000000000000000000120000000000000000000000000000000000000000000000000000000005f7542bd00000000000000000000000000000000000000000000000000000000656b23bd000000000000000000000000000000000000000000000000000000000000016000000000000000000000000000000000000000000000000000000000000001e000000000000000000000000000000000000000000000000000000000000002600000000000000000000000000000000000000000000000000000000000000004746573740000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000067465737420310000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000100000000000000000000000000000000000000000000000000000000000000200000000000000000000000000000000000000000000000000000000000000004686d6d6d00000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000100000000000000000000000000000000000000000000000000000000000000200000000000000000000000000000000000000000000000000000000000000004686d32320000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000010000000000000000000000000449859a071f6b654fde713074728c4fc22f04fe"
    }

------------------------------------------------------------------------------

encodeABIFunctionSC
===================

Encodes the ABI for smart contract method/functions. This can be used to send a transaction of a method inside a smart contract and accept method's arguments if any.

Headers
--------
Need to set headers::

    Key             Value

    Content-Type    application/json

    Authorization   OBC eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYW1lIjoib2JjIiwiaWF0IjoxNjAzMTU3NjMzLCJleHAiOjE2MDM3NjI0MzN9.71my1T-2IxQNJhNNu-aRX7N3TLo9BqAczyGWX1ph2vA

Parameters
--------
Need parameters::

    JSON Object         Body to encodeABI for specific function in smart contract.           
                        {
                            "contractAddress": "0xFF3821A29c484c42DFa245b842C05154E4baAB8a",
                            "method": "castVote",
                            "param": ["Ahmad 222 ",["0x0449859A071F6b654FDe713074728C4FC22F04Fe"]],
                            "abi": [...]
                        }

Example
--------
Example JSON body::

    {
        "version": 2,
        "blockchain": "ETH",
        "payload": {
            "method": "encodeABIFunctionSC",
            "parameter":
            {
                "contractAddress": "0xFF3821A29c484c42DFa245b842C05154E4baAB8a",
                "method": "castVote",
                "param": ["Ahmad 222 ",["0x0449859A071F6b654FDe713074728C4FC22F04Fe"]],
                "abi": [...]
            },
            "webhook": <User Webhook API>,
            "Id": <Unique ID>
        }
    }

Response
--------
Results::

    {
        "status": 200,
        "values": "0x0fb3750900000000000000000000000000000000000000000000000000000000000000400000000000000000000000000000000000000000000000000000000000000080000000000000000000000000000000000000000000000000000000000000000a41686d616420323232200000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000010000000000000000000000000449859a071f6b654fde713074728c4fc22f04fe"
    }

---------------------------------------------------------------------------------------------------------------------------

toHex
=====

Will auto convert any given value to HEX. Number strings will interpreted as numbers. Text strings will be interpreted as UTF-8 strings.

Headers
--------
Need to set headers::

    Key             Value

    Content-Type    application/json

    Authorization   OBC eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYW1lIjoib2JjIiwiaWF0IjoxNjAzMTU3NjMzLCJleHAiOjE2MDM3NjI0MzN9.71my1T-2IxQNJhNNu-aRX7N3TLo9BqAczyGWX1ph2vA

Parameters
--------
Need parameters::

    Mixed       String need to be convert
                {
                    "mixed":"asdfaskhfuunds"
                }

Example
--------
Example JSON body::

    {
        "version": 2,
        "blockchain": "ETH",
        "payload": {
            "method": "toHex",
            "parameter":
            {
                "mixed":"asdfaskhfuunds"
            },
            "webhook": <User Webhook API>,
            "Id": <Unique ID>
        }
    }

Response
--------
Results::

    {
        "status": 200,
        "values": "0x6173646661736b686675756e6473"
    }

---------------------------------------------------------------------------------------------------------------------------

asciiToHex
==========

Returns the HEX representation of a given ASCII string.

Headers
--------
Need to set headers::

    Key             Value

    Content-Type    application/json

    Authorization   OBC eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYW1lIjoib2JjIiwiaWF0IjoxNjAzMTU3NjMzLCJleHAiOjE2MDM3NjI0MzN9.71my1T-2IxQNJhNNu-aRX7N3TLo9BqAczyGWX1ph2vA

Parameters
--------
Need parameters::

    Ascii Hex       Ascii character need to be convert
                    {
                        "string": "I am clever"
                    }

Example
--------
Example JSON body::

    {
        "version": 2,
        "blockchain": "ETH",
        "payload": {
            "method": "asciiToHex",
            "parameter":
            {
                "string":"I am clever"
            },
            "webhook": <User Webhook API>,
            "Id": <Unique ID>
        }
    }

Response
--------
Results::

    {
        "status": 200,
        "values": "0x736179612062696a616b"
    }

---------------------------------------------------------------------------------------------------------------------------

isAddress
=========

Checks if a given string is a valid Ethereum address. It will also check the checksum, if the address has upper and lowercase letters.

Headers
--------
Need to set headers::

    Key             Value

    Content-Type    application/json

    Authorization   OBC eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYW1lIjoib2JjIiwiaWF0IjoxNjAzMTU3NjMzLCJleHAiOjE2MDM3NjI0MzN9.71my1T-2IxQNJhNNu-aRX7N3TLo9BqAczyGWX1ph2vA

Parameters
--------
Need parameters::

    Ethereum Address        The ethereum's address
                            {
                                "address":"0xc1912fee45d61c87cc5ea59dae31190fffff232d"
                            }

Example
--------
Example JSON body::

    {
        "version": 2,
        "blockchain": "ETH",
        "payload": {
            "method": "isAddress",
            "parameter":
            {
                "address":"0xc1912fee45d61c87cc5ea59dae31190fffff232d"
            },
            "webhook": <User Webhook API>,
            "Id": <Unique ID>
        }
    }

Response
--------
Results::

    {
        "status": 200,
        "values": true
    }

---------------------------------------------------------------------------------------------------------------------------

fromWei
=======

Converts any wei value into a ether value.

Headers
--------
Need to set headers::

    Key             Value

    Content-Type    application/json

    Authorization   OBC eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYW1lIjoib2JjIiwiaWF0IjoxNjAzMTU3NjMzLCJleHAiOjE2MDM3NjI0MzN9.71my1T-2IxQNJhNNu-aRX7N3TLo9BqAczyGWX1ph2vA

Parameters
--------
Need parameters::

    Number              Unit to be convert
    and unit            {
                            "number":"1",
                            "unit":"ether"
                        }

Example
--------
Example JSON body::

    {
        "version": 2,
        "blockchain": "ETH",
        "payload": {
            "method": "fromWei",
            "parameter":
            {
                "number":"1",
                "unit":"ether"
            },
            "webhook": <User Webhook API>,
            "Id": <Unique ID>
        }
    }

Response
--------
Results::

    {
        "status": 200,
        "values": "0.000000000000000001"
    }

---------------------------------------------------------------------------------------------------------------------------

estimateGas
============

Executes a message call or transaction and returns the amount of the gas used.

Headers
--------
Need to set headers::

    Key             Value

    Content-Type    application/json

    Authorization   OBC eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYW1lIjoib2JjIiwiaWF0IjoxNjAzMTU3NjMzLCJleHAiOjE2MDM3NjI0MzN9.71my1T-2IxQNJhNNu-aRX7N3TLo9BqAczyGWX1ph2vA

Parameters
--------
Need parameters::

    Address and data object     Body example for send smart contract
                                {
                                    "to": contract address | string ,
                                    "data": encodedABIHex | string              
                                }

                                Body example for deploying smart contract
                                {                              
                                    "from": wallet address | string , //optional
                                    "data": encodedABIHex | string                                           
                                }

                                Body example for sending ether
                                {
                                    "to": address receiver | string ,
                                    "value": wei value in hex | string                                   
                                }                                

Example
--------
Example JSON body::

    {
        "version": 2,
        "blockchain": "ETH",
        "payload": {
            "method": "estmateGas",
            "parameter":
            {
                "to": "0xceb21b8ce14e287a106bd01f5c92dac970c1efd3",
                "value": 100000000                                 
            },
            "webhook": <User Webhook API>,
            "Id": <Unique ID>
        }
    }

Response
--------
Results::

    {
        "status": 200,
        "values": 219904
    }
