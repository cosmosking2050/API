REQUEST
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

RESPONSE
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