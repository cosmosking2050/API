[Back to the Table of Contents](/1.3/README.md)

## getMmsCampaigns

__Synopsis:__  
This API function returns a list of MMS Campaigns for that account. Returned data consists of the campaign's ID and Name.

__Request: XML__
```xml
<REQUEST>
    <ACTION>getMmsCampaigns</ACTION>
    <API_KEY>apiKey</API_KEY>
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
	</zeroOrMore>
</element>
```

__Request: GET__

    API_URL?action=getmmscampaigns&api_key=apiKey

__Request Parameters:__

    Mandatory: action, apikey
    Optional: N/A

__Response Parameters:__

    status, campaign, id, name, Errorcode, Errorinfo

__Related Errorcodes:__

    E405

__Request Examples__  
XML:
```xml
<REQUEST>
    <ACTION>getMmsCampaigns</ACTION>
    <API_KEY>qTFkykO9JTfahCOqJ0V2Wf5Cg1t8iWlZ</API_KEY>    
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
	</zeroOrMore>
</element>
```

GET:

    https://secure.skycore.com/API/wxml/1.3/index.php?action=getmmscampaigns&api_key=qTFkykO9JTfahCOqJ0V2Wf5Cg1t8iWlZ

__Response Example: Success__
```xml
<RESPONSE>
    <STATUS>Success</STATUS>
    <MMSCAMPAIGNS>
        <CAMPAIGN>
            <ID>1233</ID>
            <NAME>Winter Sale</NAME>
        </CAMPAIGN>
        <CAMPAIGN>
            <ID>1234</ID>
            <NAME>Summer Sale</NAME>
        </CAMPAIGN>
        <CAMPAIGN>
            <ID>1235</ID>
            <NAME>Store opening</NAME>
        </CAMPAIGN>
    </MMSCAMPAIGNS>
</RESPONSE>
```

```xml
<element name="RESPONSE">
	<zeroOrMore>
		<element name="STATUS">
			</text>
		</element>
		<element name="MMSCAMPAIGNS">
		    <zeroOrMore>
		        <element name="CAMPAIGN">
		            <zeroOrMore>
		                <element name="ID">
		                    </text>
		                </element>
		                <element name="NAME">
		                    </text>
		                </element>
		            </zeroOrMore>
		        </element>
		        ....
		        ....
		    </zeroOrMore>
		</element>
    </zeroOrMore>
</element>
```

__Response Example: Failure__
```xml
<RESPONSE>
    <STATUS>Failure</STATUS>
    <ERRORCODE>E405</ERRORCODE>
    <ERRORINFO>No MMS Campaigns were created in this account</ERRORINFO>
</RESPONSE>
```

```xml
<element name="RESPONSE">
	<zeroOrMore>
		<element name="STATUS">
			</text>
		</element>
		<element name="ERRORCODE">
			</text>
		</element>
		<element name="ERRORINFO">
			</text>
		</element>
	</zeroOrMore>
</element>
```
