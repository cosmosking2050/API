[Back to the Table of Contents](/1.3/README.md)

## sendSavedMMS

__Synopsis:__  
This API sends stored content from a specified account using an MMSID to a single mobile number. FROM must be one of the shortcodes allowed for your account. In case the number is from a different country than the FROM shortcode is assigned to, the default shortcode for those countries will be used.

__Content Transcoding:__  
Every binary MMS we deliver can be transcoded for the destination handset and every web page we deliver is transcoded for the browsing handset. To transcode a binary MMS we must know what type of handset the user has. We are able to obtain this handset type information from delivery receipts and store the record in a handset cache for later use. We have a database of attributes which we manually match to every new handset in the cache so we can adapt the content during MMS delivery.

Our API allows you to dynamically change the text of each slide by setting up optional CUSTOMTEXT (CUSTOMTEXT must include mandatory fields: value and slide) and MMS Subject by setting CUSTOMSUBJECT.

A Device Discovery Message (DDM) is a short textual MMS message that is sent to the number to discover what handset the end user is using. We store this handset information in our system and reuse it, so a DDM is sent only to new numbers. If the DDM settings are not included within your API call and the number is not in the handset cache we will deliver the MMS with generic settings. If the handset is in the handset cache the DDM will not be sent and the MMS message will be transcoded and delivered immediately. You can force sending of DDM (regardless if number is cached) by setting DDMFORCE to 'true'

Our API allows you to customize DDM by setting 3 parameters:  
DDMTITLE - this is the DDM title (optional, if not set then "Device Discovery" text will be used)  
DDMTEXT - this is the DDM body (mandatory)  
DDMTIMEOUT - (in minutes) when we send DDM we wait for the Delivery Report which contain the handset profile. In some cases we do not receive it or it takes very long (handset turned off or out of range). This variable tells the system how long should it wait for DDM Delivery Report before sending actual content using Default parameters. Default value of this parameter is 5 minutes.

__Request:__
```xml
<REQUEST>
    <ACTION>sendSavedMMS</ACTION>
    <API_KEY>apiKey</API_KEY>
    <MMSID>MMSID</MMSID>
    <TO>Number</TO>
    <FROM>Shortcode</FROM>
    <CAMPAIGNREF>CampaignID</CAMPAIGNREF>
    <DDMTITLE>DDM Title</DDMTITLE>
    <DDMTEXT>DDM Body</DDMTEXT>
    <DDMTIMEOUT>DDM Timeout in minutes</DDMTIMEOUT>
    <CUSTOMTEXT>
        <VALUE>Custom Text for slide</VALUE>
        <SLIDE>Slide ID</SLIDE>
    </CUSTOMTEXT>
    <CUSTOMSUBJECT>MMS Custom Subject</CUSTOMSUBJECT>
    <DATA>
        <FIRST_NAME>First Name</FIRST_NAME>
        <LAST_NAME>Last Name</LAST_NAME>
        <GENDER>Gender</GENDER>
        ...
    </DATA>        
</REQUEST>
```

__Request Parameters:__

    Mandatory: action, api_key, mmsId, to, from
    Optional: campaignRef, ddmTitle, ddmText, ddmTimeout, customText, customSubject, data

__Response Parameters:__

    status, to, from, mmsId, trackingId, errorCode, errorInfo

__Related Error Codes:__

    E110, E111, E241, E620, E621, E623, E626, E628, E629, E713, E714, E715

__Request Example:__  
XML:
```xml
<REQUEST>
    <ACTION>sendSavedMMS</ACTION>
    <API_KEY>qTFkykO9JTfahCOqJ0V2Wf5Cg1t8iWlZ</API_KEY>
    <TO>16501234123</TO>
    <FROM>60856</FROM>
    <CAMPAIGNREF>12333</CAMPAIGNREF>
    <MMSID>35674</MMSID>
    <DDMTITLE>We are detecting your handset</DDMTITLE>
    <DDMTEXT>This message is free of charge and will allow us to deliver your content nice and smooth</DDMTEXT>
    <DDMTIMEOUT>10</DDMTIMEOUT>
    <CUSTOMTEXT>
        <VALUE>My Custom text in first slide</VALUE>
        <SLIDE>1</SLIDE>
    </CUSTOMTEXT>
    <CUSTOMSUBJECT>My Custom Subject</CUSTOMSUBJECT>
    <DATA>
        <FIRST_NAME>John</FIRST_NAME>
        <LAST_NAME>Smith</LAST_NAME>
        <AGE>30</AGE>
        <PET>Dog</PET>
    </DATA>        
</REQUEST>
```

GET:

    https://secure.skycore.com/API/wxml/1.3/index.php?action=sendsavedmms&api_key=qTFkykO9JTfahCOqJ0V2Wf5Cg1t8iWlZ
    &to=16501234123&from=60856&mmsid=35674&ddmtitle=We+are+detecting+your+handset
    &ddmtext=This+message+is+free+of+charge+and+will+allow+us+to+deliver+your+content+nice+and+smooth&ddmtimeout=5
    &customtext_1=My+Custom+text+in+first+slide&customsubject=My+Custom+Subject&data_first_name=John
    &data_last_name=Smith
    &data_age=30&data_pet=Dog

__Response Example: Success__
```xml
<RESPONSE>
    <STATUS>Success</STATUS>
    <MMSID>35674</MMSID>
    <TRACKINGID>TU1TXzU5Nzg3OQ==</TRACKINGID>
    <TO>16501234123</TO>
    <FROM>60586</FROM>
</RESPONSE>
```

__Response Example: Failure__
```xml
<RESPONSE>
    <STATUS>Failure</STATUS>
    <ERRORCODE>E713</ERRORCODE>
    <TO>16501234123</TO>
    <ERRORINFO>There is billing problem on your account</ERRORINFO>
</RESPONSE>
```

__Postback Notifications For SendSavedMMS__  
When the MMS delivery is processed successfully the system will generate a Postback notification. For more details please visit [postback doc](https://github.com/SkycoreMobile/API/blob/master/1.3/CONTENTS/POSTBACK_NOTIFICATION_SYSTEM.md).
```xml
<?xml version='1.0'?>
<POSTBACK>
    <ORIGIN>MMS_MT</ORIGIN>
    <CODE>N101</CODE>
    <SENTAS>MMS</SENTAS>
    <STATUS>Message Sent</STATUS>
    <MMSID>35674</MMSID>
    <TO>16501234123</TO>
    <TRACKINGID>TU1TXzU5Nzg3OQ==</TRACKINGID>
    <SPID>0001570</SPID>
    <TIMESTAMP>2012-06-07T07:27:29-05:00</TIMESTAMP>
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
    <TRACKINGID>TU1TXzU5Nzg3OQ==</TRACKINGID>
    <SPID>0001570</SPID>
    <TIMESTAMP>2012-06-07T07:27:34-05:00</TIMESTAMP>
    <HANDSET>motol7c</HANDSET>
    <AGGREGATORID>11529-64807-97508-73852-97658</AGGREGATORID>
</POSTBACK>
```