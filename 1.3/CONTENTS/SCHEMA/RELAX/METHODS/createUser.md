REQUEST
```xml
element REQUEST {
    element ACTION { "createUser" } &
    element API_KEY { text } &
    element NEWUSER { text } &
    element NEWPASS { text }
}
```

RESPONSE
```xml
element RESPONSE {
    element STATUS { text } &
    element USERNAME { text }? &
    element PASSWORD { text }? &
    element API_KEY { text }? &
    element ERRORCODE { text }? &
    element ERRORINFO { text }?
}
```