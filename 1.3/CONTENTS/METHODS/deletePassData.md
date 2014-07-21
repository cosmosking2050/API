[Back to the Table of Contents](/1.3/README.md)

## deletePassData


__Synopsis:__  
This API request deletes the pass data from the pass database. All the delivered passes with this data are not affected but any future requests to deliver/update/generate Passbook pass with this data will result in failure. For more info see below for Mandatory/Optional fields and Error codes.

__Request: XML__
```xml
<REQUEST>
    <ACTION>deletePassData</ACTION>
    <API_KEY>apiKey</API_KEY>
    <PASSDATAID>passDataId</PASSDATAID>
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
    <element name="PASSDATAID">
        </text>
    </element>
</element>
```

__Request: GET__

    API_URL?action=deletepassdata&api_key=apiKey&passdataid=passDataId

__Request Parameters:__

    Mandatory: action, apiKey, passDataId
    Optional: N/A

__Response Parameters:__

    status, Errorcode, Errorinfo

__Related Errorcodes:__

    E807, E808, E821
    
__Request Example:__
```xml
<REQUEST>
    <ACTION>deletePassData</ACTION>
    <API_KEY>qTFkykO9JTfahCOqJ0V2Wf5Cg1t8iWlZ</API_KEY>
    <PASSDATAID>1233</PASSDATAID>
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
    <element name="PASSDATAID">
        </text>
    </element>
</element>
```

__Response Example: Success__
```xml
<RESPONSE>
    <STATUS>Success</STATUS>
</RESPONSE>
```

```xml
<element name="RESPONSE">
    <element name="STATUS">
        </text>
    </element>
</element>
```

__Response Example: Failure__
```xml
<RESPONSE>
    <STATUS>Failure</STATUS>
    <ERRORCODE>E821</ERRORCODE>
    <ERRORINFO>Pass was not deleted. Internal error occured.</ERRORINFO>
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
