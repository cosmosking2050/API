REQUEST
```xml
element REQUEST {
    element ACTION { “saveMMS” } &
    element API_KEY { text } &
    element SUBJECT { text } &
    element NAME { text } &
    element SLIDE {
        element IMAGE {
            element URL { text }
        }? &
        element AUDIO {
            element URL { text }
        }? &
        element VIDEO {
            element url { text }
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
    element MMSID { text }? &
    element ERRORCODE { text }? &
    element ERRORINFO { text }?
}
```

POSTBACK

N003
```xml
element POSTBACK {
    element ORIGIN { "MMS_MT" } &
    element CODE { "N003" } &
    element MMSID { text } &

}
```

E002
```xml
element POSTBACK {
    element ORIGIN { "MMS_MT" } &
    element CODE { "E002" } &
    element MMSID { text } &
    element AUDIONAME { text }
}
```