[Back to the Table of Contents](/1.3/README.md)

## subscribe + unsubscribe

__Synopsis:__  
This API will subscribe or unsubscribe users to a particular campaign. Once a user is subscribed to a campaign they will receive all auto responders and scheduled messages for that campaign until they are unsubscribed through the API or through normal STOP or STOP ALL SMS request. You may not re-subscribe someone who has unsubscribed themselves from a campaign. You may re-subscribe someone who you have unsubscribed through the API.

__Request: subscribe__
```xml
<REQUEST>
	<ACTION>subscribe</ACTION>
    <API_KEY>API KEY</API_KEY>
    <CAMPAIGNID>Campaign ID</CAMPAIGNID>
    <MOBILE>Number to subscribe</MOBILE>
    <DATA>
        <FIRST_NAME>First Name</FIRST_NAME>
        <LAST_NAME>Last Name</LAST_NAME>
        <GENDER>Gender</GENDER>
        ...
    </DATA>   
    <NOTIFY>'yes/no' on whether to notify user on successful opt in</NOTIFY>
    <SPID> the carrier ID </SPID>
    <CTA>'yes/no' to request double opt in from the user to opt-in</CTA>
        <TIMEZONE>Timezone abbreviation: EST, CST, MST, PST, etc.</TIMEZONE>
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
	<element name="CAMPAIGNID">
		</text>
	</element>
	<element name="MOBILE">
		</text>
	</element>
	<optional>
		<element name="DATA">
			<element name="FIRST_NAME">
				</text>
			</element>
			<element name="LAST_NAME">
				</text>
			</element>
			<element name="GENDER">
				</text>
			</element>
			...
		</element>
	</optional>
	<optional>
		<element name="NOTIFY">
			</text>
		</element>
	</optional>
	<optional>
		<element name="SPID">
			</text>
		</element>
	</optional>
	<optional>
		<element name="CTA">
			<optional>
				<element name="TIMEZONE">
					</text>
				</element>
			</optional>
		</element>
	</optional>
</element>
```

__Request: unsubscribe__
```xml
<REQUEST>
    <ACTION>unsubscribe</ACTION>
    <API_KEY>API KEY</API_KEY>
    <CAMPAIGNID>Campaign ID</CAMPAIGNID>
    <MOBILE>Number to unsubscribe</MOBILE>
    <NOTIFY>'yes/no' on whether to notify user on opt-out</NOTIFY>
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
	<element name="CAMPAIGNID">
		</text>
	</element>
	<element name="MOBILE">
		</text>
	</element>
	<optional>
		<element name="NOTIFY">
			</text>
		</element>
	</optional>
</element>
```

__Request Parameters:__

    Mandatory: Action, API_KEY, CAMPAIGNID, Mobile
    Optional: CTA, Notify, SPID, TZ, Data

__Response Parameters:__

    CAMPAIGNID, Errorcode, Errorinfo, mobile, Status

__Related Errorcodes:__

    E901, E902, E903, E904, E905

__Request Example:__  
XML:
```xml
<REQUEST>
    <ACTION>subscribe</ACTION>
    <API_KEY>qTFkykO9JTfahCOqJ0V2Wf5Cg1t8iWlZ</API_KEY>
    <CAMPAIGNID>1116</CAMPAIGNID>
    <MOBILE>16502426055</MOBILE>
    <DATA>
        <FIRST_NAME>John</FIRST_NAME>
        <LAST_NAME>Smith</LAST_NAME>
        <AGE>29</AGE>
        <PET>Dog</PET>
    </DATA>   
    <NOTIFY>no</NOTIFY>
    <CTA>no</CTA>
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
	<element name="CAMPAIGNID">
		</text>
	</element>
	<element name="MOBILE">
		</text>
	</element>
	<optional>
		<element name="DATA">
			<element name="FIRST_NAME">
				</text>
			</element>
			<element name="LAST_NAME">
				</text>
			</element>
			<element name="AGE">
				</text>
			</element>
			<element name="PET">
				</text>
			</element>
		</element>
	</optional>
	<optional>
		<element name="NOTIFY">
			</text>
		</element>
	</optional>
	<optional>
		<element name="CTA">
			</text>
		</element>
	</optional>
</element>
```

GET:

    https://secure.skycore.com/API/wxml/1.3/index.php?action=subscribe&api_key=qTFkykO9JTfahCOqJ0V2Wf5Cg1t8iWlZ
    &mobile=16502426055&campaignid=1116&notify=no&cta=no&data_first_name=John&data_last_name=Smith&data_age=29&
    data_pet=Dog
    
__Response Example: Success__
```xml
<RESPONSE>
    <STATUS>Success</STATUS>
    <CAMPAIGNID>1116</CAMPAIGNID>
    <MOBILE>16502426055</MOBILE>
</RESPONSE>
```

```xml
<element name="RESPONSE">
	<element name="STATUS">
		</text>
	</element>
	<element name="CAMPAIGNID">
		</text>
	</element>
	<element name="MOBILE">
		</text>
	</element>
</element>
```

__Response Example: Failure__
```xml
<RESPONSE>
    <STATUS>Failure</STATUS>
    <ERRORCODE>E903</ERRORCODE>
    <ERRORINFO> Invalid CAMPAIGNID </ERRORINFO>
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
</element>
```

__Postback Notifications__  
Upon subscribing/unsubscribing a number the system will generate a notification.

__On subscribe:__
```xml
<NOTIFICATION id="325" created="2011-01-01 20:09:12.975911-04">
    <ORIGIN>SUB</ORIGIN>
    <CODE>N301</CODE>
    <BODY>
        <MOBILE>16502426055</MOBILE>
        <CAMPAIGNID>1116</CAMPAIGNID>
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
	    <element name="MOBILE">
	        </text>
        </element>
        <element name="CAMPAIGNID">
	        </text>
        </element>
	</element>
</element>
```

__On unsubscribe:__
```xml
<NOTIFICATION id="325" created="2011-01-01 20:09:12.975911-04">
    <ORIGIN>SUB</ORIGIN>
    <CODE>N302</CODE>
    <BODY>
        <MOBILE>16502426055</MOBILE>
        <CAMPAIGNID>1116</CAMPAIGNID>
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
	    <element name="MOBILE">
	        </text>
        </element>
        <element name="CAMPAIGNID">
	        </text>
        </element>
	</element>
</element>
```
