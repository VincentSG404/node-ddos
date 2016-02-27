This is pretty rough, read the source. It's a fork of
 https://github.com/rook2pawn/node-ddos

 with a few essential improvements


Let's review Configuration
==========================

Let's go over the configuration options to help illustrate how this module works.
All of the configurations default to the following:

    _params.maxcount = 30;
    _params.burst = 5;
    _params.limit = _params.burst * 4;  
    _params.maxexpiry = 120;
    _params.checkinterval = 1;
    _params.errormessage = 'Error';
    _params.testmode = false;
    _params.silent = false;
    _params.silentStart = false;
    _params.responseStatus = 429;


params.limit 
------------

limit is the number of maximum counts allowed.
If the count exceeds the limit, then the request is denied.
Recommended limit is to use a multiple of the number of bursts.


params.burst
------------

Burst is the number or amount of allowable burst requests before the client starts being penalized.
When the client is penalized, the expiration is increased by twice the previous expiration.


params.maxexpiry
----------------

maxexpiry is the seconds of maximum amount of expiration time. 
In order for the user to use whatever service you are providing again, they have to wait through the expiration time.


params.checkinterval
--------------------

checkinterval is the seconds between updating the internal table. 

params.errormessage
-------------------

When a request is denied, the user receives a 429 and the error message.

params.responseStatus
-------------------

By default HTTP status code 429 (Too Many Requests) are sent in response.



TODO
====

Looking for a more advanced Koa test!



Contribute
==========

Contributions welcome!
