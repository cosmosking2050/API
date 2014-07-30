REQUEST

```xml
element REQUEST {
    element ACTION { "generatePassById" } &
    element API_KEY { text } &
    element PASSDATAID { text }
}
```

RESPONSE

```xml
element RESPONSE {
    element STATUS { text } &
    element PASSDATAID { text }? &
    element SERIALNUMBER { text }? &
    element CUSTOMPASSID { text }? &
    element PASSLINK { text }? &
    element DOWNLOADURL { text }? &
    element ERRORCODE { text }? &
    element ERRORINFO { text }?
}
```