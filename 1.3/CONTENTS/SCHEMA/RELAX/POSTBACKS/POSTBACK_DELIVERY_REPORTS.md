SMS MT N201
```xml
element POSTBACK {
    element ORIGIN { "SMS_MT" } &
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

SMS MT N202
```xml
element POSTBACK {
    element ORIGIN { "SMS_MT" } &
    element CODE { "N202" } &
    element STATUS { text } &
    element FROM { text } &
    element FROM_MASK { text } &
    element TO { text } &
    element TRACKINGID { text } &
    element SPID { text } &
    element TIMESTAMP { text } &
    element AGGREGATORID { text }
}
```

MMS MT N101 (Binary)
```xml
element POSTBACK {
    element ORIGIN { "MMS_MT" } &
    element CODE { "N101" } &
    element SENTAS { text } &
    element STATUS { text } &
    element MMSID { text } &
    element FROM { text } &
    element TO { text } &
    element TRACKINGID { text } &
    element SPID { text } &
    element TIMESTAMP { text }
}
```

MMS MT N101 (xHTML)
```xml
element POSTBACK {
    element ORIGIN { "MMS_MT" } &
    element CODE { "N101" } &
    element SENTAS { text } &
    element STATUS { text } &
    element MMSID { text } &
    element FROM { text } &
    element TO { text } &
    element TRACKINGID { text } &
    element SPID { text } &
    element TIMESTAMP { text } &
    element STATUSDETAILS { text }
}
```

MMS MT N102 (Binary)
```xml
element POSTBACK {
    element ORIGIN { "MMS_MT" } &
    element CODE { "N102" } &
    element SENTAS { text } &
    element STATUS { text } &
    element MMSID { text } &
    element FROM { text } &
    element TO { text } &
    element TRACKINGID { text } &
    element SPID { text } &
    element TIMESTAMP { text } &
    element HANDSET { text } &
    element AGGREGATORID { text } &
}
```

MMS MT N102 (xHTML)
```xml
element POSTBACK {
    element ORIGIN { "MMS_MT" } &
    element CODE { "N102" } &
    element SENTAS { text } &
    element STATUS { text } &
    element FROM { text } &
    element TO { text } &
    element TRACKINGID { text } &
    element SPID { text } &
    element TIMESTAMP { text } &
    element AGGREGATORID { text }
}
```

MMS MT ERROR
E101
```xml
element POSTBACK {
    element ORIGIN { "MMS_MT" } &
    element CODE { "E101" } &
    element STATUS { text } &
    element MMSID { text } &
    element FROM { text } &
    element TO { text } &
    element TRACKINGID { text } &
    element SPID { text } &
    element STATUSDETAILS { text }
}
```

Save MMS SUCCESS N003
```xml
element POSTBACK {
    element ORIGIN { "MMS_MT" } &
    element CODE { "N003" } &
    element MMSID { text }
}
```

Save MMS FAILURE E002
```xml
element POSTBACK {
    element ORIGIN { "MMS_MT" } &
    element CODE { "E002" } &
    element MMSID { text } &
    element AUDIONAME { text }
}
```