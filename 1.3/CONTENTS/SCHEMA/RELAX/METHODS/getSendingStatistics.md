REQUEST
```xml
element REQUEST {
    element ACTION { "getSendingStatus" } &
    element API_KEY { text } &
    element START_DATE { text } &
    element END_DATE { text }
}
```

RESPONSE
```xml
element RESPONSE {
    element STATUS { text } &
    element MMSID { text }? &
    element ERRORCODE { text }? &
    element ERRORINFO { text }?
}
```