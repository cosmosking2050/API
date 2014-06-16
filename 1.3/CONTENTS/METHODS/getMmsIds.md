[Back to the Table of Contents](/1.3/README.md) | [Back to API Methods](API_METHODS.md)
<h2>getMmsIds</h2>
<strong>Synopsis:</strong>  
This API function returns a list of comma separated MMSIDS for that account.

__Request: XML__
```xml
<REQUEST>
    <ACTION>getMmsIds</ACTION>
    <API_KEY>apiKey</API_KEY>
</REQUEST>
```

__Request: GET__  

    API_URL?action=getmmsids&api_key=apiKey
    
__Request Parameters:__  
<pre><strong>Mandatory:</strong>
action, apikey
<strong>Optional:</strong>
--
</pre>

__Response Parameters:__  
status, mmsids, Errorcode, Errorinfo

__Related Errorcodes:__  
E200

__Request Examples__

XML:
```xml
<REQUEST>
    <ACTION>getmmsids</ACTION>
    <API_KEY>qTFkykO9JTfahCOqJ0V2Wf5Cg1t8iWlZ</API_KEY>    
</REQUEST>
```

GET:

    https://secure.skycore.com/API/wxml/1.3/index.php?action=getmmsids&api_key=qTFkykO9JTfahCOqJ0V2Wf5Cg1t8iWlZ

__Response Example: Success__
```xml
<RESPONSE>
    <STATUS>Success</STATUS>
    <MMSIDS>10011,10234,10634</MMSIDS>
</RESPONSE>
```

__Response Example: Failure__
```xml
<RESPONSE>
    <STATUS>Failure</STATUS>
    <ERRORCODE>E200</ERRORCODE>
    <ERRORINFO>No MMS Templates were created in this account.</ERRORINFO>
</RESPONSE>
```
