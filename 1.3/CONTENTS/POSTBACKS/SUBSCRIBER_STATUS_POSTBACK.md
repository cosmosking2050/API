[Back to the Table of Contents](/1.3/README.md)

## Subscriber Status Postback

The Subscribe / Unsubscribe Postback API notifies you of the an opt-in or opt-out status change for each number or email address subscribed to your campaigns. 

### Mobile Subscribe

This postback notification triggers when a mobile phone number subscribes to a specific campaign.  We send the notification again even if someone who is already opt-in triggers the opt-in process a second time.

| Variable | Description |
| -------- | ----------- |
| CODE | N301. |
| ORIGIN | SUB. | 
| MOBILE | Subscriber's mobile number. |
| CAMPAIGNID | ID of the campaign. |
| TIMESTAMP | Timestamp of the subscription. |
| SHORTCODE | The shortcode. | 
| CAMPAIGNTITLE | The title of the campaign |
| BRANDNAME | The brand name associated with the account or campaign |
| SOURCE | The source of the subscription: MANAGER, API, MO, WEB. MANAGER indicates the number was imported or manually added in your campaign audience manager. API indicates it came from a subscribe call to our API. MO indicates the phone number opted-in by texting campaign keyword. WEB indicates they subscribed via mobile web landing page. |

```xml
<?xml version='1.0'?>
<POSTBACK>
    <ORIGIN>SUB</ORIGIN>
    <CODE>N301</CODE>
    <MOBILE>16501112222</MOBILE>
    <CAMPAIGNID>1478</CAMPAIGNID>
    <TIMESTAMP>2014-07-02 14:32:23-04</TIMESTAMP>
    <SHORTCODE>123456</SHORTCODE>
    <CAMPAIGNTITLE>My Campaign Name</CAMPAIGNTITLE>
    <BRANDNAME>My Brand Name</BRANDNAME>
    <SOURCE>API</SOURCE>
</POSTBACK>
```

```xml
element POSTBACK {
    element ORIGIN { text } &
    element CODE { text } &
    element MOBILE { text } &
    element CAMPAIGNID { text } &
    element TIMESTAMP { text } &
    element SHORTCODE { text } &
    element CAMPAIGNTITLE { text } &
    element BRANDNAME { text } &
    element SOURCE { text }
}
```

### Mobile Unsubscribe

This postback notification triggers when a mobile phone number unsubscribes to a specific campaign.

| Variable | Description |
| -------- | ----------- |
| CODE | N302. |
| ORIGIN | SUB. | 
| MOBILE | Subscriber's mobile number. |
| CAMPAIGNID | ID of the campaign. |
| TIMESTAMP | Timestamp of the unsubscription. |
| SHORTCODE | The shortcode. | 
| CAMPAIGNTITLE | The title of the campaign |
| BRANDNAME | The brand name associated with the account or campaign |
| SOURCE | The source of the unsubscription: MANAGER, API, MO, IMPORTED AS UNSUBSCRIBED. MANAGER indicates the number was deported or manually removed in your campaign audience manager. API indicates it came from a unsubscribe call to our API. MO indicates the phone number opted-out by texting STOP. IMPORTED AS UNSUBSCRIBED indicates the number was attempted to be imported or manually added, but was imported as unsubscribed due to a previous opt-out. |

```xml
<?xml version='1.0'?>
<POSTBACK>
    <ORIGIN>SUB</ORIGIN>
    <CODE>N302</CODE>
    <MOBILE>16502424956</MOBILE>
    <CAMPAIGNID>1478</CAMPAIGNID>
    <TIMESTAMP>2014-07-02 14:32:23-04</TIMESTAMP>
    <SHORTCODE>123456</SHORTCODE>
    <CAMPAIGNTITLE>My Campaign Name</CAMPAIGNTITLE>
    <BRANDNAME>My Brand Name</BRANDNAME>
    <SOURCE>API</SOURCE>  
</POSTBACK>
```

```xml
element POSTBACK {
    element ORIGIN { text } &
    element CODE { text } &
    element MOBILE { text } &
    element CAMPAIGNID { text } &
    element TIMESTAMP { text } &
    element SHORTCODE { text } &
    element CAMPAIGNTITLE { text } &
    element BRANDNAME { text } &
    element SOURCE { text }
}
```

### Email Subscribe

This postback notification triggers when an email address subscribes to a specific campaign.

| Variable | Description |
| -------- | ----------- |
| CODE | N303. |
| ORIGIN | EMAIL_SUB. | 
| EMAIL | Subscriber's email. |
| CAMPAIGNID | ID of the campaign. |

```xml
<?xml version='1.0'?>
<POSTBACK>
  <ORIGIN>EMAIL_SUB</ORIGIN>
  <CODE>N303</CODE>
  <EMAIL>info@skycore.com</EMAIL>
  <CAMPAIGNID>89</CAMPAIGNID>
</POSTBACK>
```

```xml
element POSTBACK {
    element ORIGIN { text } &
    element CODE { text } &
    element EMAIL { text } &
    element CAMPAIGNID { text }
}
```

### Email Unsubscribe

This postback notification triggers when an email address unsubscribes to a specific campaign.

| Variable | Description |
| -------- | ----------- |
| CODE | N304. |
| ORIGIN | EMAIL_SUB. | 
| EMAIL | Email address of the subscriber. |
| CAMPAIGNID | The ID of the campaign. |

```xml
<?xml version='1.0'?>
<POSTBACK>
  <ORIGIN>EMAIL_SUB</ORIGIN>
  <CODE>N304</CODE>
  <EMAIL>info@skycore.com</EMAIL>
  <CAMPAIGNID>89</CAMPAIGNID>
</POSTBACK>
```

```xml
element POSTBACK {
    element ORIGIN { text } &
    element CODE { text } &
    element EMAIL { text } &
    element CAMPAIGNID { text }
}
```