REQUEST

```xml
element REQUEST {
    element ACTION { ”sendSavedMMS” } &
    element API_KEY { text } &
    element MMSID { text } &
    element TO { text } &
    element FROM { text } &
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
    element FROM { text }? &
    element MMSID { text }? &
    element TRACKINGID { text }? &
    element ERRORCODE { text }? &
    element ERRORINFO { text }?
}
```

POSTBACK

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
