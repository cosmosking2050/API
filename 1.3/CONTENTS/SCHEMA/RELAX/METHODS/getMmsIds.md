REQUEST
```xml
element REQUEST {
    element ACTION { "getMmsIds" } &
    element API_KEY { text }
}
```

RESPONSE
```xml
element RESPONSE {
    element STATUS { text } &
    element MMSIDS { text }? &
    element ERRORCODE { text }? &
    element ERRORINFO { text }?
}
```