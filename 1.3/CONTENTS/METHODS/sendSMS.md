<a href="/1.3/README.md">Back to the Table of Contents</a>&nbsp;&nbsp;|&nbsp;&nbsp;<a href="API_METHODS.md">Back to API Methods</a>
<h2>sendSMS</h2>
<strong>Synopsis:</strong>

This API function sends an SMS containing _text_ from the specified account and _shortcode_ to a recipient’s mobile number. If the aggregator allows masking longcode/sender with some brand or string, 'from_mask' can be set in the API. 'from_mask' is limited to 11 characters beyond which it will be cut-off. If 'Enforce Campaign Check' is turned ON this function will require the ID of MMS campaign that receiver's number is subscribed to passed inside _campaignref_ node.

<strong>Request:</strong>

```xml
<REQUEST>
    <ACTION>sendSMS</ACTION>
    <API_KEY>API KEY</API_KEY>
    <SPID>SPID</SPID>
    <TO>Recipient Number</TO>
    <FROM>shortcode</FROM>
    <FROM_MASK>senderName</FROM_MASK>
    <CAMPAIGNREF>CampaignID</CAMPAIGNREF>
    <TEXT>SMS Text message text</TEXT>
</REQUEST>
```

<strong>Request Parameters:</strong>

<pre>
<strong>(If "Enforce Campaign Check" is NOT Enabled)</strong>

<strong>Mandatory:</strong> Action, API_KEY, To, Text, From

<strong>Optional:</strong> SPID, CampaignRef, From_Mask

<strong>(If "Enforce Campaign Check" IS Enabled)</strong>

<strong>Mandatory:</strong> Action, API_KEY, To, Text, From, CampaignRef

<strong>Optional:</strong> SPID, From_Mask
</pre>
	
<strong>Response Parameters:</strong>

<pre>Status, TrackingID, To, Errorcode, Errorinfo</pre>
	
<strong>Related Error codes:</strong>

<pre>E712, E201, E713, E110, E628, E111</pre>
	
<strong>Request Examples</strong>

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

<pre>https://secure.skycore.com/API/wxml/1.3/index.php?action=sendsms&api_key=Y6r74u6Br4hAVgrolveksjEiiu8yJX
&to=15551234888&from=60856&text=Hello+Jerry%2C+Greetings+from+Marc</pre>

<strong>Response Example: Success</strong>

```xml
<RESPONSE>
    <STATUS>Success</STATUS>
    <TRACKINGID>SMS_12345</TRACKINGID>
    <TO>15551234888</TO>
 </RESPONSE>
```

<strong>Response Example: Failure</strong>

```xml
<RESPONSE>
    <STATUS>Failure</STATUS>
    <ERRORCODE>E713</ERRORCODE>
    <ERRORINFO>There is billing problem on your account</ERRORINFO>
    <TO>15551234888</TO>
</RESPONSE>
```

<strong>Postback Notification:</strong>

When the SMS is sent we will generate a Postback notification.

```xml
<NOTIFICATION ID="325" CREATED="2011-07-26 10:22:26.975911-04">
    <ORIGIN>SMS_MT</ORIGIN>
    <CODE>N201</CODE>
    <BODY>
    <HISTORYID>236990</HISTORYID>
    <TO>15551234888</TO>
    <TRACKINGID>SMS_12345</TRACKINGID>
    <TIMESTAMP>2011-07-26 10:22:25.262743-04</TIMESTAMP>
    </BODY>
</NOTIFICATION>
```

When we get an SMS delivery receipt we will generate another Postback notification. Not all carriers provide SMS delivery receipts.

```xml
<NOTIFICATION ID="326" CREATED="2011-07-26 10:22:27.146582-04">
    <ORIGIN>SMS_MT</ORIGIN>
    <CODE>N201</CODE>
    <BODY>
    <HISTORYID>236990</HISTORYID>
    <TO>15551234888</TO>
    <TRACKINGID>SMS_12345</TRACKINGID>
    <STATUS PROTOCOL="4" STATUS="0"/>
    <TIMESTAMP>2011-07-26 10:22:25.262743-04</TIMESTAMP>
    </BODY>
</NOTIFICATION>
```
