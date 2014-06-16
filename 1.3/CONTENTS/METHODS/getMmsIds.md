<a href="/1.3/README.md">Back to the Table of Contents</a>&nbsp;&nbsp;|&nbsp;&nbsp;<a href="API_METHODS.md">Back to API Methods</a>
<h2>getMmsIds</h2>
<strong>Synopsis:</strong>

This API function returns a list of comma separated MMSIDS for that account.

<strong>Request: XML</strong>
```xml
<REQUEST>
    <ACTION>getMmsIds</ACTION>
    <API_KEY>apiKey</API_KEY>
</REQUEST>
```

<strong>Request: GET</strong>
<pre>API_URL?action=getmmsids&amp;api_key=apiKey</pre>

<strong>Request Parameters:</strong>
<pre><strong>Mandatory:</strong>
action, apikey
<strong>Optional:</strong>
--
</pre>

<strong>Response Parameters:</strong>  
status, mmsids, Errorcode, Errorinfo

<strong>Related Errorcodes:</strong>  
E200

<strong>Request Examples</strong>

XML:
```xml
<REQUEST>
    <ACTION>getmmsids</ACTION>
    <API_KEY>qTFkykO9JTfahCOqJ0V2Wf5Cg1t8iWlZ</API_KEY>    
</REQUEST>
```

GET:
    https://secure.skycore.com/API/wxml/1.3/index.php?action=getmmsids&api_key=qTFkykO9JTfahCOqJ0V2Wf5Cg1t8iWlZ

<strong>Response Example: Success</strong>
```xml
<RESPONSE>
    <STATUS>Success</STATUS>
    <MMSIDS>10011,10234,10634</MMSIDS>
</RESPONSE>
```

<strong>Response Example: Failure</strong>
```xml
<RESPONSE>
    <STATUS>Failure</STATUS>
    <ERRORCODE>E200</ERRORCODE>
    <ERRORINFO>No MMS Templates were created in this account.</ERRORINFO>
</RESPONSE>
```
