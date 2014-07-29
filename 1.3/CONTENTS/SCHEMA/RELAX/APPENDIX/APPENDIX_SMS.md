[Back to the Table of Contents](/1.3/README.md)

## APPENDIX SMS

__SMS Protocol Reference__

| Protocol | Status | Success | Notification Information |
| -------- | ------ | ------- | ------------------------ |
| 1 | 92100 | no | No Route |
| 1 | 92101 | no | No Credits |
| 1 | 92102 | no | Overspending |
| 1 | 92110 | no | No ProgramID |
| 1 | 92111 | no | TMobile Missing RefID |
| 2 | 0 | yes | Message sent |
| 2 | 1 | yes | Processing request |
| 2 | 2 | yes | Message queued |
| 2 | 3 | yes | Message buffered with carrier and waiting for delivery response |
| 2 | 4 | yes | Message delivered |
| 2 | 5 | yes | Message transferred to carrier and waiting for buffered response |
| 2 | 301 | no | Only one top level request element is permitted |
| 2 | 303 | no | The required version attribute of the request element was not found in the request |
| 2 | 304 | no | The required protocol attribute of the request element was not found in the request |
| 2 | 306 | no | The XML POST parameter cannot be empty |
| 2 | 307 | no | The request was an ill-formed XML document |
| 2 | 310 | no | If the force option is going to be set, it can only be set to one or zero |
| 2 | 311 | no | Method option is no longer used |
| 2 | 321 | no | Invalid request version |
| 2 | 322 | no | Invalid request protocol |
| 2 | 323 | no | Invalid request type |
| 2 | 330 | no | Invalid number of page elements |
| 2 | 331 | no | Client not found |
| 2 | 337 | no | Invalid carrier ID value |
| 2 | 338 | no | Message Service Id and destination carrier attributes cannot be used at same time |
| 2 | 339 | no | Invalid destination carrier ID value |
| 2 | 340 | no | Invalid source carrier ID value |
| 2 | 341 | no | Transaction failed; Carrier ID does not exist |
| 2 | 342 | no | A message service ID is required |
| 2 | 343 | no | The message service ID is discontinued |
| 2 | 344 | no | The message service ID is beta |
| 2 | 345 | no | Unable to determine carrier ID from destination address |
| 2 | 349 | no | Destination address contains non-numeric characters |
| 2 | 350 | no | A destination address is required |
| 2 | 351 | no | Transaction failed: Invalid destination address value |
| 2 | 352 | no | Invalid destination address country code |
| 2 | 353 | no | Message text or data is required |
| 2 | 354 | no | Message text is not long enough |
| 2 | 355 | no | Message text is too long |
| 2 | 356 | no | Message from is required |
| 2 | 357 | no | Message from is not long enough |
| 2 | 358 | no | Message from is too long |
| 2 | 359 | no | Message callback is required |
| 2 | 360 | no | Message callback is not long enough |
| 2 | 361 | no | Message callback is too long |
| 2 | 362 | no | Message callback contains non-numeric characters |
| 2 | 363 | no | Invalid callback number used |
| 2 | 364 | no | Callback and destination address cannot be identical |
| 2 | 365 | no | Strict international addressing is enforced, please use a + sign, country code, and national number |
| 2 | 366 | no | Invalid message length control option |
| 2 | 367 | no | Invalid source TON value |
| 2 | 368 | no | Invalid source address value |
| 2 | 369 | no | Account not permitted to use an alphanumeric source address |
| 2 | 370 | no | Account not permitted to use a short code source address |
| 2 | 371 | no | Callback attribute and source element cannot be used at same time |
| 2 | 372 | no | Pin attribute and destination element cannot be used at same time |
| 2 | 373 | no | Invalid destination TON value |
| 2 | 374 | no | Preview lookup request failed |
| 2 | 375 | no | Source address denied |
| 2 | 376 | no | Account not permitted to use premium billing options |
| 2 | 377 | no | Invalid premium billing charge type |
| 2 | 378 | no | Invalid premium billing charge amount |
| 2 | 379 | no | Invalid user data header |
| 2 | 380 | no | Invalid data coding scheme |
| 2 | 381 | no | Invalid characters used with selected data coding scheme |
| 2 | 382 | no | Invalid source or destination port |
| 2 | 383 | no | Message data and text attributes cannot be used at same time |
| 2 | 384 | no | Invalid message data |
| 2 | 385 | no | Invalid or unsupported ringtone format |
| 2 | 386 | no | Invalid or unsupported image format |
| 2 | 387 | no | Must provide a valid phone type to send images or ringtones |
| 2 | 388 | no | Binary messaging is not supported for this carrier |
| 2 | 389 | no | A valid image type must be specified |
| 2 | 390 | no | Must provide a numeric country and network code |
| 2 | 391 | no | Must provide ringtone data |
| 2 | 392 | no | Must provide image data |
| 2 | 393 | no | Must provide at least a screen saver or a ringtone to send a profile |
| 2 | 394 | no | Invalid option type for the phone specified |
| 2 | 395 | no | Must provide a country code and a network code to send a logo |
| 2 | 396 | no | Smart messages cannot use more than 3 messages to transfer |
| 2 | 397 | no | WAP Pushes require the optional URL parameter to be included |
| 2 | 398 | no | WAP Pushes not supported for this type of carrier |
| 2 | 399 | no | Binary data with a User Data Header is not allowed for your account |
| 2 | 400 | no | General error occurred while delivering the message to the carrier |
| 2 | 401 | no | General error occurred while delivering the message to the carrier |
| 2 | 410 | no | Message recipient not found on carrier |
| 2 | 411 | no | Message recipient not found on carrier |
| 2 | 420 | no | Invalid subscriber ID or subscriber password |
| 2 | 430 | no | Demo or commercial access is required |
| 2 | 431 | no | Invalid Subscriber ID |
| 2 | 432 | no | Account access permanently blocked |
| 2 | 433 | no | Account access denied |
| 2 | 434 | no | Account access has expired |
| 2 | 451 | no | Account mobile originated deliver profile incorrectly setup |
| 2 | 460 | no | Account entry not found in billing database |
| 2 | 461 | no | Must include source address if premium billing requested |
| 2 | 507 | no | Carrier facility not supported |
| 2 | 508 | no | Carrier absent subscriber |
| 2 | 509 | no | Carrier delivery failed |
| 2 | 510 | no | Carrier protocol error |
| 2 | 511 | no | Carrier MS not equipped |
| 2 | 512 | no | Carrier unknown SC |
| 2 | 513 | no | Carrier illegal MS |
| 2 | 514 | no | Carrier MS not a subscriber |
| 2 | 560 | no | Message recipient not authorized by carrier to receive the message |
| 2 | 561 | no | Content blocked by carrier |
| 2 | 562 | no | Short code not active |
| 2 | 563 | no | Short code expired |
| 2 | 564 | no | Short code blocked |
| 2 | 565 | no | Reseller address blocked by carrier |
| 2 | 566 | no | Destination address blocked by carrier |
| 2 | 568 | no | Destination address not provisioned for SMS |
| 2 | 569 | no | Destination address suspended by carrier |
| 2 | 570 | no | Invalid charge amount: charge amount not allowed for charge type |
| 2 | 571 | no | Campaign rejected by carrier |
| 2 | 572 | no | Campaign information is not provisioned for this carrier or is not active |
| 2 | 800 | no | Invalid number of service elements in request |
| 2 | 801 | no | General error while retrieving the service list |
| 2 | 802 | no | Service ID is required |
| 2 | 803 | no | Invalid service ID since it was null |
| 2 | 810 | no | Failed message delivery |
| 2 | 811 | no | Message Delivery Error: Message expired by carrier |
| 2 | 815 | no | Message Delivery Error - Message submitted to but not acknowledged by carrier |
| 2 | 1000 | no | System error: General error occurred while processing request |
| 2 | 1001 | no | System error: Duplicate Ticket ID |
| 2 | 1010 | no | Temporary system error |
| 2 | 1020 | no | Temporary external system error |
| 2 | 1030 | no | External system error |
| 2 | 2001 | no | Invalid subscription authentication |
| 2 | 2002 | no | Subscriber/account ID has been de-activated |
| 2 | 2003 | no | Subscriber/account ID has been deleted |
| 2 | 2010 | no | General billing error |
| 2 | 2011 | no | Transaction failed: Message delivery expired, no charge was made |
| 2 | 2012 | no | Transaction failed: Consumer cancelled the transaction |
| 2 | 2013 | no | Message still in process |
| 2 | 2014 | no | Transaction failed: Wireless subscriber is ineligible for billing on carrier |
| 2 | 2015 | no | Transaction failed: Wireless subscriber's account is deactivated |
| 2 | 2016 | no | Unspecified error |
| 2 | 2017 | no | Message has been deleted by carrier |
| 2 | 2018 | no | Subscriber payment method is invalid |
| 2 | 2019 | no | Undeliverable to user |
| 2 | 2020 | no | Transaction failed: Wireless subscriber over spending limit |
| 2 | 2021 | no | Service not available for user |
| 2 | 2022 | no | Transaction failed: Wireless subscriber not eligible for premium billing: Subscriber setting |
| 2 | 2023 | no | User not found on carrier network |
| 2 | 2024 | no | Transaction failed: Wireless subscriber's account closed, suspended or locked. |
| 2 | 2025 | no | Transaction failed: Carrier does not support premium billing with the supplied short code |
| 2 | 2026 | no | Transaction failed: Ineligible product |
| 2 | 2027 | no | Transaction failed: Wireless network operator temporary system error |
| 2 | 2028 | no | Wireless subscriber has run out of prepaid credits |
| 2 | 2029 | no | Wireless subscriber not eligible for premium billing: blocked MDN |
| 2 | 2030 | no | Transaction failed: Wireless subscriber not eligible for premium billing: Reseller |
| 2 | 2031 | no | Short code is currently in test mode, only whitelisted handsets are permitted |
| 2 | 2032 | no | Short code is not certified on carrier |
| 2 | 2033 | no | Short code not permitted for this carrier |
| 2 | 2034 | no | Short code and price point combination is not allowed for this carrier |
| 2 | 2035 | no | Transaction failed: Wireless subscriber not found |
| 2 | 2036 | no | Tax failed on transaction |
| 2 | 2037 | no | Transaction failed: Does not meet minimum charge amount |
| 2 | 2038 | no | Transaction failed: Amount exceeds specified maximum |
| 2 | 2039 | no | Advice-of-Charge Timed Out |
| 2 | 2040 | no | Transaction failed: Charge duration exceeded |
| 2 | 2041 | no | Transaction failed: Unable to process request; previous billing request still being processed; Advice-of-Charge re-sent |
| 2 | 2042 | no | Refund denied: Transaction already refunded |
| 2 | 2043 | no | Request Failed: No transaction found matching provided data |
| 2 | 2044 | no | Invalid URL |
| 2 | 2045 | no | Carrier not supported |
| 2 | 2046 | no | Invalid sessionId |
| 2 | 2047 | no | Invalid ticketid |
| 2 | 2048 | no | Validation Error |
| 2 | 2049 | no | Transaction failed: Request with no associated charge; failed by OpenMarket |
| 2 | 2050 | no | Transaction failed: The transaction has been denied by the carrier's billing system |
| 2 | 2051 | no | Supplied ticketId is either in a processed state or failed state |
| 2 | 2052 | no | Transaction failed: Campaign information is not provisioned for this carrier or is not active |
| 2 | 2053 | no | Transaction failed: Advice of charge message exceeded maximum length |
| 2 | 2054 | no | Transaction failed:Wireless subscriber?s account closed |
| 2 | 2056 | no | Transaction failed: Campaign rejected by carrier |
| 2 | 2100 | no | Invalid request - &lt;request parameter&gt; is missing |
| 2 | 2101 | no | Account is not authorized |
| 2 | 2102 | no | Account is not authorized to use short code |
| 2 | 2104 | no | Transaction failed: Refund cannot be processed against a failed charge |
| 2 | 2120 | no | Account does not have permission to refund the charge |
| 2 | 2121 | no | Refund cannot exceed the original transaction amount |
| 2 | 2122 | no | ProgramId is a required field for this carrier |
| 2 | 2123 | no | The carrier does not support refunds to be processed |
| 2 | 2124 | no | The carrier does not support partial refunds |
| 2 | 2125 | no | Refund cannot be processed as it exceeds the allowable time period since the charge |
| 2 | 2126 | no | Carrier information cannot be found from the WAP header |
| 2 | 3041 | no | Standard rate message blocked by the OpenMarket deactivated numbers firewall |
| 2 | 3042 | no | Premium rate message blocked by the OpenMarket deactivated numbers firewall |
| 2 | 4000 | no | Transaction failed: Merchant account not permitted to use the subscription service |
| 2 | 4001 | no | Short code is not provisioned to use the subscription service for this carrier |
| 2 | 4010 | no | Transaction failed: Subscription already exists |
| 2 | 4011 | no | Transaction failed: Unable to process request; previous billing request still being processed |
| 2 | 4012 | no | Transaction failed: Subscription already exists on carrier; possible phone number change |
| 2 | 4013 | no | Transaction failed: Unable to process request; previous billing request is pending consumer response |
| 2 | 4020 | no | Transaction failed: Subscription not found |
| 2 | 4021 | no | Transaction failed: Subscription already expired |
| 2 | 4030 | no | Renewal error: subscription already billed for this period |
| 2 | 4031 | no | Renewal error: Subscription renewal status cannot be determined |
| 2 | 4032 | no | Renewal error: Subscription already expired |
| 2 | 4033 | no | Subscription successfully cancelled, message delivery failed. |
| 2 | 4035 | no | Renewal Error: Subscription renewal failed by carrier |
| 2 | 4050 | no | Conclude error: subscription already concluded. |
| 2 | 4051 | no | Conclude error: Subscription cannot be concluded while in indeterminate state. |
| 2 | 4052 | no | Transaction failed: Received notification of account deactivation; failed by OpenMarket |
| 2 | 4054 | no | Renewal error: Subscription already revoked |
| 2 | 4055 | no | Conclude error: Subscription cannot be concluded while a renewal is pending |
| 3 | 1 | yes | Delivery success |
| 3 | 2 | no | Delivery failure |
| 3 | 4 | yes | msg buffered |
| 3 | 8 | yes | smsc submit |
| 3 | 16 | no | smsc reject (error) |
| 4 | 0 | yes | Successfully executed |
| 4 | 1 | no | Invalid login or unauthorized API usage |
| 4 | 2 | no | Consumer is blocked by IPX |
| 4 | 3 | no | Operation is not provisioned by IPX |
| 4 | 4 | no | The consumer is unknown to IPX |
| 4 | 5 | no | Consumer has blocked this service in IPX |
| 4 | 6 | no | The originating address is not supported |
| 4 | 7 | no | Alpha originating address not supported by account |
| 4 | 8 | no | MSISDN originating address not supported by account |
| 4 | 9 | no | GSM extended not supported by account |
| 4 | 10 | no | Unicode not supported by account |
| 4 | 11 | no | Status report not supported by account |
| 4 | 12 | no | Required capability not supported |
| 4 | 13 | no | Could not route message |
| 4 | 14 | no | The content provider max throttling rate is exceeded |
| 4 | 15 | no | The account max throttling rate is exceeded |
| 4 | 16 | no | Protocol ID not supported by account |
| 4 | 50 | no | Partial success: (&lt;1&gt;;&lt;2&gt;;&lt;n&gt;) |
| 4 | 99 | no | Internal server error |
| 4 | 100 | no | Invalid destination address |
| 4 | 101 | no | Invalid tariff class (price) |
| 4 | 102 | no | Invalid referenced (linked) ID |
| 4 | 103 | no | Invalid account name |
| 4 | 104 | no | Invalid content category |
| 4 | 105 | no | Invalid content meta data |
| 4 | 106 | no | Invalid originating address |
| 4 | 107 | no | Invalid alphanumeric originating address |
| 4 | 108 | no | Invalid validity time |
| 4 | 109 | no | Invalid delivery time |
| 4 | 110 | no | Invalid message content/user data |
| 4 | 111 | no | Invalid message length |
| 4 | 112 | no | Invalid user data header |
| 4 | 113 | no | Invalid data coding scheme |
| 4 | 114 | no | Invalid protocol ID |
| 4 | 115 | no | Invalid status report flags |
| 4 | 116 | no | Invalid TON |
| 4 | 117 | no | Invalid VAT |
| 4 | 200 | no | Operator integration error |
| 4 | 201 | no | Communication problems |
| 4 | 202 | no | Read timeout |
| 4 | 299 | no | Integration error |
