[Back to the Table of Contents](/1.3/README.md)&nbsp;&nbsp;|&nbsp;&nbsp;[Postback System Overview](/1.3/CONTENTS/POSTBACKS/POSTBACK_SYSTEM_OVERVIEW.md)
## SMS/MMS MT Postbacks

The MMS MT / SMS MT Postback API notifies you of the delivery status of each message you send.  For MMS, we have two methods for delivering content; Binary and xHTML. We send different postback notification formats depending on which method is used.

__SMS MT/MMS MT Postback Types:__

[SMS Delivery Status](#SMSStatus)                        
[MMS Delivery Status](#MMSStatus)                       
[SaveMMS Encoding Status](#SaveMMSStatus)

__Schema:__

https://www.skycore.com/platform/schema/postback.xsd


### [SMS MT Delivery Status](SMSStatus)

Postback notification when an SMS is sent to the mobile network operator.

| Variable | Description |
| -------- | ----------- |
| ORIGIN | SMS_MT means an SMS terminated on a mobile. |
| CODE | Code 201 means the SMS was submitted to the carrier. |
| STATUS | Whether the message was forwarded successfully - "Message Sent" or "Message Failed". Whether the message was delivered successfully - "Message Sent/Delivered" or "Message Sent/Failed" |
| FROM | The shortcode the message is sent from. |
| FROM_MASK | If Alpha-Numeric Sender ID was passed. |
| TO | The recipient of the message. |
| TRACKINGID | The ID to correleate API requests, and delivery receipts. |
| SPID |  Carrier Identification - please refer to [APPENDIX E](/1.3/CONTENTS/APPENDIX/APPENDIX_E.md). |
| TIMESTAMP | The timestamp the message sent (N201) or when MMS was delivered (N202) |
| AGGREGATORID | SMS aggregator or carrier transaction ID. |
| STATUSDETAILS | Any additional information passed back from the aggregator/carrier. |

_N201 Example:_
```xml
<?xml version='1.0'?>
<POSTBACK>
  <ORIGIN>SMS_MT</ORIGIN>
  <CODE>N201</CODE>
  <STATUS>Message Sent</STATUS>
  <FROM>60856</FROM>
  <FROM_MASK><FROM_MASK>
  <TO>16503333058</TO>
  <TRACKINGID>U01TXzgwNjc4</TRACKINGID>
  <SPID>0001470</SPID>
  <TIMESTAMP>2013-11-05T05:41:08-05:00</TIMESTAMP>
</POSTBACK>
```

_N202 Example:_
```xml
<?xml version='1.0'?>
<POSTBACK>
  <ORIGIN>SMS_MT</ORIGIN>
  <CODE>N202</CODE>
  <STATUS>Message Sent/Delivered</STATUS>
  <FROM>60856</FROM>
  <FROM_MASK></FROM_MASK>
  <TO>16503333058</TO>
  <TRACKINGID>U01TXzgwNjc4</TRACKINGID>
  <SPID>0001470</SPID>
  <TIMESTAMP>2013-11-05T05:41:15-05:00</TIMESTAMP>
  <AGGREGATORID>11529-64807-97508-73852-97658</AGGREGATORID>
</POSTBACK>
```
[Back To The Top](#DocTop)


### [MMS MT Delivery Status](MMSStatus)

A postback notification called `N101` is immediately sent after we begin to process the MMS. Upon receiving Delivery Report (DLR) from the carrier, the system generates Postback notification `N102` with the handset information. The N101 and N102 notifications are linked by TRACKINGID.

When the mobile network operator does not suport MMS or the destination handset does not support the size of the content within the MMS we fall back to SMS/xHTML to deliver the message. In this method we deliver the MMS as an SMS containing a link to an xHTML page with the content. The subject text of the MMS is included in the SMS message text. 

| Variable | Description |
| -------- | ----------- |
| ORIGIN | SMS_MT means an SMS terminated on a mobile. |
| CODE | Code 201 means the SMS was submitted to the carrier. |
| SENTAS | Indicates if the MMS was delivered as MMS (binary) or SMS (xHTML).|
| MMSID | ID of the MMS Template. |
| STATUS | For N101 notification status can be "Message Sent". For N102 notification status can be "Message Sent/Delivered", "Message Sent/Expired" or "Message Sent/Rejected" |
| FROM | The shortcode the message is sent from. |
| HANDSET | Handset profile returned inside Delivery Receipt. This is present only in N102 notification. |
| TO | The recipient of the message. |
| TRACKINGID | The ID to correleate API requests, and delivery receipts. |
| SPID |  Carrier Identification - please refer to [APPENDIX E](/1.3/CONTENTS/APPENDIX/APPENDIX_E.md). |
| TIMESTAMP | The timestamp the MMS was sent (N101) or when MMS was delivered (N102) |
| AGGREGATORID | SMS aggregator or carrier transaction ID. |
| STATUSDETAILS | Any additional information passed back from the aggregator/carrier. |
| OS | Only in N102 notification for binary sending, contains detected operating system of the handset. |

_N101 Example: (Binary)_
```xml
<?xml version='1.0'?>
<POSTBACK>
  <ORIGIN>MMS_MT</ORIGIN>
  <CODE>N101</CODE>
  <SENTAS>MMS</SENTAS>
  <STATUS>Message Sent</STATUS>
  <MMSID>39597</MMSID>
  <FROM>60856</FROM>
  <TO>16501112222</TO>
  <TRACKINGID>TU1TXzU5Nzg3OQ==</TRACKINGID>
  <SPID>0001570</SPID>
  <TIMESTAMP>2012-06-07T07:27:29-05:00</TIMESTAMP>
</POSTBACK>
```

_N101 Example: (xHTML)_
```xml
<?xml version='1.0'?>
<POSTBACK>
  <ORIGIN>MMS_MT</ORIGIN>
  <CODE>N101</CODE>
  <SENTAS>SMS</SENTAS>
  <STATUS>Message Sent</STATUS>
  <MMSID>39755</MMSID>
  <FROM>60856</FROM>
  <TO>16502424956</TO>
  <TRACKINGID>TU1TXzU5Nzg3Nw==</TRACKINGID>
  <SPID>0001140</SPID>
  <TIMESTAMP>2012-06-07T07:27:34-05:00</TIMESTAMP>
  <STATUSDETAILS>Handset setting: mms with pass via xHTML</STATUSDETAILS>
</POSTBACK>
```

_N102 Example: (Binary)_
```xml
<?xml version='1.0'?>
<POSTBACK>
  <ORIGIN>MMS_MT</ORIGIN>
  <CODE>N102</CODE>
  <SENTAS>MMS</SENTAS>
  <STATUS>Message Sent/Delivered</STATUS>
  <MMSID>39597</MMSID>
  <FROM>60856</FROM>
  <TO>16501112222</TO>
  <TRACKINGID>TU1TXzU5Nzg3OQ==</TRACKINGID>
  <SPID>0001570</SPID>
  <TIMESTAMP>2012-06-07T07:27:34-05:00</TIMESTAMP>
  <HANDSET>motol7c</HANDSET>
  <AGGREGATORID>11529-64807-97508-73852-97658</AGGREGATORID>
  <OS>iOS</OS>
</POSTBACK>
```

_N102 Example: (xHTML)_
```xml
<?xml version='1.0'?>
<POSTBACK>
  <ORIGIN>MMS_MT</ORIGIN>
  <CODE>N202</CODE>
  <SENTAS>SMS</SENTAS>
  <STATUS>Message Sent/Delivered</STATUS>
  <FROM>60856</FROM>
  <TO>16502424956</TO>
  <TRACKINGID>TU1TXzU5Nzg3Nw==</TRACKINGID>
  <SPID>0001140</SPID>
  <TIMESTAMP>2012-06-07T07:28:09-05:00</TIMESTAMP>
  <AGGREGATORID>11529-64807-97508-73852-97658</AGGREGATORID>
</POSTBACK>
```

When the system is unable to send an MMS we return a postback E101. 

_E101 Example:_
```xml
<?xml version='1.0'?>
<POSTBACK>
  <ORIGIN>MMS_MT</ORIGIN>
  <CODE>E101</CODE>
  <STATUS>Message Failed</STATUS>
  <MMSID>39755</MMSID>
  <FROM>60856</FROM>
  <TO>16502424956</TO>
  <TRACKINGID>TU1TXzU5Nzg3Nw==</TRACKINGID>
  <SPID>0001140</SPID>
  <STATUSDETAILS>Error fetching dynamic content</STATUSDETAILS>
</POSTBACK>
```
[Back To The Top](#DocTop)


<h3><a name="SaveMMSStatus">SaveMMS Encoding Status</h3>

When MMS is saved (using API or the MMS Composer) we generate postback notification. When saving and encoding of the content is successful we generate N003. If encoding of the content failed we generate postback E002 containgin MMSID and AUDIONAME/VIDEONAME pointing to the content that failed to encode properly. When E002 is returned the MMSID should be considered corrupted.

| Variable | Description |
| -------- | ----------- |
| CODE | N003 or E002 based on the success of the content encoding.|
| ORIGIN | MMS_MT for saving MMS content. |
| MMSID | ID of the MMS. |
| AUDIONAME | points to audio content that failed to encode properly. |
| VIDEONAME | points to video content that failed to encode properly. |

_N003 (Save MMS Successful) Example:_
```xml
<?xml version='1.0'?>
<POSTBACK>
  <ORIGIN>MMS_MT</ORIGIN>
  <CODE>N003</CODE>
  <MMSID>35674</MMSID>
</POSTBACK>
```

_E002 (Save MMS Failure) Example:_
```xml
<?xml version='1.0'?>
<POSTBACK>
  <ORIGIN>MMS_MT</ORIGIN>
  <CODE>E002</CODE>
  <MMSID>35674</MMSID>
  <AUDIONAME>sample.mp3</AUDIONAME>
</POSTBACK>
```
[Back To The Top](#DocTop)

## ToDo
- [ ] Add an SMS failure example XML
- [ ] Show an additional MMS failure Example XML
- [ ] Show applicable error codes inline
- [ ] Reference nodes back to original API XML responses
- [ ] Provie a better explanation of the timestamps and when the N101 is triggered
