[Back to the Table of Contents](/1.3/README.md)

__Synopsis:__  
This API function creates new MMS/SMS campaign within the account holders account and returns a CampaignID. 
Campaign will be created under *campaignname* in our system. *Campaignname* will be sent to users in opt-in/opt-out messages. *Brandname* will be shown on opt-in, help and opt-out messages to the end user to identify who is running the campaign.

__Request:__
```xml
<REQUEST>
  <ACTION>createMMSCampaign</ACTION>
    <API_KEY>API KEY</API_KEY>
    <CAMPAIGNNAME>Camapign Name</CAMPAIGNNAME>
    <BRANDNAME>Brand</BRANDNAME>
</REQUEST>
```

__Request Parameters:__

    Mandatory: Action, API_KEY, CampaignName, BrandName
    Optional: N/A

__Response Parameters:__

    CampaignID, CampaignName, BrandName, ErrorInfo, Errorcode

__Related Error codes:__

    E170, E171, E172

__Request Example:__  
XML:
```xml
<REQUEST>
    <ACTION>createMMSCampaign</ACTION>
    <API_KEY>qTFkykO9JTfahCOqJ0V2Wf5Cg1t8iWlZ</API_KEY>
    <CAMPAIGNNAME>Winter Sale</CAMPAIGNNAME>
    <BRANDNAME>Gap</BRANDNAME>
</REQUEST>
```

GET:

    https://secure.skycore.com/API/wxml/1.3/index.php?action=createmmscampaign&api_key=qTFkykO9JTfahCOqJ0V2Wf5Cg1t8iWlZ
    &campaignname=Winter+Sale&brandname=Gap
    
__Response Example: Success__
```xml
<RESPONSE>
    <STATUS>Success</STATUS>
    <CAMPAIGNID>1116</CAMPAIGNID>
    <CAMPAIGNNAME>Winter Sale</CAMPAIGNNAME>
    <BRANDNAME>Gap</BRANDNAME>
</RESPONSE>
```

__Response Example: Failure__
```xml
<RESPONSE>
    <STATUS>Failure</STATUS>
    <ERRORCODE>E170</ERRORCODE>
    <ERRORINFO>campaignname is required</ERRORINFO>
</RESPONSE>
```
