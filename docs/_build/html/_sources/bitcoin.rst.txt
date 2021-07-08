========
Bitcoin
========

All RPC included are based on bitcoin-cli. 

Request URL : http://integrationhub.okwave.global/api/v2/

.. note::  Make sure to enter received token in headers using key 'Authorization'. 

------------------------------------------------------------------------------

getblockcount
=============

Returns the number of blocks in the longest blockchain.

Headers
--------
Need to set headers::

    Key             Value

    Content-Type    application/json

    Authorization   OBC eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYW1lIjoib2JjIiwiaWF0IjoxNjAzMTU3NjMzLCJleHAiOjE2MDM3NjI0MzN9.71my1T-2IxQNJhNNu-aRX7N3TLo9BqAczyGWX1ph2vA

Parameters
----------
No need parameters::

Example
--------
Example JSON body::

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

Response
--------
Returns the current block number::

    {
    "status": 200,
    "values": 653506
    }

------------------------------------------------------------------------------

getbestblockhash
================

Returns the hash of the best (tip) block in the longest blockchain.

Headers
-------
Need to set headers::

    Key             Value

    Content-Type    application/json

    Authorization   OBC eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYW1lIjoib2JjIiwiaWF0IjoxNjAzMTU3NjMzLCJleHAiOjE2MDM3NjI0MzN9.71my1T-2IxQNJhNNu-aRX7N3TLo9BqAczyGWX1ph2vA

Parameters
----------
No need parameters::

Example
-------
Example body::

    {
        "version": 2,
        "blockchain": "BTC",
        "payload": {
            "method": "getbestblockhash",
            "parameter": {},
            "webhook": <User Webhook API>,
            "Id": <Unique ID>
    }

Response
--------
Results::

    {
    "status": 200,
    "values": "0000000000000000000192e1fe636f862d3416bbc13a3a2a084fd1e9775aa903"
    }

------------------------------------------------------------------------------

getblock
========

Returns a string that is serialized, hex-encoded data for block ‘hash’.

Headers
-------
Need to set headers::

    Key             Value

    Content-Type    application/json

    Authorization   OBC eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYW1lIjoib2JjIiwiaWF0IjoxNjAzMTU3NjMzLCJleHAiOjE2MDM3NjI0MzN9.71my1T-2IxQNJhNNu-aRX7N3TLo9BqAczyGWX1ph2vA

Parameters
----------
Need parameters::

    blockhash   hash of the block
                {
                "blockhash": "0000000000000293c83a20b0e537c52fb7903c3b5d6e358400d5574ea0ec33ba"
                }

Example
-------
Example body::
    
    {
        "version": 2,
        "blockchain": "BTC",
        "payload": {
            "method": "getblock",
            "parameter":
            {
                "blockhash": "0000000000000293c83a20b0e537c52fb7903c3b5d6e358400d5574ea0ec33ba"
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
        "hash": "00000000c937983704a73af28acdec37b049d214adbda81d7e2a3dd146f6ed09",
        "confirmations": 654601,
        "strippedsize": 216,
        "size": 216,
        "weight": 864,
        "height": 1000,
        "version": 1,
        "versionHex": "00000001",
        "merkleroot": "fe28050b93faea61fa88c4c630f0e1f0a1c24d0082dd0e10d369e13212128f33",
        "tx": [
            "fe28050b93faea61fa88c4c630f0e1f0a1c24d0082dd0e10d369e13212128f33"
        ],
        "time": 1232346882,
        "mediantime": 1232344831,
        "nonce": 2595206198,
        "bits": "1d00ffff",
        "difficulty": 1,
        "chainwork": "000000000000000000000000000000000000000000000000000003e903e903e9",
        "nTx": 1,
        "previousblockhash": "0000000008e647742775a230787d66fdf92c46a48c896bfbc85cdc8acc67e87d",
        "nextblockhash": "00000000a2887344f8db859e372e7e4bc26b23b9de340f725afbf2edb265b4c6"
    }
    }

------------------------------------------------------------------------------

getblockchaininfo
=================

Returns an object containing various state info regarding blockchain processing.

Headers
-------
Need to set headers::

    Key             Value

    Content-Type    application/json

    Authorization   OBC eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYW1lIjoib2JjIiwiaWF0IjoxNjAzMTU3NjMzLCJleHAiOjE2MDM3NjI0MzN9.71my1T-2IxQNJhNNu-aRX7N3TLo9BqAczyGWX1ph2vA

Parameters
----------
No need parameters::

Example
--------
Example body::

    {
        "version": 2,
        "blockchain": "BTC",
        "payload": {
            "method": "getblockchaininfo",
            "parameter": {},
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
        "chain": "main",
        "blocks": 653506,
        "headers": 653506,
        "bestblockhash": "0000000000000000000192e1fe636f862d3416bbc13a3a2a084fd1e9775aa903",
        "difficulty": 19997335994446.11,
        "mediantime": 1603158828,
        "verificationprogress": 0.9999927472184578,
        "initialblockdownload": false,
        "chainwork": "000000000000000000000000000000000000000014e050ddea8491609bc1e1d2",
        "size_on_disk": 347139991490,
        "pruned": false,
        "softforks": {
            "bip34": {
                "type": "buried",
                "active": true,
                "height": 227931
            },
            "bip66": {
                "type": "buried",
                "active": true,
                "height": 363725
            },
            "bip65": {
                "type": "buried",
                "active": true,
                "height": 388381
            },
            "csv": {
                "type": "buried",
                "active": true,
                "height": 419328
            },
            "segwit": {
                "type": "buried",
                "active": true,
                "height": 481824
            }
        },
        "warnings": ""
        }
    }

------------------------------------------------------------------------------

getblockhash
============

Returns hash of block in best-block-chain at height provided.

Headers
--------
Need to set headers::

    Key             Value

    Content-Type    application/json

    Authorization   OBC eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYW1lIjoib2JjIiwiaWF0IjoxNjAzMTU3NjMzLCJleHAiOjE2MDM3NjI0MzN9.71my1T-2IxQNJhNNu-aRX7N3TLo9BqAczyGWX1ph2vA

Parameters
--------
Need parameters::

    height  value height block
            {
            "height": 1457
            }

Example
--------
Example body::
    
    {
        "version": 2,
        "blockchain": "BTC",
        "payload": {
            "method": "getblockhash",
            "parameter": 
            {
            "height": 1457
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
    "values": "00000000c1b653c16878482f16d9d25f59214468f79ceceb6b0b58020d83aab5"
    }

------------------------------------------------------------------------------

getblockheader
========

bitcoin rpc for get block header.

Headers
--------
Need to set headers::

    Key             Value

    Content-Type    application/json

    Authorization   OBC eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYW1lIjoib2JjIiwiaWF0IjoxNjAzMTU3NjMzLCJleHAiOjE2MDM3NjI0MzN9.71my1T-2IxQNJhNNu-aRX7N3TLo9BqAczyGWX1ph2vA

Parameters
--------
Need parameters::

    blockhash   blockhash of the block
                {
                "hash": "00000000c937983704a73af28acdec37b049d214adbda81d7e2a3dd146f6ed09"
                }

Example
--------
Example body::

    {
        "version": 2,
        "blockchain": "BTC",
        "payload": {
            "method": "getbestblockhash",
            "parameter":
            {
                "hash": "00000000c937983704a73af28acdec37b049d214adbda81d7e2a3dd146f6ed09"
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
        "hash": "00000000c937983704a73af28acdec37b049d214adbda81d7e2a3dd146f6ed09",
        "confirmations": 654601,
        "height": 1000,
        "version": 1,
        "versionHex": "00000001",
        "merkleroot": "fe28050b93faea61fa88c4c630f0e1f0a1c24d0082dd0e10d369e13212128f33",
        "time": 1232346882,
        "mediantime": 1232344831,
        "nonce": 2595206198,
        "bits": "1d00ffff",
        "difficulty": 1,
        "chainwork": "000000000000000000000000000000000000000000000000000003e903e903e9",
        "nTx": 1,
        "previousblockhash": "0000000008e647742775a230787d66fdf92c46a48c896bfbc85cdc8acc67e87d",
        "nextblockhash": "00000000a2887344f8db859e372e7e4bc26b23b9de340f725afbf2edb265b4c6"
    }
    }

------------------------------------------------------------------------------

getblockstats
========

Compute per block statistics for a given window. All amounts are in satoshis.

It won’t work for some heights with pruning.

It won’t work without -txindex for utxo_size_inc, *fee or *feerate stats.

Headers
--------
Need to set headers::

    Key             Value

    Content-Type    application/json

    Authorization   OBC eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYW1lIjoib2JjIiwiaWF0IjoxNjAzMTU3NjMzLCJleHAiOjE2MDM3NjI0MzN9.71my1T-2IxQNJhNNu-aRX7N3TLo9BqAczyGWX1ph2vA

Parameters
--------
Need parameters::

    hash_or_height  set height or hash of the block
                    {
                    "hash_or_height": "10000"
                    } 

Example
--------
Example body::

    {
        "version": 2,
        "blockchain": "BTC",
        "payload": {
            "method": "getbestblockhash",
            "parameter":
            {
                "hash_or_height": "10000"
            } ,
            "webhook": <User Webhook API>,
            "Id": <Unique ID>
        }
    }

Response
--------
Returns the block stats::

    {
    "status": 200,
    "values": {
        "avgfee": 0,
        "avgfeerate": 0,
        "avgtxsize": 0,
        "blockhash": "0000000099c744455f58e6c6e98b671e1bf7f37346bfd4cf5d0274ad8ee660cb",
        "feerate_percentiles": [
            0,
            0,
            0,
            0,
            0
        ],
        "height": 10000,
        "ins": 0,
        "maxfee": 0,
        "maxfeerate": 0,
        "maxtxsize": 0,
        "medianfee": 0,
        "mediantime": 1238985062,
        "mediantxsize": 0,
        "minfee": 0,
        "minfeerate": 0,
        "mintxsize": 0,
        "outs": 1,
        "subsidy": 5000000000,
        "swtotal_size": 0,
        "swtotal_weight": 0,
        "swtxs": 0,
        "time": 1238988213,
        "total_out": 0,
        "total_size": 0,
        "total_weight": 0,
        "totalfee": 0,
        "txs": 1,
        "utxo_increase": 1,
        "utxo_size_inc": 117
    }
}

------------------------------------------------------------------------------

getdifficulty
========

Returns the proof-of-work difficulty as a multiple of the minimum difficulty.

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
Example body::

    {
        "version": 2,
        "blockchain": "BTC",
        "payload": {
            "method": "getdifficulty",
            "parameter":{},
            "webhook": <User Webhook API>,
            "Id": <Unique ID>
        }
    }

Response
--------
Returns the current difficulty::

    {
    "status": 200,
    "values": 19997335994446.11
    }   

------------------------------------------------------------------------------

getmemoryinfo
========

Returns an object containing information about memory usage.

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
Example::

    {
        "version": 2,
        "blockchain": "BTC",
        "payload": {
            "method": "getmemoryinfo",
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
    "values": {
        "locked": {
            "used": 117056,
            "free": 145088,
            "total": 262144,
            "locked": 262144,
            "chunks_used": 3656,
            "chunks_free": 2
            }
        }
    }   

------------------------------------------------------------------------------

getrpcinfo
========

Returns details of the RPC server.

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
Example::

    {
        "version": 2,
        "blockchain": "BTC",
        "payload": {
            "method": "getrpcinfo",
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
    "values": {
        "active_commands": [
            {
                "method": "getrpcinfo",
                "duration": 1037
            }
        ],
        "logpath": "/var/lib/bitcoind/debug.log"
        }
    }   

------------------------------------------------------------------------------

help
========

List all commands, or get help for a specified command.

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
Example::

    {
        "version": 2,
        "blockchain": "BTC",
        "payload": {
            "method": "help",
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
    "values": "== Blockchain ==\ngetbestblockhash\ngetblock \"blockhash\" ( verbosity )\ngetblockchaininfo\ngetblockcount\ngetblockfilter \"blockhash\" ( \"filtertype\" )\ngetblockhash height\ngetblockheader \"blockhash\" ( verbose )\ngetblockstats hash_or_height ( stats )\ngetchaintips\ngetchaintxstats ( nblocks \"blockhash\" )\ngetdifficulty\ngetmempoolancestors \"txid\" ( verbose )\ngetmempooldescendants \"txid\" ( verbose )\ngetmempoolentry \"txid\"\ngetmempoolinfo\ngetrawmempool ( verbose )\ngettxout \"txid\" n ( include_mempool )\ngettxoutproof [\"txid\",...] ( \"blockhash\" )\ngettxoutsetinfo\npreciousblock \"blockhash\"\npruneblockchain height\nsavemempool\nscantxoutset \"action\" [scanobjects,...]\nverifychain ( checklevel nblocks )\nverifytxoutproof \"proof\"\n\n== Control ==\ngetmemoryinfo ( \"mode\" )\ngetrpcinfo\nhelp ( \"command\" )\nlogging ( [\"include_category\",...] [\"exclude_category\",...] )\nstop\nuptime\n\n== Generating ==\ngeneratetoaddress nblocks \"address\" ( maxtries )\n\n== Mining ==\ngetblocktemplate ( \"template_request\" )\ngetmininginfo\ngetnetworkhashps ( nblocks height )\nprioritisetransaction \"txid\" ( dummy ) fee_delta\nsubmitblock \"hexdata\" ( \"dummy\" )\nsubmitheader \"hexdata\"\n\n== Network ==\naddnode \"node\" \"command\"\nclearbanned\ndisconnectnode ( \"address\" nodeid )\ngetaddednodeinfo ( \"node\" )\ngetconnectioncount\ngetnettotals\ngetnetworkinfo\ngetnodeaddresses ( count )\ngetpeerinfo\nlistbanned\nping\nsetban \"subnet\" \"command\" ( bantime absolute )\nsetnetworkactive state\n\n== Rawtransactions ==\nanalyzepsbt \"psbt\"\ncombinepsbt [\"psbt\",...]\ncombinerawtransaction [\"hexstring\",...]\nconverttopsbt \"hexstring\" ( permitsigdata iswitness )\ncreatepsbt [{\"txid\":\"hex\",\"vout\":n,\"sequence\":n},...] [{\"address\":amount},{\"data\":\"hex\"},...] ( locktime replaceable )\ncreaterawtransaction [{\"txid\":\"hex\",\"vout\":n,\"sequence\":n},...] [{\"address\":amount},{\"data\":\"hex\"},...] ( locktime replaceable )\ndecodepsbt \"psbt\"\ndecoderawtransaction \"hexstring\" ( iswitness )\ndecodescript \"hexstring\"\nfinalizepsbt \"psbt\" ( extract )\nfundrawtransaction \"hexstring\" ( options iswitness )\ngetrawtransaction \"txid\" ( verbose \"blockhash\" )\njoinpsbts [\"psbt\",...]\nsendrawtransaction \"hexstring\" ( maxfeerate )\nsignrawtransactionwithkey \"hexstring\" [\"privatekey\",...] ( [{\"txid\":\"hex\",\"vout\":n,\"scriptPubKey\":\"hex\",\"redeemScript\":\"hex\",\"witnessScript\":\"hex\",\"amount\":amount},...] \"sighashtype\" )\ntestmempoolaccept [\"rawtx\",...] ( maxfeerate )\nutxoupdatepsbt \"psbt\" ( [\"\",{\"desc\":\"str\",\"range\":n or [n,n]},...] )\n\n== Util ==\ncreatemultisig nrequired [\"key\",...] ( \"address_type\" )\nderiveaddresses \"descriptor\" ( range )\nestimatesmartfee conf_target ( \"estimate_mode\" )\ngetdescriptorinfo \"descriptor\"\nsignmessagewithprivkey \"privkey\" \"message\"\nvalidateaddress \"address\"\nverifymessage \"address\" \"signature\" \"message\"\n\n== Wallet ==\nabandontransaction \"txid\"\nabortrescan\naddmultisigaddress nrequired [\"key\",...] ( \"label\" \"address_type\" )\nbackupwallet \"destination\"\nbumpfee \"txid\" ( options )\ncreatewallet \"wallet_name\" ( disable_private_keys blank \"passphrase\" avoid_reuse )\ndumpprivkey \"address\"\ndumpwallet \"filename\"\nencryptwallet \"passphrase\"\ngetaddressesbylabel \"label\"\ngetaddressinfo \"address\"\ngetbalance ( \"dummy\" minconf include_watchonly avoid_reuse )\ngetbalances\ngetnewaddress ( \"label\" \"address_type\" )\ngetrawchangeaddress ( \"address_type\" )\ngetreceivedbyaddress \"address\" ( minconf )\ngetreceivedbylabel \"label\" ( minconf )\ngettransaction \"txid\" ( include_watchonly verbose )\ngetunconfirmedbalance\ngetwalletinfo\nimportaddress \"address\" ( \"label\" rescan p2sh )\nimportmulti \"requests\" ( \"options\" )\nimportprivkey \"privkey\" ( \"label\" rescan )\nimportprunedfunds \"rawtransaction\" \"txoutproof\"\nimportpubkey \"pubkey\" ( \"label\" rescan )\nimportwallet \"filename\"\nkeypoolrefill ( newsize )\nlistaddressgroupings\nlistlabels ( \"purpose\" )\nlistlockunspent\nlistreceivedbyaddress ( minconf include_empty include_watchonly \"address_filter\" )\nlistreceivedbylabel ( minconf include_empty include_watchonly )\nlistsinceblock ( \"blockhash\" target_confirmations include_watchonly include_removed )\nlisttransactions ( \"label\" count skip include_watchonly )\nlistunspent ( minconf maxconf [\"address\",...] include_unsafe query_options )\nlistwalletdir\nlistwallets\nloadwallet \"filename\"\nlockunspent unlock ( [{\"txid\":\"hex\",\"vout\":n},...] )\nremoveprunedfunds \"txid\"\nrescanblockchain ( start_height stop_height )\nsendmany \"\" {\"address\":amount} ( minconf \"comment\" [\"address\",...] replaceable conf_target \"estimate_mode\" )\nsendtoaddress \"address\" amount ( \"comment\" \"comment_to\" subtractfeefromamount replaceable conf_target \"estimate_mode\" avoid_reuse )\nsethdseed ( newkeypool \"seed\" )\nsetlabel \"address\" \"label\"\nsettxfee amount\nsetwalletflag \"flag\" ( value )\nsignmessage \"address\" \"message\"\nsignrawtransactionwithwallet \"hexstring\" ( [{\"txid\":\"hex\",\"vout\":n,\"scriptPubKey\":\"hex\",\"redeemScript\":\"hex\",\"witnessScript\":\"hex\",\"amount\":amount},...] \"sighashtype\" )\nunloadwallet ( \"wallet_name\" )\nwalletcreatefundedpsbt [{\"txid\":\"hex\",\"vout\":n,\"sequence\":n},...] [{\"address\":amount},{\"data\":\"hex\"},...] ( locktime options bip32derivs )\nwalletlock\nwalletpassphrase \"passphrase\" timeout\nwalletpassphrasechange \"oldpassphrase\" \"newpassphrase\"\nwalletprocesspsbt \"psbt\" ( sign \"sighashtype\" bip32derivs )\n\n== Zmq ==\ngetzmqnotifications"
    }  

------------------------------------------------------------------------------

uptime
========

Returns the total uptime of the server.

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
Example::

    {
        "version": 2,
        "blockchain": "BTC",
        "payload": {
            "method": "uptime",
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
    "values": 423824
    }  

------------------------------------------------------------------------------

getconnectioncount
========

Returns the number of connections to other nodes.

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
Example::

    {
        "version": 2,
        "blockchain": "BTC",
        "payload": {
            "method": "getconnectioncount",
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
    "values": 10
    }  

------------------------------------------------------------------------------

getnettotals
========

Returns information about network traffic, including bytes in, bytes out, and current time.

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
Example::

    {
        "version": 2,
        "blockchain": "BTC",
        "payload": {
            "method": "help",
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
    "values": {
        "totalbytesrecv": 3299246288,
        "totalbytessent": 40608233565,
        "timemillis": 1603167889678,
        "uploadtarget": {
            "timeframe": 86400,
            "target": 0,
            "target_reached": false,
            "serve_historical_blocks": true,
            "bytes_left_in_cycle": 0,
            "time_left_in_cycle": 0
            }
        }
    } 

------------------------------------------------------------------------------

getnetworkinfo
========

Returns an object containing various state info regarding P2P networking.

Example::

    https://integrationhub.okwave.global/api/v2/btcmainnet/getnetworkinfo

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
Example::

    var request = require('request');
    var options = {
        'method': 'GET',
        'url': 'https://integrationhub.okwave.global/api/v2/btcmainnet/getnetworkinfo',
        'headers': {
            'Authorization': 'OBC eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYW1lIjoib2JjIiwiaWF0IjoxNjAzMTU3NjMzLCJleHAiOjE2MDM3NjI0MzN9.71my1T-2IxQNJhNNu-aRX7N3TLo9BqAczyGWX1ph2vA',
            'Content-Type': 'application/json'
    }
    };
    request(options, function (error, response) {
        if (error) throw new Error(error);
        console.log(response.body);
    });

Response
--------
Results::

    {
    "status": 200,
    "values": {
        "version": 190001,
        "subversion": "/Satoshi:0.19.0.1/",
        "protocolversion": 70015,
        "localservices": "0000000000000409",
        "localservicesnames": [
            "NETWORK",
            "WITNESS",
            "NETWORK_LIMITED"
        ],
        "localrelay": true,
        "timeoffset": 0,
        "networkactive": true,
        "connections": 10,
        "networks": [
            {
                "name": "ipv4",
                "limited": false,
                "reachable": true,
                "proxy": "",
                "proxy_randomize_credentials": false
            },
            {
                "name": "ipv6",
                "limited": false,
                "reachable": true,
                "proxy": "",
                "proxy_randomize_credentials": false
            },
            {
                "name": "onion",
                "limited": true,
                "reachable": false,
                "proxy": "",
                "proxy_randomize_credentials": false
            }
        ],
        "relayfee": 0.00001,
        "incrementalfee": 0.00001,
        "localaddresses": [
            {
                "address": "20.8.1.103",
                "port": 8333,
                "score": 1
            }
        ],
        "warnings": ""
        }
    }  

------------------------------------------------------------------------------

getpeerinfo
========

Returns data about each connected network node as a json array of objects.

Example::

    https://integrationhub.okwave.global/api/v2/btcmainnet/getpeerinfo

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
Example::

    var request = require('request');
    var options = {
        'method': 'GET',
        'url': 'https://integrationhub.okwave.global/api/v2/btcmainnet/getpeerinfo',
        'headers': {
            'Authorization': 'OBC eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYW1lIjoib2JjIiwiaWF0IjoxNjAzMTU3NjMzLCJleHAiOjE2MDM3NjI0MzN9.71my1T-2IxQNJhNNu-aRX7N3TLo9BqAczyGWX1ph2vA',
            'Content-Type': 'application/json'
    }
    };
    request(options, function (error, response) {
        if (error) throw new Error(error);
        console.log(response.body);
    });

Response
--------
Results::

    {
    "status": 200,
    "values": [
        {
            "id": 0,
            "addr": "51.154.60.34:8333",
            "addrlocal": "13.250.189.186:10157",
            "addrbind": "20.8.1.33:51984",
            "services": "000000000000040d",
            "servicesnames": [
                "NETWORK",
                "BLOOM",
                "WITNESS",
                "NETWORK_LIMITED"
            ],
            "relaytxes": true,
            "lastsend": 1603168028,
            "lastrecv": 1603168031,
            "bytessent": 124958917,
            "bytesrecv": 458812896,
            "conntime": 1602037402,
            "timeoffset": 7,
            "pingtime": 0.234671,
            "minping": 0.148192,
            "version": 70015,
            "subver": "/Satoshi:0.18.0/",
            "inbound": false,
            "addnode": false,
            "startingheight": 651584,
            "banscore": 0,
            "synced_headers": 653523,
            "synced_blocks": 653523,
            "inflight": [],
            "whitelisted": false,
            "permissions": [],
            "minfeefilter": 0.00001,
            "bytessent_per_msg": {
                "addr": 236115,
                "feefilter": 32,
                "getaddr": 24,
                "getblocktxn": 725,
                "getdata": 28047333,
                "getheaders": 1053,
                "headers": 50456,
                "inv": 91387979,
                "notfound": 111767,
                "ping": 301408,
                "pong": 301376,
                "sendcmpct": 99,
                "sendheaders": 24,
                "tx": 4520374,
                "verack": 24,
                "version": 128
            },
            "bytesrecv_per_msg": {
                "addr": 209662,
                "blocktxn": 816959,
                "cmpctblock": 17018070,
                "feefilter": 32,
                "getdata": 431988,
                "getheaders": 1053,
                "headers": 45280,
                "inv": 70147264,
                "notfound": 56327,
                "ping": 301376,
                "pong": 301408,
                "reject": 15625,
                "sendcmpct": 66,
                "sendheaders": 24,
                "tx": 369467612,
                "verack": 24,
                "version": 126
            }
        },
        {
            "id": 1,
            "addr": "93.88.75.75:8333",
            "addrlocal": "13.250.189.186:27409",
            "addrbind": "20.8.1.33:55542",
            "services": "000000000000040d",
            "servicesnames": [
                "NETWORK",
                "BLOOM",
                "WITNESS",
                "NETWORK_LIMITED"
            ],
            "relaytxes": true,
            "lastsend": 1603168030,
            "lastrecv": 1603168030,
            "bytessent": 123770795,
            "bytesrecv": 596513702,
            "conntime": 1602037407,
            "timeoffset": 5,
            "pingtime": 0.181661,
            "minping": 0.155844,
            "version": 70015,
            "subver": "/Satoshi:0.16.0/",
            "inbound": false,
            "addnode": false,
            "startingheight": 651582,
            "banscore": 0,
            "synced_headers": 653523,
            "synced_blocks": 653523,
            "inflight": [],
            "whitelisted": false,
            "permissions": [],
            "minfeefilter": 0.00001,
            "bytessent_per_msg": {
                "addr": 239220,
                "block": 1079340,
                "cmpctblock": 192895,
                "feefilter": 32,
                "getaddr": 24,
                "getblocktxn": 4360,
                "getdata": 34222609,
                "getheaders": 1053,
                "headers": 153594,
                "inv": 86655890,
                "notfound": 35328,
                "ping": 301408,
                "pong": 301472,
                "sendcmpct": 198,
                "sendheaders": 24,
                "tx": 583196,
                "verack": 24,
                "version": 128
            },
            "bytesrecv_per_msg": {
                "addr": 188662,
                "blocktxn": 2360809,
                "cmpctblock": 9289483,
                "feefilter": 32,
                "getdata": 78575,
                "getheaders": 1053,
                "headers": 115982,
                "inv": 75128871,
                "notfound": 64996,
                "ping": 301472,
                "pong": 301408,
                "reject": 13508,
                "sendcmpct": 132,
                "sendheaders": 24,
                "tx": 508668545,
                "verack": 24,
                "version": 126
            }
        },
        ]
    } 

------------------------------------------------------------------------------

listbanned
========

List all banned IPs/Subnets.

Example::

    https://integrationhub.okwave.global/api/v2/btcmainnet/listbanned

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
Example::

    var request = require('request');
    var options = {
        'method': 'GET',
        'url': 'https://integrationhub.okwave.global/api/v2/btcmainnet/listbanned',
        'headers': {
            'Authorization': 'OBC eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYW1lIjoib2JjIiwiaWF0IjoxNjAzMTU3NjMzLCJleHAiOjE2MDM3NjI0MzN9.71my1T-2IxQNJhNNu-aRX7N3TLo9BqAczyGWX1ph2vA',
            'Content-Type': 'application/json'
    }
    };
    request(options, function (error, response) {
        if (error) throw new Error(error);
        console.log(response.body);
    });

Response
--------
Results::

    {
    "status": 200,
    "values": []
    }

------------------------------------------------------------------------------

ping
========

Requests that a ping be sent to all other nodes, to measure ping time.

Results provided in getpeerinfo, pingtime and pingwait fields are decimal seconds.

Ping command is handled in queue with all other commands, so it measures processing backlog, not just network ping.

Example::

    https://integrationhub.okwave.global/api/v2/btcmainnet/ping

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
Example::

    var request = require('request');
    var options = {
        'method': 'GET',
        'url': 'https://integrationhub.okwave.global/api/v2/btcmainnet/ping',
        'headers': {
            'Authorization': 'OBC eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYW1lIjoib2JjIiwiaWF0IjoxNjAzMTU3NjMzLCJleHAiOjE2MDM3NjI0MzN9.71my1T-2IxQNJhNNu-aRX7N3TLo9BqAczyGWX1ph2vA',
            'Content-Type': 'application/json'
    }
    };
    request(options, function (error, response) {
        if (error) throw new Error(error);
        console.log(response.body);
    });

Response
--------
Returns ping status::

    {
    "status": 200,
    "values": "Operation completed succcessfully"
    }

------------------------------------------------------------------------------

getutxobyaddress
========

bitcoin rpc for getutxobyaddress.

Returns the best block hash::

    https://integrationhub.okwave.global/api/v2/btcmainnet/getutxobyaddress

Headers
--------
Need to set headers::

    Key             Value

    Content-Type    application/json

    Authorization   OBC eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYW1lIjoib2JjIiwiaWF0IjoxNjAzMTU3NjMzLCJleHAiOjE2MDM3NjI0MzN9.71my1T-2IxQNJhNNu-aRX7N3TLo9BqAczyGWX1ph2vA

Parameters
--------
Parameters::

    address     address for account
                {
                "address": "n4rZHAPGXCu8bYchjzJhK3V7VVreascJxe"
                }

Example
--------
Example::
    
    var request = require('request');
    var options = {
        'method': 'POST',
        'url': 'https://integrationhub.okwave.global/api/v2/btcmainnet/getutxobyaddress',
        'headers': {
            'Authorization': 'OBC eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYW1lIjoib2JjIiwiaWF0IjoxNjAzMTU3NjMzLCJleHAiOjE2MDM3NjI0MzN9.71my1T-2IxQNJhNNu-aRX7N3TLo9BqAczyGWX1ph2vA',
            'Content-Type': 'application/json'
    },
    body: JSON.stringify({"address":"n3Z4FToecPHbjPyVDVsPgoFjcvYvq6SiFR"})
    };
    request(options, function (error, response) {
        if (error) throw new Error(error);
        console.log(response.body);
    });

Response
--------
Returns the utxo address::

    {
    "status": 200,
    "values": []
    }

------------------------------------------------------------------------------

getbalancebyaddress
========

Returns the total available balance in specific address.

Example::

    https://integrationhub.okwave.global/api/v2/btcmainnet/getbalancebyaddress

Headers
--------
Need to set headers::

    Key             Value

    Content-Type    application/json

    Authorization   OBC eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYW1lIjoib2JjIiwiaWF0IjoxNjAzMTU3NjMzLCJleHAiOjE2MDM3NjI0MzN9.71my1T-2IxQNJhNNu-aRX7N3TLo9BqAczyGWX1ph2vA

Parameters
--------
Need parameters::

    address     address for account
                {
                "address": "1HnRsoRMD4EhjryV6Pi91hj9gsSMbgXC3V"
                } 

Example
--------
Example::

    var request = require('request');
    var options = {
        'method': 'POST',
        'url': 'https://integrationhub.okwave.global/api/v2/btcmainnet/getbalancebyaddress',
        'headers': {
            'Authorization': 'OBC eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYW1lIjoib2JjIiwiaWF0IjoxNjAzMTU3NjMzLCJleHAiOjE2MDM3NjI0MzN9.71my1T-2IxQNJhNNu-aRX7N3TLo9BqAczyGWX1ph2vA',
            'Content-Type': 'application/json'
    },
    body: JSON.stringify({"address":"n3Z4FToecPHbjPyVDVsPgoFjcvYvq6SiFR"})
    };
    request(options, function (error, response) {
        if (error) throw new Error(error);
        console.log(response.body);
    });
  
Response
--------
Results::

    {
    "status": 200,
    "values": {
        "confirmed": 0,
        "unconfirmed": 0,
        "balance": 0
        }
    }

------------------------------------------------------------------------------

gettransactionbytxid
========

bitcoin rpc for gettransactionbytxid.

Returns the best block hash::

    https://integrationhub.okwave.global/api/v2/btcmainnet/gettransactionbytxid

Headers
--------
Need to set headers::

    Key             Value

    Content-Type    application/json

    Authorization   OBC eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYW1lIjoib2JjIiwiaWF0IjoxNjAzMTU3NjMzLCJleHAiOjE2MDM3NjI0MzN9.71my1T-2IxQNJhNNu-aRX7N3TLo9BqAczyGWX1ph2vA

Parameters
--------
Parameters::

    txid        transaction id of block
                {
                "txid": "b70dff05c88115938588fb769a986b90574f7d0682b2209b9e26f947ca106220"
                } 

Example
--------
Example::
    
    var request = require('request');
    var options = {
        'method': 'POST',
        'url': 'https://integrationhub.okwave.global/api/v2/btcmainnet/gettransactionbytxid',
        'headers': {
            'Authorization': 'OBC eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYW1lIjoib2JjIiwiaWF0IjoxNjAzMTU3NjMzLCJleHAiOjE2MDM3NjI0MzN9.71my1T-2IxQNJhNNu-aRX7N3TLo9BqAczyGWX1ph2vA',
            'Content-Type': 'application/json'
    },
    body: JSON.stringify({"txid":"7a4284ed47e0d68eac8c0cf62a697a2f9411a53975b146444f8b17640cfca891"})
    };
    request(options, function (error, response) {
        if (error) throw new Error(error);
        console.log(response.body);
    });

Response
--------
Results::

    {
    "status": 200,
    "values": {
        "_id": "5fa4ae6128d40b5fd0f097e9",
        "txid": "b70dff05c88115938588fb769a986b90574f7d0682b2209b9e26f947ca106220",
        "network": "mainnet",
        "chain": "BTC",
        "blockHeight": -1,
        "blockHash": "",
        "blockTime": "2020-11-06T02:01:00.816Z",
        "blockTimeNormalized": "2020-11-06T02:01:00.816Z",
        "coinbase": false,
        "locktime": -1,
        "inputCount": 3,
        "outputCount": 1,
        "size": 483,
        "fee": 241434,
        "value": 1473130,
        "confirmations": 0
    }
    }

------------------------------------------------------------------------------

gettransactionbyaddress
========

Get detailed information about in-wallet transaction <txid>.

Example::

    https://integrationhub.okwave.global/api/v2/btcmainnet/gettransactionbyaddress

Headers
--------
Need to set headers::

    Key             Value

    Content-Type    application/json

    Authorization   OBC eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYW1lIjoib2JjIiwiaWF0IjoxNjAzMTU3NjMzLCJleHAiOjE2MDM3NjI0MzN9.71my1T-2IxQNJhNNu-aRX7N3TLo9BqAczyGWX1ph2vA

Parameters
--------
Parameters::

    address     block address
                {
                "address": "1HnRsoRMD4EhjryV6Pi91hj9gsSMbgXC3V"
                }

Example
--------
Example::

    var request = require('request');
    var options = {
        'method': 'POST',
        'url': 'https://integrationhub.okwave.global/api/v2/btcmainnet/gettransactionbyaddress',
        'headers': {
            'Authorization': 'OBC eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYW1lIjoib2JjIiwiaWF0IjoxNjAzMTU3NjMzLCJleHAiOjE2MDM3NjI0MzN9.71my1T-2IxQNJhNNu-aRX7N3TLo9BqAczyGWX1ph2vA',
            'Content-Type': 'application/json'
    },
    body: JSON.stringify({"address":"n4rZHAPGXCu8bYchjzJhK3V7VVreascJxe"})
    };
    request(options, function (error, response) {
        if (error) throw new Error(error);
        console.log(response.body);
    });

Response
--------
Results::

    {
    "status": 200,
    "values": [
        {
            "_id": "5fa4ae1e28d40b5fd0f02e4a",
            "chain": "BTC",
            "network": "mainnet",
            "coinbase": false,
            "mintIndex": 2,
            "spentTxid": "b70dff05c88115938588fb769a986b90574f7d0682b2209b9e26f947ca106220",
            "mintTxid": "971ec10a9334b299a6d2fcf5464efbf0c7b009c1c1ae4b931127e78933d5c349",
            "mintHeight": -1,
            "spentHeight": -1,
            "address": "1HnRsoRMD4EhjryV6Pi91hj9gsSMbgXC3V",
            "script": "76a914b8197f03ac3f64b99d94ceacb7ef44dd7d08638688ac",
            "value": 95369,
            "confirmations": -1,
            "sequenceNumber": 4294967295
        },
        {
            "_id": "5fa4abc728d40b5fd0ec7073",
            "chain": "BTC",
            "network": "mainnet",
            "coinbase": false,
            "mintIndex": 0,
            "spentTxid": "b70dff05c88115938588fb769a986b90574f7d0682b2209b9e26f947ca106220",
            "mintTxid": "f0cc380a3f0bc2a1d030833bb45f683ac08ed26b07e72a747afbc911a0ca6157",
            "mintHeight": -1,
            "spentHeight": -1,
            "address": "1HnRsoRMD4EhjryV6Pi91hj9gsSMbgXC3V",
            "script": "76a914b8197f03ac3f64b99d94ceacb7ef44dd7d08638688ac",
            "value": 94893,
            "confirmations": -1,
            "sequenceNumber": 4294967295
        },
        {
            "_id": "5fa4aa9d28d40b5fd0eaf294",
            "chain": "BTC",
            "network": "mainnet",
            "coinbase": false,
            "mintIndex": 9,
            "spentTxid": "b70dff05c88115938588fb769a986b90574f7d0682b2209b9e26f947ca106220",
            "mintTxid": "5ca6008b02119848b3b44370c354108ddf34c0ce90f405cafd5d0e1fd903d35b",
            "mintHeight": -1,
            "spentHeight": -1,
            "address": "1HnRsoRMD4EhjryV6Pi91hj9gsSMbgXC3V",
            "script": "76a914b8197f03ac3f64b99d94ceacb7ef44dd7d08638688ac",
            "value": 1524302,
            "confirmations": -1,
            "sequenceNumber": 4294967295
        }
    ]
    }

------------------------------------------------------------------------------

createrawtransaction
====================

bitcoin rpc for createrawtransaction.

Returns the best block hash::

    https://integrationhub.okwave.global/api/v2/btcmainnet/createrawtransaction

Headers
-------
Need to set headers::

    Key             Value

    Content-Type    application/json

    Authorization   OBC eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYW1lIjoib2JjIiwiaWF0IjoxNjAzMTU3NjMzLCJleHAiOjE2MDM3NjI0MzN9.71my1T-2IxQNJhNNu-aRX7N3TLo9BqAczyGWX1ph2vA

Parameters
--------
Need parameters::

    JSON Object     txid and txout
                    {
                        "txin": [
                                    {
                                    "txid": "39105b99edf04adcdce79cf0c0496152bfe876596cfb59504317b62e89769566",
                                    "vout": 0
                                    }
                                ],
                        "txout": [
                            {
                                "address": "2NFBd2GAgnPuyK6BPcDDgodiDchxKbDgWGh",
                                "amount": 0.0005
                            }
                        ]
                    }

Example
--------
Example::

    var request = require('request');
    var options = {
        'method': 'POST',
        'url': 'https://integrationhub.okwave.global/api/v2/btcmainnet/createrawtransaction',
        'headers': {
            'Authorization': 'OBC eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYW1lIjoib2JjIiwiaWF0IjoxNjAzMTU3NjMzLCJleHAiOjE2MDM3NjI0MzN9.71my1T-2IxQNJhNNu-aRX7N3TLo9BqAczyGWX1ph2vA',
            'Content-Type': 'application/json'
    },
    body: JSON.stringify({"txin":[{"txid":"","vout":0}],"txout":[{"address":"","amount":0}]})
    };
    request(options, function (error, response) {
        if (error) throw new Error(error);
        console.log(response.body);
    });

Response
--------
Returns the transaction hash::

    {
    "status": ,
    "values": "0100000001e34ac1e2baac09c366fce1c2245536bda8f7db0f6685862aecf53ebd69f9a89c0000000000ffffffff02a0252600000000001976a914d90d36e98f62968d2bc9bbd68107564a156a9bcf88ac50622500000000001976a91407bdb518fa2e6089fd810235cf1100c9c13d1fd288ac00000000"
    }

------------------------------------------------------------------------------

sendrawtransaction
========

bitcoin rpc for sendrawtransaction.

Returns the best block hash::

    https://integrationhub.okwave.global/api/v2/btcmainnet/sendrawtransaction

Headers
--------
Need to set headers::

    Key             Value

    Content-Type    application/json

    Authorization   OBC eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYW1lIjoib2JjIiwiaWF0IjoxNjAzMTU3NjMzLCJleHAiOjE2MDM3NjI0MzN9.71my1T-2IxQNJhNNu-aRX7N3TLo9BqAczyGWX1ph2vA

Parameters
--------
Need parameters::

    hexstring     hexstring and privatekey
    and           {
    privatekey      "hexstring": "0200000001669576892eb617435059fb6c5976e8bf526149c0f09ce7dcdc4af0ed995b10390000000000ffffffff0150c300000000000017a914f0a454d03ca355e47b13fbdd497d258a0b365b0a8700000000",
                    "allowhighfees": true
                    } 

Example
--------
Example::

    var request = require('request');
    var options = {
        'method': 'POST',
        'url': 'https://integrationhub.okwave.global/api/v2/btcmainnet/sendrawtransaction',
        'headers': {
            'Authorization': 'OBC eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYW1lIjoib2JjIiwiaWF0IjoxNjAzMTU3NjMzLCJleHAiOjE2MDM3NjI0MzN9.71my1T-2IxQNJhNNu-aRX7N3TLo9BqAczyGWX1ph2vA',
            'Content-Type': 'application/json'
    },
    body: JSON.stringify({"hexstring":"0200000001669576892eb617435059fb6c5976e8bf526149c0f09ce7dcdc4af0ed995b10390000000000ffffffff0150c300000000000017a914f0a454d03ca355e47b13fbdd497d258a0b365b0a8700000000","privkeys":[""]})
    };
    request(options, function (error, response) {
        if (error) throw new Error(error);
        console.log(response.body);
    });

Response
--------
Returns the result for sendrawtransaction::

    {
    "status": 200,
    "values": 
    }