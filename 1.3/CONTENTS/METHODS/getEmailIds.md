[Back to the Table of Contents](/1.3/README.md)

## getEmailIds

__Synopsis:__  
This API function returns a comma separated list of Email Template Ids for that account.

__Request: XML__
```xml
<REQUEST>
    <ACTION>getEmailIds</ACTION>
    <API_KEY>apiKey</API_KEY>
</REQUEST>
```

__Request: GET__

    API_URL?action=getemailids&api_key=apiKey

__Request Parameters:__

    Mandatory: action, apikey
    Optional: N/A

__Response Parameters:__

    status, emailids, Errorcode, Errorinfo

__Related Errorcodes:__

    E400

__Request Example:__  
XML:
```xml
<REQUEST>
    <ACTION>getEmailIds</ACTION>
    <API_KEY>qTFkykO9JTfahCOqJ0V2Wf5Cg1t8iWlZ</API_KEY>    
</REQUEST>
```

GET:

    https://secure.skycore.com/API/wxml/1.3/index.php?action=getemailids&api_key=qTFkykO9JTfahCOqJ0V2Wf5Cg1t8iWlZ
    
__Response Example: Success__
```xml
<RESPONSE>
    <STATUS>Success</STATUS>
    <EMAILIDS>30011,30234,30634</EMAILIDS>
</RESPONSE>
```

__Response Example: Failure__
```xml
<RESPONSE>
    <STATUS>Failure</STATUS>
    <ERRORCODE>E400</ERRORCODE>
    <ERRORINFO>No Email Templates were created in this account</ERRORINFO>
</RESPONSE>
```
