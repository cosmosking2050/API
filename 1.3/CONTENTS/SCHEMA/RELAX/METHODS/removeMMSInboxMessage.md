REQUEST

```xml
element REQUEST {
    element ACTION { "removeMMSInboxMessage" } &
    element API_KEY { text } &
    element MMSINBOXID { text }
}
```

RESPONSE

```xml
element RESPONSE {
    element STATUS { text } &
    element MMSINBOXID { text }? &
    element ERRORCODE { text }? &
    element ERRORINFO { text }?
}
```