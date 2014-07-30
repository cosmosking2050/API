REQUEST

```xml
element REQUEST {
    element ACTION { text } &
    element API_KEY { text } &
    element CAMPAIGNID { text } &
    element EMAIL { text } &
    element DATA {
        element FIRST_NAME { text }? &
        element LAST_NAME { text }? &
        element GENDER { text }? &
        ...
    }? &
    element NOTIFY { text }?
}
```

RESPONSE

```xml
element RESPONSE {
    element STATUS { text } &
    element CAMPAIGNID { text }? &
    element EMAIL { text }? &
    element ERRORCODE { text }? &
    element ERRORINFO { text }?
}
```