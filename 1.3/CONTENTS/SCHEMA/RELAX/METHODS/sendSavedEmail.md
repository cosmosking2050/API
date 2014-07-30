REQUEST

```xml
element REQUEST {
    element ACTION { "sendSavedEmail" } &
    element API_KEY { text } &
    element EMAILTEMPLATEID { text } &
    element EMAIL { text } &
    element CAMPAIGNID { text } &
    element DATA {
        element FIRST_NAME { text }? &
        element LAST_NAME { text }? &
        element GENDER { text }? &
        ...
    }?
}
```

RESPONSE

```xml
element RESPONSE {
    element STATUS { text } &
    element EMAILTEMPLATEID { text }? &
    element TRACKINGID { text }? &
    element EMAIL { text }? &
    element CAMPAIGNID { text }? &
    element ERRORCODE { text }? &
    element ERRORINFO { text }?
}
```