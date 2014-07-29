[Back to the Table of Contents](/1.3/README.md)

## sendSMS

__Synopsis:__  
This API function sends an SMS containing *text* from the specified account and *shortcode* to a recipient’s mobile number. If the aggregator allows masking longcode/sender with some brand or string, 'from_mask' can be set in the API. 'from_mask' is limited to 11 characters beyond which it will be cut-off. If 'Enforce Campaign Check' is turned ON this function will require the ID of MMS campaign that receiver's number is subscribed to passed inside *campaignref* node.

__Request:__
```xml
<REQUEST>
    <ACTION>sendSMS</ACTION>
    <API_KEY>apiKey</API_KEY>
    <SPID>SPID</SPID>
    <TO>Recipient Number</TO>
    <FROM>shortcode</FROM>
    <FROM_MASK>senderName</FROM_MASK>
    <CAMPAIGNREF>CampaignID</CAMPAIGNREF>
    <TEXT>SMS Text message text</TEXT>
</REQUEST>
```

__Request Parameters:__

    (If "Enforce Campaign Check" is NOT Enabled)
    Mandatory: action, api_key, to, from, text
    Optional: spid, from_mask, campaignRef
    (If "Enforce Campaign Check" IS Enabled)
    Mandatory: Action, api_key, to, from, campaignRef, text
    Optional: spid, from_mask

```xml
element REQUEST {
    element ACTION { "sendSMS" } &
    element API_KEY { text } &
    element SPID { text }? &
    element TO { text } &
    element FROM { text } &
    element FROM_MASK { text }? &
    element CAMPAIGNREF { text } &
    element TEXT { text }
}
```
	
__Response Parameters:__

    status, trackingId, to, errorCode, errorInfo

```xml
element RESPONSE {
    element STATUS { text } &
    element TRACKINGID { text }? &
    element TO { text }? &
    element ERRORCODE { text }? &
    element ERRORINFO { text }?
}
```

__Related Error Codes:__

    E712, E201, E713, E110, E628, E111
	
__Request Examples__  
XML:
```xml
<REQUEST>
    <ACTION>sendSMS</ACTION>
    <API_KEY>Y6r74u6Br4hAVgrolveksjEiiu8yJX</API_KEY>
    <TO>15551234888</TO>
    <FROM>60856</FROM>
    <CAMPAIGNREF>77676</CAMPAIGNREF>
    <TEXT>Hello Jerry, Greetings from Marc</TEXT>
</REQUEST>
```

GET:

    https://secure.skycore.com/API/wxml/1.3/index.php?action=sendsms&api_key=Y6r74u6Br4hAVgrolveksjEiiu8yJX&to=15551234888&from=60856&text=Hello+Jerry%2C+Greetings+from+Marc

__Response Example: Success__
```xml
<RESPONSE>
    <STATUS>Success</STATUS>
    <TRACKINGID>U01TXzc2Nzg2Nw==</TRACKINGID>
    <TO>15551234888</TO>
 </RESPONSE>
```

__Response Example: Failure__
```xml
<RESPONSE>
    <STATUS>Failure</STATUS>
    <ERRORCODE>E713</ERRORCODE>
    <ERRORINFO>There is billing problem on your account</ERRORINFO>
    <TO>15551234888</TO>
</RESPONSE>
```

__Postback Notification:__  
When the SMS is sent we will generate a Postback notification.
```xml
<?xml version='1.0'?>
<POSTBACK>
    <ORIGIN>SMS_MT</ORIGIN>
    <CODE>N201</CODE>
    <STATUS>Message Sent</STATUS>
    <FROM>60856</FROM>
    <FROM_MASK></FROM_MASK>
    <TO>15551234888</TO>
    <TRACKINGID>U01TXzc2Nzg2Nw==</TRACKINGID>
    <SPID>0001470</SPID>
    <TIMESTAMP>2014-07-23T09:38:07.123456-04:00</TIMESTAMP>
</POSTBACK>
```

```xml
element POSTBACK {
    element ORIGIN { text } &
    element CODE { text } &
    element STATUS { text } &
    element FROM { text } &
    element FROM_MASK { text } &
    element TO { text } &
    element TRACKINGID { text } &
    element SPID { text } &
    element TIMESTAMP { text }
}
```

When we get an SMS delivery receipt we will generate another Postback notification. Not all carriers provide SMS delivery receipts.
```xml
<?xml version='1.0'?>
<POSTBACK>
    <ORIGIN>SMS_MT</ORIGIN>
    <CODE>N202</CODE>
    <STATUS>Message Sent/Delivered</STATUS>
    <FROM>60856</FROM>
    <FROM_MASK></FROM_MASK>
    <TO>16502555296</TO>
    <TRACKINGID>U01TXzc2Nzg2Nw==</TRACKINGID>
    <SPID>0001470</SPID>
    <TIMESTAMP>2014-07-23T09:38:09.765432-04:00</TIMESTAMP>
    <STATUSDETAILS>?smpp?deliver_sm=4&amp;</STATUSDETAILS>
    <AGGREGATORID>5114E-07230-09382-0762U</AGGREGATORID>
</POSTBACK>
```

```xml
element POSTBACK {
    element ORIGIN { text } &
    element CODE { text } &
    element STATUS { text } &
    element FROM { text } &
    element FROM_MASK { text } &
    element TO { text } &
    element TRACKINGID { text } &
    element SPID { text } &
    element TIMESTAMP { text } &
    element STATUSDETAILS { text } &
    element AGGREGATORID { text }
}
```