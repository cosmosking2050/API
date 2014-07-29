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

__Request: GET__

    API_URL?action=getmmscampaigns&api_key=apiKey

__Request Parameters:__

    Mandatory: action, api_key
    Optional: N/A

```xml
element REQUEST {
    element ACTION { "getMmsCampaigns" } &
    element API_KEY { text }
}
```

__Response Parameters:__

    status, mmsCampaigns, campaign, id, name, errorCode, errorInfo

```xml
element RESPONSE {
    element STATUS { text } &
    element MMSCAMPAIGNS {
        element CAMPAIGN {
            element ID { text } &
            element NAME { text }
        }+
    }? &
    element ERRORCODE { text }? &
    element ERRORINFO { text }?
}
```

__Related Error Codes:__

    E405

__Request Examples__  
XML:
```xml
<REQUEST>
    <ACTION>getMmsCampaigns</ACTION>
    <API_KEY>qTFkykO9JTfahCOqJ0V2Wf5Cg1t8iWlZ</API_KEY>    
</REQUEST>
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

__Response Example: Failure__
```xml
<RESPONSE>
    <STATUS>Failure</STATUS>
    <ERRORCODE>E405</ERRORCODE>
    <ERRORINFO>No MMS Campaigns were created in this account</ERRORINFO>
</RESPONSE>
```