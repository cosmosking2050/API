[Back to the Table of Contents](/1.3/README.md)&nbsp;&nbsp;|&nbsp;&nbsp;[Back to API Methods](API_METHODS.md)
## getEmailCampaigns
__Synopsis:__  
This API function returns a list of Email Campaigns for that account. Returned data consists of a campaign ID and Name.

__Request: XML__
```xml
<REQUEST>
    <ACTION>getEmailCampaigns</ACTION>
    <API_KEY>apiKey</API_KEY>
</REQUEST>
```

__Request: GET__

    API_URL?action=getemailcampaigns&api_key=apiKey

__Request Parameters:__
<pre>
<strong>Mandatory:</strong>
action, apikey
<strong>Optional:</strong>
--
</pre>

__Response Parameters:__  
status, campaign, id, name, Errorcode, Errorinfo

__Related Errorcodes:__  
E404

__Request Example:__  
XML:
```xml
<REQUEST>
    <ACTION>getEmailCampaigns</ACTION>
    <API_KEY>qTFkykO9JTfahCOqJ0V2Wf5Cg1t8iWlZ</API_KEY>    
</REQUEST>
```

GET:

    https://secure.skycore.com/API/wxml/1.3/index.php?action=getemailcampaigns&api_key=qTFkykO9JTfahCOqJ0V2Wf5Cg1t8iWlZ

__Response Example: Success__
```xml
<RESPONSE>
    <STATUS>Success</STATUS>
    <EMAILCAMPAIGNS>    
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
    </EMAILCAMPAIGNS>
</RESPONSE>
```

__Response Example: Failure__
```xml
<RESPONSE>
    <STATUS>Failure</STATUS>
    <ERRORCODE>E404</ERRORCODE>
    <ERRORINFO>No Email Campaigns were created in this account</ERRORINFO>
</RESPONSE>
```
