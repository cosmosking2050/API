REQUEST
```xml
element REQUEST {
    element ACTION { "getEmailIds" } &
    element API_KEY { text }
}
```

RESPONSE
```xml
element RESPONSE {
    element STATUS { text } &
    element EMAILIDS { text }? &
    element ERRORCODE { text }? &
    element ERRORINFO { text }?
}
```