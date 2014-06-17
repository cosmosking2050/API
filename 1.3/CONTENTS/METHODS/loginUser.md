[Back to the Table of Contents](/1.3/README.md)&nbsp;&nbsp;|&nbsp;&nbsp;[Back to API Methods](API_METHODS.md)
## loginUser
__Synopsis:__  
This API function creates a session for an account so that widgets can be launched and linked to it such as the SWF MMS Composer Object or the MMS Preview SWF Objects.

__Request:__
```xml
<REQUEST>
    <ACTION>loginUser</ACTION>
    <API_KEY>API KEY</API_KEY>
</REQUEST>
```

__Request Parameters:__
<pre>
<strong>Mandatory:</strong>
Action, API_KEY
<strong>Optional:</strong>
N/A
</pre>

__Response Parameters:__  
Status, SessionID

__Related Error codes:__   
N/A

__Request Examples__  
XML:
```xml
<REQUEST>
    <ACTION>loginUSer</ACTION>
    <API_KEY>qTFkykO9JTfahCOqJ0V2Wf5Cg1t8iWlZ</API_KEY>
</REQUEST>
```

GET:

    https://secure.skycore.com/API/wxml/1.3/index.php?action=loginuser&api_key=qTFkykO9JTfahCOqJ0V2Wf5Cg1t8iWlZ
    
__Response Example: Success__
```xml
<RESPONSE>
    <STATUS>Success</STATUS>
    <SESSIONID>asdfsadfsadfsdf</SESSIONID>
</RESPONSE>
```

__Response Example: Failure__
```xml
<RESPONSE>
    <STATUS>Failure</STATUS>
    <ERRORCODE>E170</ERRORCODE>
    <ERRORINFO>Invalid</ERRORINFO>
</RESPONSE>
```
