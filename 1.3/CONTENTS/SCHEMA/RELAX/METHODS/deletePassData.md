REQUEST

```xml
element REQUEST {
    element ACTION { "deletePassData" } &
    element API_KEY { text } &
    element PASSDATAID { text }
}
```

RESPONSE

```xml
element RESPONSE {
    element STATUS { text } &
    element ERRORCODE { text }? &
    element ERRORINFO { text }?
}
```