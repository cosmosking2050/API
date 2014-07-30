REQUEST
```xml
element REQUEST {
    element ACTION { “sendMMS” } &
    element API_KEY { text } &
    element TO { text } &
    element FROM { text } &
    element SPID { text }? &
    element CAMPAIGNREF { text }? &
    element SUBJECT { text }? &
    element NAME { text } &
    element SLIDE {
        element IMAGE {
            element URL { text }
        }? &
        element AUDIO {
            element URL { text }
        }? &
        element VIDEO {
            element URL { text }
        }? &
        element TEXT { text }? &
        element DURATION { xsd:nonNegativeInteger }?    # in seconds
    }+
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