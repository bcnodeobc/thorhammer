========
Bitcoin
========

All RPC included are based on bitcoin-cli. 

Request URL : http://integrationhub.okwave.global/api/v2/

.. note::  Make sure to enter received token in headers using key 'Authorization'. 

------------------------------------------------------------------------------

getblockcount
=============

The latest number of blocks in the longest blockchain.

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
Results::

    {
        "payload": {
            "method": "getblockcount",
            "parameter": {},
            "webhook": <User Webhook API>,
            "id": <Unique ID>
        },
        "result": 690320
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
Example JSON body::

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
        "payload": {
            "method":"getbestblockhash",
            "parameter":{},
            "webhook": <User Webhook API>,
            "id": <Unique ID>
        },
        "result":"00000000000000000003d2b25625609863b9284b407268cf63f4b2730a9c4bb8"
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
Example JSON body::
    
    {
        "version": 2,
        "blockchain": "BTC",
        "payload": {
            "method": "getblock",
            "parameter": {
                "blockhash": "00000000000000000002261dcf468e8eb604e9c0a8c747e27305787b86d1126f"
            },
            "webhook": <User Webhook API>,
            "id": <Unique ID>
        }
    }

Response
--------
Results::

    {
        "payload": {
            "method":"getblock",
            "parameter": {
                "blockhash":"00000000000000000002261dcf468e8eb604e9c0a8c747e27305787b86d1126f"
            },
            "webhook":"https://webhook.site/44275a9d-feac-4d26-9431-8d313da43490",
            "id":"0007"
        },
        "result": {
            "hash":"00000000000000000002261dcf468e8eb604e9c0a8c747e27305787b86d1126f",
            "confirmations":4444,
            "strippedsize":773109,
            "size":1673937,
            "weight":3993264,
            "height":685879,
            "version":545259524,
            "versionHex":"20800004",
            "merkleroot":"1f325b56d38ec591448e027b978a3e0ac35e317979fb5f5758de5a981e3f4b08",
            "tx":["40160b63c5e89e7cdb2310cda62ae810a568046f0d53ccd19cb4269892588def", ...],
            "time": 1622604448,
            "mediantime": 1622600666,
            "nonce": 1280152327,
            "bits": "170d5f7b",
            "difficulty": 21047730572451.55,
            "chainwork": "00000000000000000000000000000000000000001e2da3f71b2c5fc533dd27f8",
            "nTx": 833,
            "previousblockhash": "0000000000000000000562b2c69e2a47efd5ea21ff5de4432d2caca8714e2382",
            "nextblockhash": "0000000000000000000ca344f248804fbafa17d44ddf63283dea48cb5495793a"
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
Example JSON body::

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
        "payload": {
            "method":"getblockchaininfo",
            "parameter":{},
            "webhook": <User Webhook API>,
            "id": <Unique ID>
        },
        "result": {
            "chain":"main",
            "blocks":690323,
            "headers":690323,
            "bestblockhash":"000000000000000000012f9e74160a42c364d5c39396ecf6b6ae952558ccdfcc",
            "difficulty":14363025673659.96,
            "mediantime":1625857194,
            "verificationprogress":0.9999989955370537,
            "initialblockdownload":false,
            "chainwork":"00000000000000000000000000000000000000001f5dbb8efdfef526b5723208",
            "size_on_disk":401890777454,
            "pruned":false,
            "softforks": {
                            "bip34": {"type":"buried","active":true,"height":227931},
                            "bip66": {"type":"buried","active":true,"height":363725},
                            "bip65": {"type":"buried","active":true,"height":388381},
                            "csv": {"type":"buried","active":true,"height":419328},
                            "segwit": {"type":"buried","active":true,"height":481824}
                        },
            "warnings":"Warning: unknown new rules activated (versionbit 2)"
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
            "height": 1000
            }

Example
--------
Example JSON body::
    
    {
        "version": 2,
        "blockchain": "BTC",
        "payload": {
            "method": "getblockhash",
            "parameter": 
            {
                "height": 1000
            },
            "webhook": <User Webhook API>,
            "Id": <Unique ID>
        }
    }

Response
--------
Results::

    {
        "payload": {
            "method":"getblockhash",
            "parameter": {
                "height":1000
            },
            "webhook": <User Webhook API>,
            "id": <Unique ID>
        },
        "result":"00000000c937983704a73af28acdec37b049d214adbda81d7e2a3dd146f6ed09"
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
                "hash": "00000000000000000002261dcf468e8eb604e9c0a8c747e27305787b86d1126f"
                }

Example
--------
Example JSON body::

    {
        "version": 2,
        "blockchain": "BTC",
        "payload": {
            "method": "getblockheader",
            "parameter":
            {
                "hash": "00000000000000000002261dcf468e8eb604e9c0a8c747e27305787b86d1126f"
            },
            "webhook": <User Webhook API>,
            "Id": <Unique ID>
        }
    }

Response
--------
Results::

    {
        "payload": {
            "method":"getblockheader",
            "parameter": {
                "hash":"00000000000000000002261dcf468e8eb604e9c0a8c747e27305787b86d1126f"
            },
            "webhook": <User Webhook API>,
            "id": <Unique ID>
        },
        "result": {
            "hash":"00000000000000000002261dcf468e8eb604e9c0a8c747e27305787b86d1126f",
            "confirmations":4445,
            "height":685879,
            "version":545259524,
            "versionHex":"20800004",
            "merkleroot":"1f325b56d38ec591448e027b978a3e0ac35e317979fb5f5758de5a981e3f4b08",
            "time":1622604448,
            "mediantime":1622600666,
            "nonce":1280152327,
            "bits":"170d5f7b",
            "difficulty":21047730572451.55,
            "chainwork":"00000000000000000000000000000000000000001e2da3f71b2c5fc533dd27f8",
            "nTx":833,
            "previousblockhash":"0000000000000000000562b2c69e2a47efd5ea21ff5de4432d2caca8714e2382",
            "nextblockhash":"0000000000000000000ca344f248804fbafa17d44ddf63283dea48cb5495793a"
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

    height set height of the block
                    {
                    "height": "10000"
                    } 

Example
--------
Example JSON body::

    {
        "version": 2,
        "blockchain": "BTC",
        "payload": {
            "method": "getblockstats",
            "parameter":
            {
                "height": "10000"
            } ,
            "webhook": <User Webhook API>,
            "Id": <Unique ID>
        }
    }

Response
--------
Returns the block stats::

    {
        "payload": {
            "method":"getblockstats",
            "parameter": {
                "height":"1000"
            },
            "webhook": <User Webhook API>,
            "id": <Unique ID>
        },
        "result": {
            "avgfee":0,
            "avgfeerate":0,
            "avgtxsize":0,
            "blockhash":"00000000c937983704a73af28acdec37b049d214adbda81d7e2a3dd146f6ed09",
            "feerate_percentiles":[0,0,0,0,0],
            "height":1000,
            "ins":0,
            "maxfee":0,
            "maxfeerate":0,
            "maxtxsize":0,
            "medianfee":0,
            "mediantime":1232344831,
            "mediantxsize":0,
            "minfee":0,
            "minfeerate":0,
            "mintxsize":0,
            "outs":1,
            "subsidy":5000000000,
            "swtotal_size":0,
            "swtotal_weight":0,
            "swtxs":0,
            "time":1232346882,
            "total_out":0,
            "total_size":0,
            "total_weight":0,
            "totalfee":0,
            "txs":1,
            "utxo_increase":1,
            "utxo_size_inc":117
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
Example JSON body::

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
        "payload":{ 
            "method":"getdifficulty",
            "parameter":{},
            "webhook": <User Webhook API>,
            "id": <Unique ID>
        },
        "result":14363025673659.96
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
Example JSON body::

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
        "payload": {
            "method":"getmemoryinfo",
            "parameter":{},
            "webhook": <User Webhook API>,
            "id": <Unique ID>
        },
        "result": {
            "locked": {
                "used":5134496,
                "free":108384,
                "total":5242880,
                "locked":5242880,
                "chunks_used":160451,
                "chunks_free":7
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
Example JSON body::

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
        "payload": {
            "method":"getrpcinfo",
            "parameter":{},
            "webhook": <User Webhook API>,
            "id": <Unique ID>
        },
        "result": {
            "active_commands":[{
                "method":"getrpcinfo",
                "duration":5
            }],
            "logpath":"/var/lib/bitcoind/debug.log"
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
Example JSON body::

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
        "payload": {
            "method":"help",
            "parameter":{},
            "webhook": <User Webhook API>,
            "Id": <Unique ID>
        },
        "result":"== Blockchain ==\ngetbestblockhash\ngetblock \"blockhash\" ( verbosity )\ngetblockchaininfo\ngetblockcount\ngetblockfilter \"blockhash\" ( \"filtertype\" )\ngetblockhash height\ngetblockheader \"blockhash\" ( verbose )\ngetblockstats hash_or_height ( stats )\ngetchaintips\ngetchaintxstats ( nblocks \"blockhash\" )\ngetdifficulty\ngetmempoolancestors \"txid\" ( verbose )\ngetmempooldescendants \"txid\" ( verbose )\ngetmempoolentry \"txid\"\ngetmempoolinfo\ngetrawmempool ( verbose )\ngettxout \"txid\" n ( include_mempool )\ngettxoutproof [\"txid\",...] ( \"blockhash\" )\ngettxoutsetinfo\npreciousblock \"blockhash\"\npruneblockchain height\nsavemempool\nscantxoutset \"action\" [scanobjects,...]\nverifychain ( checklevel nblocks )\nverifytxoutproof \"proof\"\n\n== Control ==\ngetmemoryinfo ( \"mode\" )\ngetrpcinfo\nhelp ( \"command\" )\nlogging ( [\"include_category\",...] [\"exclude_category\",...] )\nstop\nuptime\n\n== Generating ==\ngeneratetoaddress nblocks \"address\" ( maxtries )\n\n== Mining ==\ngetblocktemplate ( \"template_request\" )\ngetmininginfo\ngetnetworkhashps ( nblocks height )\nprioritisetransaction \"txid\" ( dummy ) fee_delta\nsubmitblock \"hexdata\" ( \"dummy\" )\nsubmitheader \"hexdata\"\n\n== Network ==\naddnode \"node\" \"command\"\nclearbanned\ndisconnectnode ( \"address\" nodeid )\ngetaddednodeinfo ( \"node\" )\ngetconnectioncount\ngetnettotals\ngetnetworkinfo\ngetnodeaddresses ( count )\ngetpeerinfo\nlistbanned\nping\nsetban \"subnet\" \"command\" ( bantime absolute )\nsetnetworkactive state\n\n== Rawtransactions ==\nanalyzepsbt \"psbt\"\ncombinepsbt [\"psbt\",...]\ncombinerawtransaction [\"hexstring\",...]\nconverttopsbt \"hexstring\" ( permitsigdata iswitness )\ncreatepsbt [{\"txid\":\"hex\",\"vout\":n,\"sequence\":n},...] [{\"address\":amount},{\"data\":\"hex\"},...] ( locktime replaceable )\ncreaterawtransaction [{\"txid\":\"hex\",\"vout\":n,\"sequence\":n},...] [{\"address\":amount},{\"data\":\"hex\"},...] ( locktime replaceable )\ndecodepsbt \"psbt\"\ndecoderawtransaction \"hexstring\" ( iswitness )\ndecodescript \"hexstring\"\nfinalizepsbt \"psbt\" ( extract )\nfundrawtransaction \"hexstring\" ( options iswitness )\ngetrawtransaction \"txid\" ( verbose \"blockhash\" )\njoinpsbts [\"psbt\",...]\nsendrawtransaction \"hexstring\" ( maxfeerate )\nsignrawtransactionwithkey \"hexstring\" [\"privatekey\",...] ( [{\"txid\":\"hex\",\"vout\":n,\"scriptPubKey\":\"hex\",\"redeemScript\":\"hex\",\"witnessScript\":\"hex\",\"amount\":amount},...] \"sighashtype\" )\ntestmempoolaccept [\"rawtx\",...] ( maxfeerate )\nutxoupdatepsbt \"psbt\" ( [\"\",{\"desc\":\"str\",\"range\":n or [n,n]},...] )\n\n== Util ==\ncreatemultisig nrequired [\"key\",...] ( \"address_type\" )\nderiveaddresses \"descriptor\" ( range )\nestimatesmartfee conf_target ( \"estimate_mode\" )\ngetdescriptorinfo \"descriptor\"\nsignmessagewithprivkey \"privkey\" \"message\"\nvalidateaddress \"address\"\nverifymessage \"address\" \"signature\" \"message\"\n\n== Wallet ==\nabandontransaction \"txid\"\nabortrescan\naddmultisigaddress nrequired [\"key\",...] ( \"label\" \"address_type\" )\nbackupwallet \"destination\"\nbumpfee \"txid\" ( options )\ncreatewallet \"wallet_name\" ( disable_private_keys blank \"passphrase\" avoid_reuse )\ndumpprivkey \"address\"\ndumpwallet \"filename\"\nencryptwallet \"passphrase\"\ngetaddressesbylabel \"label\"\ngetaddressinfo \"address\"\ngetbalance ( \"dummy\" minconf include_watchonly avoid_reuse )\ngetbalances\ngetnewaddress ( \"label\" \"address_type\" )\ngetrawchangeaddress ( \"address_type\" )\ngetreceivedbyaddress \"address\" ( minconf )\ngetreceivedbylabel \"label\" ( minconf )\ngettransaction \"txid\" ( include_watchonly verbose )\ngetunconfirmedbalance\ngetwalletinfo\nimportaddress \"address\" ( \"label\" rescan p2sh )\nimportmulti \"requests\" ( \"options\" )\nimportprivkey \"privkey\" ( \"label\" rescan )\nimportprunedfunds \"rawtransaction\" \"txoutproof\"\nimportpubkey \"pubkey\" ( \"label\" rescan )\nimportwallet \"filename\"\nkeypoolrefill ( newsize )\nlistaddressgroupings\nlistlabels ( \"purpose\" )\nlistlockunspent\nlistreceivedbyaddress ( minconf include_empty include_watchonly \"address_filter\" )\nlistreceivedbylabel ( minconf include_empty include_watchonly )\nlistsinceblock ( \"blockhash\" target_confirmations include_watchonly include_removed )\nlisttransactions ( \"label\" count skip include_watchonly )\nlistunspent ( minconf maxconf [\"address\",...] include_unsafe query_options )\nlistwalletdir\nlistwallets\nloadwallet \"filename\"\nlockunspent unlock ( [{\"txid\":\"hex\",\"vout\":n},...] )\nremoveprunedfunds \"txid\"\nrescanblockchain ( start_height stop_height )\nsendmany \"\" {\"address\":amount} ( minconf \"comment\" [\"address\",...] replaceable conf_target \"estimate_mode\" )\nsendtoaddress \"address\" amount ( \"comment\" \"comment_to\" subtractfeefromamount replaceable conf_target \"estimate_mode\" avoid_reuse )\nsethdseed ( newkeypool \"seed\" )\nsetlabel \"address\" \"label\"\nsettxfee amount\nsetwalletflag \"flag\" ( value )\nsignmessage \"address\" \"message\"\nsignrawtransactionwithwallet \"hexstring\" ( [{\"txid\":\"hex\",\"vout\":n,\"scriptPubKey\":\"hex\",\"redeemScript\":\"hex\",\"witnessScript\":\"hex\",\"amount\":amount},...] \"sighashtype\" )\nunloadwallet ( \"wallet_name\" )\nwalletcreatefundedpsbt [{\"txid\":\"hex\",\"vout\":n,\"sequence\":n},...] [{\"address\":amount},{\"data\":\"hex\"},...] ( locktime options bip32derivs )\nwalletlock\nwalletpassphrase \"passphrase\" timeout\nwalletpassphrasechange \"oldpassphrase\" \"newpassphrase\"\nwalletprocesspsbt \"psbt\" ( sign \"sighashtype\" bip32derivs )\n\n== Zmq ==\ngetzmqnotifications"
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
Example JSON body::

    {
        "version": 2,
        "blockchain": "BTC",
        "payload": {
            "method": "uptime",
            "parameter":{},
            "webhook": <User Webhook API>,
            "id": <Unique ID>
        }
    }

Response
--------
Results::

    {
        "payload": {
            "method":"uptime",
            "parameter":{},
            "webhook": <User Webhook API>,
            "id": <Unique ID>
        },
        "result":135936
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
Example JSON body::

    {
        "version": 2,
        "blockchain": "BTC",
        "payload": {
            "method": "getconnectioncount",
            "parameter":{},
            "webhook": <User Webhook API>,
            "id": <Unique ID>
        }
    }

Response
--------
Results::

    {
        "payload": {
            "method":"getconnectioncount",
            "parameter":{},
            "webhook": <User Webhook API>,
            "id": <Unique ID>
        },
        "result":10
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
Example JSON body::

    {
        "version": 2,
        "blockchain": "BTC",
        "payload": {
            "method": "getnettotals",
            "parameter":{},
            "webhook": <User Webhook API>,
            "id": <Unique ID>
        }
    }

Response
--------
Results::

    {
        "payload": {
            "method":"getnettotals",
            "parameter":{},
            "webhook": <User Webhook API>,
            "id": <Unique ID>
        },
        "result": {
            "totalbytesrecv":324889728,
            "totalbytessent":559231498,
            "timemillis":1625862465986,
            "uploadtarget":{"timeframe":86400,"target":0,"target_reached":false,"serve_historical_blocks":true,"bytes_left_in_cycle":0,"time_left_in_cycle":0}
        }
    }

------------------------------------------------------------------------------

getnetworkinfo
========

Returns an object containing various state info regarding P2P networking.

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
        "blockchain":"BTC",
        "payload": {
            "method": "getnetworkinfo",
            "parameter": {},
            "webhook": <User Webhook API>,
            "id": <Unique ID>
        }
    }

Response
--------
Results::

    {
        "payload": {
            "method": "getnetworkinfo",
            "parameter": {},
            "webhook": <User Webhook API>,
            "id": <Unique ID>
        },
        "result": {
        "version": 190001,
        "subversion": "/Satoshi:0.19.0.1/",
        "protocolversion": 70015,
        "localservices": "0000000000000409",
        ...
    }

------------------------------------------------------------------------------

getpeerinfo
========

Returns data about each connected network node as a json array of objects.

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
        "blockchain":"BTC",
        "payload": {
            "method": "getpeerinfo",
            "parameter": {},
            "webhook": <User Webhook API>,
            "id": <Unique ID>
        }
    }

Response
--------
Results::

    {
        "payload": {
            "method": "getpeerinfo",
            "parameter": {},
            "webhook": "https://webhook.site/44275a9d-feac-4d26-9431-8d313da43490",
            "id": "0026"
        },
        "result": [
            {
                "id": 0,
                "addr": "18.167.92.1:8333",
                "addrlocal": "13.250.189.186:5361",
                "addrbind": "20.8.1.33:55754",
                "services": "0000000000000409",
                ...
            }, {...},
        ] 
    }

------------------------------------------------------------------------------

listbanned
========

List all banned IPs/Subnets.

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
        "blockchain":"BTC",
        "payload": {
            "method": "listbanned",
            "parameter": {},
            "webhook": <User Webhook API>,
            "id": <Unique ID>
        }
    }

Response
--------
Results::

    {
        "payload": {
            "method":"listbanned",
            "parameter":{},
            "webhook": <User Webhook API>,
            "id": <Unique ID>
        },
        "result":[]
    }

------------------------------------------------------------------------------

ping
========

Requests that a ping be sent to all other nodes, to measure ping time.

Results provided in getpeerinfo, pingtime and pingwait fields are decimal seconds.

Ping command is handled in queue with all other commands, so it measures processing backlog, not just network ping.

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
        "blockchain":"BTC",
        "payload": {
            "method": "ping",
            "parameter": {},
            "webhook": <User Webhook API>,
            "id": <Unique ID>
        }
    }

Response
--------
Returns ping status::

    {
        "payload": {
            "method":"ping",
            "parameter":{},
            "webhook": <User Webhook API>,
            "id": <Unique ID>
        },
        "result":"Operation completed succcessfully"
    }

------------------------------------------------------------------------------

getutxobyaddress
========

Returns list of unspent transaction from an bitcoin address.

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
Example JSON body::
    
    {
        "version": 2,
        "blockchain":"BTC",
        "payload": {
            "method": "getutxobyaddress",
            "parameter": {
                "address": "12dRugNcdxK39288NjcDV4GX7rMsKCGn6B"
            },
            "webhook": <User Webhook API>,
            "id": <Unique ID>
        }
    }

Response
--------
Returns the list of utxo address::

    {
        "payload": {
            "method": "getutxobyaddress",
            "parameter": {
                "address": "12dRugNcdxK39288NjcDV4GX7rMsKCGn6B"
            },
            "webhook": <User Webhook API>,
            "id": <Unique ID>
        },
        "result": [{
            "_id": "60e871260a44a1f4e6808357",
            "chain": "BTC",
            "network": "mainnet",
            "coinbase": true,
            "mintIndex": 0,
            "spentTxid": "",
            "mintTxid": "26510f0e64f3c99835624b5c90f9d1f0145cc17a285cbcf45db54417122f4df2",
            "mintHeight": 690305,
            "spentHeight": -2,
            "address": "12dRugNcdxK39288NjcDV4GX7rMsKCGn6B",
            "script": "76a91411dbe48cc6b617f9c6adaf4d9ed5f625b1c7cb5988ac",
            "value": 653485577,
            "confirmations": -1
        }, {...}, ...,
        ]
    }

------------------------------------------------------------------------------

getbalancebyaddress
========

Returns the total available balance in specific address.


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
                "address": "12dRugNcdxK39288NjcDV4GX7rMsKCGn6B"
                } 

Example
--------
Example JSON body::

    {
        "version": 2,
        "blockchain": "BTC",
        "payload": {
            "method": "getbalancebyaddress",
            "parameter": {
                "address": "12dRugNcdxK39288NjcDV4GX7rMsKCGn6B"
            },
            "webhook": <User Webhook API>,
            "id": <Unique ID>
        }
    }
  
Response
--------
Results::

    {
        "payload": {
            "method":"getbalancebyaddress",
            "parameter":{
                "address":"12dRugNcdxK39288NjcDV4GX7rMsKCGn6B"
            },
            "webhook": <User Webhook API>,
            "id": <Unique ID>
        },
        "result":{
            "confirmed":40602170638,
            "unconfirmed":0,
            "balance":40602170638
        }
    }

------------------------------------------------------------------------------

gettransactionbytxid
========

Returns transaction details from transaction id.

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
Example JSON body::
    
    {
        "version": 2,
        "blockchain": "BTC",
        "payload": {
            "method": "gettransactionbytxid",
            "parameter": {
                "txid": "f431af00064eec358cdde7bbffd6c298131e52af01513c283d507682bdfed0dd"
            },
            "webhook": <User Webhook API>,
            "id": <Unique ID>
        }
    }

Response
--------
Results::

    {
        "payload": {
            "method":"gettransactionbytxid",
            "parameter": {
                "txid":"f431af00064eec358cdde7bbffd6c298131e52af01513c283d507682bdfed0dd"
            },
            "webhook": <User Webhook API>,
            "id": <Unique ID>
        },
        "result":{
            "_id":"60b878920a44a1f4e6ec3cd2",
            "txid":"f431af00064eec358cdde7bbffd6c298131e52af01513c283d507682bdfed0dd",
            "network":"mainnet",
            "chain":"BTC",
            "blockHeight":686067,
            "blockHash":"00000000000000000003f1e52a5668af5848edc209707ec42fbe9d43aa3033c4",
            "blockTime":"2021-06-03T06:36:39.000Z",
            "blockTimeNormalized":"2021-06-03T06:36:39.000Z",
            "coinbase":true,
            "locktime":-1,
            "inputCount":1,
            "outputCount":4,
            "size":315,
            "fee":-1,
            "value":688023701,
            "confirmations":4265
        }
    }

------------------------------------------------------------------------------

gettransactionbyaddress
========

Get detailed information about in-wallet transaction <txid>.

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
Example JSON body::

    {
        "version": 2,
        "blockchain":"BTC",
        "payload": {
            "method": "gettransactionbyaddress",
            "parameter": {
              "address": "12dRugNcdxK39288NjcDV4GX7rMsKCGn6B"
            },
            "webhook": <User Webhook API>,
            "id": <Unique ID>
        }
    }


Response
--------
Results::

    {
        "payload": {
        "method": "gettransactionbyaddress",
        "parameter": {
            "address": "12dRugNcdxK39288NjcDV4GX7rMsKCGn6B"
        },
        "webhook": <User Webhook API>,
        "id": <Unique ID>
        },
        "result": [{
            "_id": "60e8bcd80a44a1f4e6ab7c9b",
            "chain": "BTC",
            "network": "mainnet",
            "coinbase": true,
            "mintIndex": 0,
            "spentTxid": "",
            "mintTxid": "165fc69135d570b42ce12f90ec3f214d7c7ab2fcae759393987c8855adcca310",
            "mintHeight": 690332,
            "spentHeight": -2,
            "address": "12dRugNcdxK39288NjcDV4GX7rMsKCGn6B",
            "script": "76a91411dbe48cc6b617f9c6adaf4d9ed5f625b1c7cb5988ac",
            "value": 662575003,
            "confirmations": -1
        }, ..., {...}
        ]
    }

------------------------------------------------------------------------------

getrawtransaction
========

Get raw transaction from transaction hash.

Headers
--------
Need to set headers::

    Key             Value

    Content-Type    application/json

    Authorization   OBC eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYW1lIjoib2JjIiwiaWF0IjoxNjAzMTU3NjMzLCJleHAiOjE2MDM3NjI0MzN9.71my1T-2IxQNJhNNu-aRX7N3TLo9BqAczyGWX1ph2vA

Parameters
--------
Parameters::

    txid     transaction hash of a transaction
                {
                "txid": "f431af00064eec358cdde7bbffd6c298131e52af01513c283d507682bdfed0dd"
                }

Example
--------
Example JSON body::

    {
        "version": 2,
        "blockchain":"BTC",
        "payload": {
            "method": "getrawtransaction",
            "parameter": {
                "txid": "f431af00064eec358cdde7bbffd6c298131e52af01513c283d507682bdfed0dd"
            },
            "webhook": <User Webhook API>,
            "id": <Unique ID>
        }
    }


Response
--------
Results::

    {
        "payload": {
            "method": "getrawtransaction",
            "parameter": {
                "txid": "f431af00064eec358cdde7bbffd6c298131e52af01513c283d507682bdfed0dd"
            },
            "webhook": <User Webhook API>,
            "id": <Unique ID>
        },
        "result": {
            "code": 200,
            "data": {
                "txid": "f431af00064eec358cdde7bbffd6c298131e52af01513c283d507682bdfed0dd",
                "hash": "6a87bd8ad52ff49aa2aec9f6af695997ce113ae6ad008815de0bd6b247d25d5b",
                "version": 1,
                "size": 351,
                "vsize": 324,
                "weight": 1296,
                "locktime": 0,
                "vin": [
                    {
                        "coinbase": "03f3770a1b4d696e656420627920416e74506f6f6c373432700083017ad1aa0ffabe6d6d81659b3453e3f876d9a324c3ca767a5e0fa806214a077f302b6c7b5dffafd2b40200000000000000c6440000b9990100",
                        "sequence": 4294967295
                    }
                ],
                ...,
            }
        }
    }

------------------------------------------------------------------------------

createrawtransaction
====================

Create raw transaction for bitcoin transaction.

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
Example JSON body::

    {
        "version": 2,
        "blockchain": "BTC",
        "payload": {
            "method": "createrawtransaction",
            "parameter": {
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
            },
            "webhook": <User Webhook API>,
            "id": <Unique ID>
        }
    }

Response
--------
Returns the transaction hash::

    {
        "payload": {
            "method": "createrawtransaction",
            "parameter": {
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
            },
            "webhook": <User Webhook API>,
            "id": <Unique ID>
        },
        "result": {
            "code": 200,
            "data": "0100000001e34ac1e2baac09c366fce1c2245536bda8f7db0f6685862aecf53ebd69f9a89c0000000000ffffffff02a0252600000000001976a914d90d36e98f62968d2bc9bbd68107564a156a9bcf88ac50622500000000001976a91407bdb518fa2e6089fd810235cf1100c9c13d1fd288ac00000000"
        }
    }

------------------------------------------------------------------------------

sendrawtransaction
========

Send raw bitcoin transaction. 

Headers
--------
Need to set headers::

    Key             Value

    Content-Type    application/json

    Authorization   OBC eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYW1lIjoib2JjIiwiaWF0IjoxNjAzMTU3NjMzLCJleHAiOjE2MDM3NjI0MzN9.71my1T-2IxQNJhNNu-aRX7N3TLo9BqAczyGWX1ph2vA

Parameters
--------
Need parameters::

    hexstring     Hexstring created from raw bitcoin transaction
               {
          "hexstring": "0200000001669576892eb617435059fb6c5976e8bf526149c0f09ce7dcdc4af0ed995b10390000000000ffffffff0150c300000000000017a914f0a454d03ca355e47b13fbdd497d258a0b365b0a8700000000"
                    } 

Example
--------
Example JSON body::

    {
        "version": 2,
        "blockchain": "BTC",
        "payload": {
            "method": "createrawtransaction",
            "parameter": {
               "hexstring": "0200000001669576892eb617435059fb6c5976e8bf526149c0f09ce7dcdc4af0ed995b10390000000000ffffffff0150c300000000000017a914f0a454d03ca355e47b13fbdd497d258a0b365b0a8700000000"
            },
            "webhook": <User Webhook API>,
            "id": <Unique ID>
        }
    }

Response
--------
Returns the txid for sendrawtransaction::

    {
        "payload": {
            "method": "createrawtransaction",
            "parameter": {
               "hexstring": "0200000001669576892eb617435059fb6c5976e8bf526149c0f09ce7dcdc4af0ed995b10390000000000ffffffff0150c300000000000017a914f0a454d03ca355e47b13fbdd497d258a0b365b0a8700000000"
            },
            "webhook": <User Webhook API>,
            "id": <Unique ID>
        },
        "result": {
            "code": 200,
            "data": "39105b99edf04adcdce79cf0c0496152bfe876596cfb59504317b62e89769566"
        }
    }