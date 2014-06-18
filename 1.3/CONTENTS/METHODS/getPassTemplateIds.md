[Back to the Table of Contents](/1.3/README.md)&nbsp;&nbsp;|&nbsp;&nbsp;[Back to API Methods](API_METHODS.md)
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

__Response Example: Success__
```xml
<RESPONSE>
    <STATUS>Success</STATUS>
    <PASSTEMPLATEIDS>30011,30234,30634</PASSTEMPLATEIDS>
</RESPONSE>
```

__Response Example: Failure__
```xml
<RESPONSE>
    <STATUS>Failure</STATUS>
    <ERRORCODE>E800</ERRORCODE>
    <ERRORINFO>No Pass Templates were created in this account</ERRORINFO>
</RESPONSE>
```
