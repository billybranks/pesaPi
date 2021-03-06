PesaPI
=======
PesaPI is an unofficial open source API for mobile money systems, released under the BSD(lite) license.  
The system currently support:
* Mpesa paybill numbers
* Mpesa private numbers

The API supports both PUSH and PULL versions.
The PHP version of the API is generally the most mature and recomended at this point - the system is build using Mysql and Curl.


Current status
--------------
The current system should be considered as beta version - at least one commercial solution is using it as its payment gateway.
However it is not recomended that you deploy the system without having a developer available to support the setup.

Version 0.1.0 was recently released and is contains a major rework of the internal structures of PesaPi - be alert that things that worked previously may not be fully working yet - as detailed testing is ongoing.

Currently we are looking for people to provide copies of the SMS messages they are getting from various payment systems.


System design overview
----------------------
* Supports both push and pull notifications.
* Does synchroization between local and server database.
* Transaction data are available even when main server is down.
* Super easy to utilize for integrators.
* Fast response on historical data.
* Keep the load on servers as low as possible.
* Hopefully more reliable than other APIs.


API Overview
------------
The PesaPi class contains several static methods, these methods are the main interface.

* availableBalance(time) -- returns the balance at a given point in time
* locateByReceipt(receipt) -- returns a payment or null for the given receipt number
* locateByPhone(phone, from, until) -- returns an array of payments from a particular phone
* locateByName(name, from, until) -- returns an array of payments from a particular client name
* locateByAccount(account, from, until) -- returns an array of payments from a particular account-no
* locateByTimeInterval(from, until) -- returns an array of all payments within a given time interval 

As an alternative you can ask PesaPi to call a your on your site when a new transaction is received (push mechanics).


Way forward
-----------
The following is a highlevel "todo" list for the project

* Getting the code to release/production quality.
* Getting more developers onboard.
* Add support for more payment systems.

