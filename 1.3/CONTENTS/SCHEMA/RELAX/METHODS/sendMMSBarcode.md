REQUEST
```xml
element REQUEST {
    element ACTION { ”sendMMSBarcode” } &
    element API_KEY { text } &
    element MMSID { text } &
    element TO { text } &
    element FROM { text } &
    element BARCODEID { text } &
    element CAMPAIGNREF { text }? &
    element DDMTITLE { text }? &
    element DDMTEXT { text }? &
    element DDMTIMEOUT { xsd:nonNegativeInteger }? &
    element CUSTOMTEXT {
        element VALUE { text } &
        element SLIDE { xsd:nonNegativeInteger }
    }? &
    element CUSTOMSUBJECT { text }? &
    element DATA {
        element FIRST_NAME { text }? &
        element LAST_NAME { text }? &
        element GENDER { text }?
        ...
    }?
}
```

RESPONSE
```xml
element RESPONSE {
    element STATUS { text } &
    element TO { text }? &
    element MMSID { text }? &
    element TRACKINGID { text }? &
    element ERRORCODE { text }? &
    element ERRORINFO { text }?
}
```

POSTBACK

N101
```xml
element POSTBACK {
    element ORIGIN { text } &
    element CODE { "N101" } &
    element SENTAS { text } &
    element STATUS { text } &
    element MMSID { text } &
    element TO { text } &
    element TRACKINGID { text } &
    element SPID { text } &
    element TIMESTAMP { text }
}
```

N102
```xml
element POSTBACK {
    element ORIGIN { text } &
    element CODE { "N102" } &
    element SENTAS { text } &
    element STATUS { text } &
    element MMSID { text } &
    element TO { text } &
    element TRACKINGID { text } &
    element SPID { text } &
    element TIMESTAMP { text } &
    element HANDSET { text } &
    element AGGREGATORID { text }
}
```