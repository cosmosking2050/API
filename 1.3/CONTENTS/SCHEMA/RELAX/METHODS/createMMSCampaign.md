REQUEST

```xml
element REQUEST {
    element ACTION { "createMMSCampaign" } &
    element API_KEY { text } &
    element CAMPAIGNNAME { text } &
    element BRANDNAME { text }
}
```

RESPONSE

```xml
element RESPONSE {
    element STATUS { text } &
    element CAMPAIGNID { text }? &
    element CAMPAIGNNAME { text }? &
    element BRANDNAME { text }? &
    element ERRORCODE { text }? &
    element ERRORINFO { text }?
}
```