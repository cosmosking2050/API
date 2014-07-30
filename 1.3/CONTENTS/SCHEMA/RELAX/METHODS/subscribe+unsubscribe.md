REQUEST
```xml
element REQUEST {
    element ACTION { text } &
    element API_KEY { text } &
    element CAMPAIGNID { text } &
    element MOBILE { text } &
    element DATA {
        element FIRST_NAME { text }? &
        element LAST_NAME { text }? &
        element GENDER { text }? &
        ...
    }? &
    element NOTIFY { text }? &
    element SPID { text }? &
    element CTA {
        element TIMEZONE { text }?
    }?
}
```

RESPONSE
```xml
element RESPONSE {
    element STATUS { text } &
    element CAMPAIGNID { text }? &
    element MOBILE { text }? &
    element ERRORCODE { text }? &
    element ERRORINFO { text }?
}
```

POSTBACK

N301
```xml
element POSTBACK {
    element ORIGIN { "SUB" } &
    element CODE { "N301" } &
    element MOBILE { text } &
    element CAMPAIGNID { text } &
    element TIMESTAMP { text } &
    element SHORTCODE { text } &
    element CAMPAIGNTITLE { text } &
    element BRANDNAME { text } &
    element SOURCE { text }
}
```

N302
```xml
element POSTBACK {
    element ORIGIN { "SUB" } &
    element CODE { "N302" } &
    element MOBILE { text } &
    element CAMPAIGNID { text } &
    element TIMESTAMP { text } &
    element SHORTCODE { text } &
    element CAMPAIGNTITLE { text } &
    element BRANDNAME { text } &
    element SOURCE { text }
}
```
