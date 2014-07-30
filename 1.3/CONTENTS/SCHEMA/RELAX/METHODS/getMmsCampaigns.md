REQUEST

```xml
element REQUEST {
    element ACTION { "getMmsCampaigns" } &
    element API_KEY { text }
}
```

RESPONSE

```xml
element RESPONSE {
    element STATUS { text } &
    element MMSCAMPAIGNS {
        element CAMPAIGN {
            element ID { text } &
            element NAME { text }
        }+
    }? &
    element ERRORCODE { text }? &
    element ERRORINFO { text }?
}
```