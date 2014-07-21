[Back to the Table of Contents](/1.3/README.md)

## sendSavedEmail

__Synopsis:__  
'sendSavedEmail' API sends a stored email template to an email address. Also, it requires a reference email campaign to which this email address will be subscribed to. If any case, the subscription fails then the email address is added to the email campaign's audience manager as 'unsubscribed'. Subscription to the campaign may fail if:

1. The _email address_ has already opted-out of a campaign in your account.  
2. The _email address_ has unsubscribed from any campaign associated with the SMTP server you are using.  
3. The _email address_ has filed a spam complaint.  
4. The _email address_ bounced during a previous delivery.  


The email address is referenced by 'EMAIL', email template is referenced by 'EMAILTEMPLATEID' and the email campaign is referenced by CAMPAIGNID in the API.

__Request:__
```xml
<REQUEST>
  	<ACTION>sendSavedEmail</ACTION>
    <API_KEY>apiKey</API_KEY>
    <EMAILTEMPLATEID>emailTemplateId</EMAILTEMPLATEID>
    <EMAIL>email</EMAIL>
    <CAMPAIGNID>emailCampaignId</CAMPAIGNID>
    <DATA>
        <FIRST_NAME>First Name</FIRST_NAME>
        <LAST_NAME>Last Name</LAST_NAME>
        <GENDER>Gender</GENDER>
        ...
    </DATA>   
</REQUEST>
```

```xml
<element name="REQUEST">
	<zeroOrMore>
		<element name="ACTION">
			</text>
		</element>
		<element name="API_KEY">
			</text>
		</element>
		<element name="EMAILTEMPLATEID">
			</text>
		</element>
		<element name="EMAIL">
			</text>
		</element>
		<element name="CAMPAIGNID">
			</text>
		</element>
		<element name="DATA">
			<zeroOrMore>
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
			</zeroOrMore>
		</element>
	</zeroOrMore>
</element>
```

__Request Parameters:__

    Mandatory: ACTION, API_KEY, EMAILTEMPLATEID, EMAIL, CAMPAIGNID
    Optional: N/A

__Response Parameters:__

    EMAILTEMPLATEID, CAMPAIGNID, EMAIL, STATUS, TRACKINGID, ERRORCODE, ERRORINFO

__Related Errorcodes:__

    E401, E402, E403, E713, E915, E916, E917

__Request Example:__  
XML:
```xml
<REQUEST>
    <ACTION>sendSavedEmail</ACTION>
    <API_KEY>qTFkykO9JTfahCOqJ0V2Wf5Cg1t8iWlZ</API_KEY>
    <EMAIL>john@email.com</EMAIL>
    <EMAILTEMPLATEID>1234</EMAILTEMPLATEID>
    <CAMPAIGNID>5678</CAMPAIGNID>
    <DATA>
        <FIRST_NAME>John</FIRST_NAME>
        <LAST_NAME>Smith</LAST_NAME>
        <AGE>29</AGE>
        <PET>Dog</PET>
    </DATA>   
</REQUEST>
```

```xml
<element name="REQUEST">
	<zeroOrMore>
		<element name="ACTION">
			</text>
		</element>
		<element name="API_KEY">
			</text>
		</element>
		<element name="EMAIL">
			</text>
		</element>
		<element name="EMAILTEMPLATEID">
			</text>
		</element>
		<element name="CAMPAIGNID">
			</text>
		</element>
		<element name="DATA">
			<zeroOrMore>
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
			</zeroOrMore>
		</element>
	</zeroOrMore>
</element>
```

GET:

    https://secure.skycore.com/API/wxml/1.3/index.php?action=sendsavedemail&api_key=qTFkykO9JTfahCOqJ0V2Wf5Cg1t8iWlZ
    &email=john@email.com&emailtemplateid=1234&campaignid=5678&data_first_name=John&data_last_name=Smith&data_age=29
    &data_pet=Dog

__Response Example: Success__
```xml
<RESPONSE>
    <STATUS>Success</STATUS>
    <EMAILTEMPLATEID>1234</EMAILTEMPLATEID>
    <TRACKINGID>EMAIL_12346</TRACKINGID>
    <EMAIL>john@email.com</EMAIL>
    <CAMPAIGNID>5678</CAMPAIGNID>
</RESPONSE>
```

```xml
<element name="RESPONSE">
	<zeroOrMore>
		<element name="STATUS">
			</text>
		</element>
		<element name="EMAILTEMPLATEID">
			</text>
		</element>
		<element name="TRACKINGID">
			</text>
		</element>
		<element name="EMAIL">
			</text>
		</element>
		<element name="CAMPAIGNID">
			</text>
		</element>
	</zeroOrMore>
</element>
```

__Response Example: Failure__
```xml
<RESPONSE>
     <STATUS>Failure</STATUS>
     <ERRORCODE>E713</ERRORCODE>
         <EMAIL>john@email.com</EMAIL>
         <EMAILTEMPLATEID>1234</EMAILTEMPLATEID>
         <CAMPAIGNID>5678</CAMPAIGNID>
     <ERRORINFO>There is billing problem on your account</ERRORINFO>
</RESPONSE>
```

```xml
<element name="RESPONSE">
	<zeroOrMore>
		<element name="STATUS">
			</text>
		</element>
		<element name="EMAILTEMPLATEID">
			</text>
		</element>
		<element name="ERRORCODE">
			</text>
		</element>
		<element name="ERRORINFO">
			</text>
		</element>
		<element name="EMAIL">
			</text>
		</element>
		<element name="CAMPAIGNID">
			</text>
		</element>
	</zeroOrMore>
</element>
```
