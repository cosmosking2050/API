Mobile Subscribe
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

Mobile Unsubscribe
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

Email Subscribe
```xml
element POSTBACK {
    element ORIGIN { "EMAIL_SUB" } &
    element CODE { "N303" } &
    element EMAIL { text } &
    element CAMPAIGNID { text }
}
```

Email Unsubscribe
```xml
element POSTBACK {
    element ORIGIN { "EMAIL_SUB" } &
    element CODE { "N304" } &
    element EMAIL { text } &
    element CAMPAIGNID { text }
}
```