REQUEST

```xml
element REQUEST {
    element ACTION { "sendSMS" } &
    element API_KEY { text } &
    element SPID { text }? &
    element TO { text } &
    element FROM { text } &
    element FROM_MASK { text }? &
    element CAMPAIGNREF { text } &    # If "Enforce Campaign Check" IS Enabled, then MANDATORY otherwise OPTIONAL
    element TEXT { text }
}
```

RESPONSE

```xml
element RESPONSE {
    element STATUS { text } &
    element TRACKINGID { text }? &
    element TO { text }? &
    element ERRORCODE { text }? &
    element ERRORINFO { text }?
}
```

POSTBACK

```xml
element POSTBACK {
    element ORIGIN { text } &
    element CODE { "N201" } &
    element STATUS { text } &
    element FROM { text } &
    element FROM_MASK { text } &
    element TO { text } &
    element TRACKINGID { text } &
    element SPID { text } &
    element TIMESTAMP { text }
}
```

```xml
element POSTBACK {
    element ORIGIN { text } &
    element CODE { "N202" } &
    element STATUS { text } &
    element FROM { text } &
    element FROM_MASK { text } &
    element TO { text } &
    element TRACKINGID { text } &
    element SPID { text } &
    element TIMESTAMP { text } &
    element STATUSDETAILS { text } &
    element AGGREGATORID { text }
}
```