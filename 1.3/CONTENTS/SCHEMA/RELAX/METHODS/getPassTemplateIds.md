REQUEST

```xml
element REQUEST {
    element ACTION { "getPassTemplateIds" } &
    element API_KEY { text }
}
```

RESPONSE

```xml
element RESPONSE {
    element STATUS { text } &
    element PASSTEMPLATEIDS { text }? &
    element ERRORCODE { text }? &
    element ERRORINFO { text }?
}
```