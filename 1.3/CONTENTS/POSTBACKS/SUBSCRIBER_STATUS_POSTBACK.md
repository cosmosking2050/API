[Back to the Table of Contents](/1.3/README.md)&nbsp;&nbsp;|&nbsp;&nbsp;[Postback System Overview](/1.3/CONTENTS/POSTBACKS/POSTBACK_SYSTEM_OVERVIEW.md)
## Subscriber Status Postback

The Subscribe / Unsubscribe Postback API notifies you of the an opt-in or opt-out status change for each number or email address subscribed to your campaigns. 

### Mobile Subscribe

This postback notification triggers when a mobile phone number subscribes to a specific campaign.

| Variable | Description |
| -------- | ----------- |
| CODE | N301. |
| ORIGIN | SUB. | 
| MOBILE | Subscriber's mobile number. |
| CAMPAIGNID | ID of the campaign. |

```xml
<?xml version='1.0'?>
<POSTBACK>
  <ORIGIN>SUB</ORIGIN>
  <CODE>N301</CODE>
  <MOBILE>16501112222</MOBILE>
  <CAMPAIGNID>1478</CAMPAIGNID>
</POSTBACK>
```

### Mobile Unsubscribe

This postback notification triggers when a mobile phone number unsubscribes to a specific campaign.

| Variable | Description |
| -------- | ----------- |
| CODE | N302. |
| ORIGIN | SUB. | 
| MOBILE | Subscriber's mobile number. |
| CAMPAIGNID | ID of the campaign. |


```xml
<?xml version='1.0'?>
<POSTBACK>
  <ORIGIN>SUB</ORIGIN>
  <CODE>N302</CODE>
  <MOBILE>16502424956</MOBILE>
  <CAMPAIGNID>1478</CAMPAIGNID>
</POSTBACK>
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
