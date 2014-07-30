SMS MO
```xml
element POSTBACK {
    element ORIGIN { "SMS_MO" } &
    element CODE { "N211" } &
    element FROM { text } &
    element TO { text } &
    element TEXT { text } &
    element RECEIVED { text } &
    element TRANSACTIONID { text }
}
```

MMS MO
```xml
element POSTBACK {
    element ORIGIN { "MMS_MO" } &
    element CODE { "N401" } &
    element FROM { text } &
    element TO { text } &
    element KEYWORD { text } &
    element TRACKINGID { text } &
    element SPID { text } &
    element TIMESTAMP { text } &
    element CONTENT {
        element FILE { text }+
    }
}
```