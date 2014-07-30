REQUEST

```xml
element REQUEST {
    element ACTION { "loginUser" } &
    element API_KEY { text }
}
```

RESPONSE

```xml
element RESPONSE {
    element STATUS { text } &
    element SESSIONID { text }
}
```