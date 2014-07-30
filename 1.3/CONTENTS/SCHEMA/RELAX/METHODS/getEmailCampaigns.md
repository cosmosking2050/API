REQUEST

```xml
element REQUEST {
    element ACTION { "getEmailCampaigns" } &
    element API_KEY { text }
}
```

RESPONSE

```xml
element RESPONSE {
    element STATUS { text } &
    element EMAILCAMPAIGNS {
        element CAMPAIGN {
            element ID { text } &
            element NAME { text }
        }+
    }? &
    element ERRORCODE { text }? &
    element ERRORINFO { text }?
}
```