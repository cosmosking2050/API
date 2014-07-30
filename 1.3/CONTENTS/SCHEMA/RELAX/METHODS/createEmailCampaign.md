[Back to the Table of Contents](/1.3/README.md)

## createEmailCampaign

__Synopsis:__  
This API function creates new email campaign within the account holders account and returns a CampaignID. Campaign will be created under _campaignname_ in our system. _Campaignname_ will be sent to users in opt-in/opt-out emails. _Brandname_ will be used in 'from' field of all sent emails. _Mailingadress_ will be inserted into email footer.

__Request:__
```xml
<REQUEST>
    <ACTION>createEmailCampaign</ACTION>
    <API_KEY>apiKey</API_KEY>
    <CAMPAIGNNAME>Campaign Name</CAMPAIGNNAME>
    <BRANDNAME>Brand Name</BRANDNAME>
        <MAILINGADDRESS>Mailing Address</MAILINGADDRESS>
</REQUEST>
```

__Request Parameters:__

    Mandatory: action, api_key, campaignName, brandName, mailingAddress
    Optional: N/A

```xml
element REQUEST {
    element ACTION { "createEmailCampaign" } &
    element API_KEY { text } &
    element CAMPAIGNNAME { text } &
    element BRANDNAME {
        element MAILINGADDRESS { text }
    }
}
```

__Response Parameters:__

    status, campaignId, campaignName, brandName, mailingAddress, errorCode, errorInfo

```xml
element RESPONSE {
    element STATUS { text } &
    element CAMPAIGNID { text }? &
    element CAMPAIGNNAME { text }? &
    element BRANDNAME {
        element MAILINGADDRESS { text }?
    }? &
    element ERRORCODE { text }? &
    element ERRORINFO { text }?
}
```

__Related Error Codes:__

    E170, E171, E172, E173    

__Request Example:__  
XML:
```xml
<REQUEST>
    <ACTION>createEmailCampaign</ACTION>
    <API_KEY>qTFkykO9JTfahCOqJ0V2Wf5Cg1t8iWlZ</API_KEY>
    <CAMPAIGNNAME>Winter Sale</CAMPAIGNNAME>
    <BRANDNAME>Codereadr</BRANDNAME>
        <MAILINGADDRESS>Skycore, LLC 
            214 Lincoln Street, Suite 360
            Allston, MA 02134</MAILINGADDRESS>
</REQUEST>
```

GET:

    https://secure.skycore.com/API/wxml/1.3/index.php?action=createemailcampaign&api_key=qTFkykO9JTfahCOqJ0V2Wf5Cg1t8iWlZ
    &campaignname=Winter+Sale&brandname=Codereadr
    &mailingaddress=Skycore%2C+LLC%0A214+Lincoln+Street%2C+Suite+360%0AAllston%2C+MA+02134

__Response Example: Success__
```xml
<RESPONSE>
    <STATUS>Success</STATUS>
    <CAMPAIGNID>1116</CAMPAIGNID>
    <CAMPAIGNNAME>Winter Sale</CAMPAIGNNAME>
    <BRANDNAME>Codereadr</BRANDNAME>
        <MAILINGADDRESS>Skycore, LLC 
            214 Lincoln Street, Suite 360
            Allston, MA 02134</MAILINGADDRESS>
</RESPONSE>
```
        
__Response Example: Failure__
```xml
<RESPONSE>
    <STATUS>Failure</STATUS>
    <ERRORCODE>E173</ERRORCODE>
    <ERRORINFO>mailingaddress is required</ERRORINFO>
</RESPONSE>
```