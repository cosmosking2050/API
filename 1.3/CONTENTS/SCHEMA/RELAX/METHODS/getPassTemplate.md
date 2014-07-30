REQUEST
```xml
element REQUEST {
    element ACTION { "getPassTemplate" } &
    element API_KEY { text } &
    element PASSTEMPLATEID { text }? &
    element MMSID { text }? &
    element EMAILID { text }?
}
```

RESPONSE
```xml
element RESPONSE {
    element STATUS { text } &
    element PASSTEMPLATEID { text }? &
    element PASSTEMPLATE {
        ...
    }? &
    element ERRORCODE { text }? &
    element ERRORINFO { text }?
}
```