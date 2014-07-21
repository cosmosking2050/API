[Back to the Table of Contents](/1.3/README.md)

## sendSMS

__Synopsis:__  
This API function sends an SMS containing *text* from the specified account and *shortcode* to a recipient’s mobile number. If the aggregator allows masking longcode/sender with some brand or string, 'from_mask' can be set in the API. 'from_mask' is limited to 11 characters beyond which it will be cut-off. If 'Enforce Campaign Check' is turned ON this function will require the ID of MMS campaign that receiver's number is subscribed to passed inside *campaignref* node.

__Request:__
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

If "Enforce Campaign Check" is NOT Enabled, CampaignRef is optional.
If "Enforce Campaign Check" IS Enabled, CampaignRef is mandatory.
```xml
<element name="REQUEST">
	<element name="ACTION">
	    </text>
	</element>
    <element name="API_KEY">
        </text>
    </element>
    <optional>
        <element name="SPID">
	        </text>
        </element>
    </optional>
    <element name="TO">
        </text>
    </element>
    <element name="FROM">
        </text>
    </element>
    <optional>
        <element name="FROM_MASK">
	        </text>
        </element>
    </optional>
    <optional>
        <element name="CAMPAIGNREF">
	        </text>
        </element>
    </optional>
    <element name="TEXT">
        </text>
    </element>
</element>
```

__Request Parameters:__

    (If "Enforce Campaign Check" is NOT Enabled)
    Mandatory: Action, API_KEY, To, Text, From
    Optional: SPID, CampaignRef, From_Mask
    (If "Enforce Campaign Check" IS Enabled)
    Mandatory: Action, API_KEY, To, Text, From, CampaignRef
    Optional: SPID, From_Mask
	
__Response Parameters:__

    Status, TrackingID, To, Errorcode, Errorinfo
	
__Related Error codes:__

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

```xml
<element name="REQUEST">
	<element name="ACTION">
	    </text>
	</element>
    <element name="API_KEY">
        </text>
    </element>
    <element name="TO">
        </text>
    </element>
    <element name="FROM">
        </text>
    </element>
    <optional>
        <element name="CAMPAIGNREF">
	        </text>
        </element>
    </optional>
    <element name="TEXT">
        </text>
    </element>
</element>
```

GET:

    https://secure.skycore.com/API/wxml/1.3/index.php?action=sendsms&api_key=Y6r74u6Br4hAVgrolveksjEiiu8yJX&to=15551234888&from=60856&text=Hello+Jerry%2C+Greetings+from+Marc

__Response Example: Success__
```xml
<RESPONSE>
    <STATUS>Success</STATUS>
    <TRACKINGID>SMS_12345</TRACKINGID>
    <TO>15551234888</TO>
 </RESPONSE>
```

```xml
<element name="RESPONSE">
	<element name="STATUS">
	    </text>
	</element>
    <element name="TRACKINGID">
        </text>
    </element>
    <element name="TO">
        </text>
    </element>
</element>
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

```xml
<element name="RESPONSE">
	<element name="STATUS">
	    </text>
	</element>
    <element name="ERRORCODE">
        </text>
    </element>
    <element name="ERRORINFO">
        </text>
    </element>
    <element name="TO">
        </text>
    </element>
</element>
```

__Postback Notification:__  
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

```xml
<element name="NOTIFICATION">
    <attribute name="ID">
        </text>
    </attribute>
    <attribute name="CREATED">
        </text>
    </attribute>
	<element name="ORIGIN">
		</text>
	</element>
	<element name="CODE">
		</text>
	</element>
	<element name="BODY">
	    <element name="HISTORYID">
	        </text>
        </element>
        <element name="TO">
	        </text>
        </element>
        <element name="TRACKINGID">
	        </text>
        </element>
        <element name="TIMESTAMP">
	        </text>
        </element>
	</element>
</element>
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

```xml
<element name="NOTIFICATION">
    <attribute name="ID">
        </text>
    </attribute>
    <attribute name="CREATED">
        </text>
    </attribute>
	<element name="ORIGIN">
		</text>
	</element>
	<element name="CODE">
		</text>
	</element>
	<element name="BODY">
	    <element name="HISTORYID">
	        </text>
        </element>
        <element name="TO">
	        </text>
        </element>
        <element name="TRACKINGID">
	        </text>
        </element>
        <element name="STATUS">
	        <attribute name="PROTOCOL">
		        </text>
		    </attribute>
		    <attribute name="STATUS">
		        </text>
		    </attribute>
        </element>
        <element name="TIMESTAMP">
	        </text>
        </element>
	</element>
</element>
```
