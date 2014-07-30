[Back to the Table of Contents](/1.3/README.md)

## sendSavedMMSCampaign

__*Postback Notifications for this action are the same as for SendSavedMMS__

__Synopsis:__  
This API function sends stored MMS from a specified account using a MMSID to a list of mobile numbers that are currently subscribed to a campaign. Recipient addresses are not specified, only the CampaignID is specified. Content will be sent from campaign default shortcode.

__Request:__
```xml
<REQUEST>
    <ACTION>sendSavedMMSCampaign</ACTION>
    <API_KEY>apiKey</API_KEY>
    <MMSID>MMSID</MMSID>
    <TOCAMPAIGN>CampaignID</TOCAMPAIGN>
</REQUEST>
```

__Request Parameters:__

    Mandatory: action, api_key, mmsId, toCampaign
    Optional: N/A

__Response Parameters:__

    status, mmsId, scheduledId, errorCode, errorInfo

__Related Error Codes:__

    E241, E620, E624, E626, E629, E714

__Request Example:__  
XML:
```xml
<REQUEST>
    <ACTION>sendSavedMMSCampaign</ACTION>
    <API_KEY>qTFkykO9JTfahCOqJ0V2Wf5Cg1t8iWlZ</API_KEY>
    <TOCAMPAIGN>332</TOCAMPAIGN>
    <MMSID>35674</MMSID>
</REQUEST>
```

GET:

    https://secure.skycore.com/API/wxml/1.3/index.php?action=sendsavedmmscampaign&api_key=qTFkykO9JTfahCOqJ0V2Wf5Cg1t8iWlZ
    &campaignid=332&mmsid=35674

__Response Example: Success__
```xml
<RESPONSE>
    <STATUS>Success</STATUS>
    <MMSID>35674</MMSID>
    <SCHEDULEDID>12346</SCHEDULEDID>
</RESPONSE>
```

__Response Example: Failure__
```xml
<RESPONSE>
    <STATUS>Failure</STATUS>
    <ERRORCODE>E714</ERRORCODE>
    <ERRORINFO>Missing/Invalid CampaignID</ERRORINFO>
</RESPONSE>
```

__Postback Notifications For SendSavedMMS, SendSavedMMSCampaign__  
When the MMS delivery is processed successfully the system will generate a Postback notification. For more details please visit [postback doc](https://github.com/SkycoreMobile/API/blob/master/1.3/CONTENTS/POSTBACKS/POSTBACK_DELIVERY_REPORTS.md).
```xml
<?xml version='1.0'?>
<POSTBACK>
    <ORIGIN>MMS_MT</ORIGIN>
    <CODE>N101</CODE>
    <SENTAS>MMS</SENTAS>
    <STATUS>Message Sent</STATUS>
    <MMSID>35674</MMSID>
    <TO>16501234123</TO>
    <TRACKINGID>TU1TXzEyMzQ2</TRACKINGID>
    <SPID>0001890</SPID>
    <TIMESTAMP>2011-08-02T07:20:44-04:00</TIMESTAMP>
</POSTBACK>
```

When an MMS delivery report is received the system will generate a Postback notification. Not all carriers provide MMS delivery receipts.
```xml
<?xml version='1.0'?>
<POSTBACK>
    <ORIGIN>MMS_MT</ORIGIN>
    <CODE>N102</CODE>
    <SENTAS>MMS</SENTAS>
    <STATUS>Message Sent/Delivered</STATUS>
    <MMSID>35674</MMSID>
    <TO>16501234123</TO>
    <TRACKINGID>TU1TXzEyMzQ2</TRACKINGID>
    <SPID>0001890</SPID>
    <TIMESTAMP>2011-08-02T07:20:49-04:00</TIMESTAMP>
    <HANDSET>motol7c</HANDSET>
    <AGGREGATORID>11529-64807-97508-73852-97658</AGGREGATORID>
</POSTBACK>
```