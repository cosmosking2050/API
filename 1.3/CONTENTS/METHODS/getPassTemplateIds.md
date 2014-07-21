[Back to the Table of Contents](/1.3/README.md)

## getPassTemplateIds

__Synopsis:__  
This API function returns a list of Pass Template Ids for that account.

__Request: XML__
```xml
<REQUEST>
    <ACTION>getPassTemplateIds</ACTION>
    <API_KEY>apiKey</API_KEY>
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
</element>
```

__Request: GET__

    API_URL?action=getpasstemplateids&api_key=apiKey
    
__Request Parameters:__

    Mandatory: action, apikey
    Optional: N/A

__Response Parameters:__

    status, passtemplateids, Errorcode, Errorinfo

__Related Errorcodes:__

    E800

__Request Example:__
```xml
<REQUEST>
    <ACTION>getPassTemplateIds</ACTION>
    <API_KEY>qTFkykO9JTfahCOqJ0V2Wf5Cg1t8iWlZ</API_KEY>    
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
</element>
```

__Response Example: Success__
```xml
<RESPONSE>
    <STATUS>Success</STATUS>
    <PASSTEMPLATEIDS>30011,30234,30634</PASSTEMPLATEIDS>
</RESPONSE>
```

```xml
<element name="RESPONSE">
	<element name="STATUS">
		</text>
	</element>
	<element name="PASSTEMPLATEIDS">
	    </text>
	</element>
</element>
```

__Response Example: Failure__
```xml
<RESPONSE>
    <STATUS>Failure</STATUS>
    <ERRORCODE>E800</ERRORCODE>
    <ERRORINFO>No Pass Templates were created in this account</ERRORINFO>
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
