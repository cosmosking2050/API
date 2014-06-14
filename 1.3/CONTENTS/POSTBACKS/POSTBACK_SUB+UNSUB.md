<a href="/1.3/README.md">Back to the Table of Contents</a>&nbsp;&nbsp;|&nbsp;&nbsp;<a href="/1.3/CONTENTS/POSTBACKS/POSTBACK_SYSTEM_OVERVIEW.md">Postback System Overview</a>

<h2>Subscribe and Unsubscribe Postbacks</h2>

The Subscribe / Unsubscribe Postback API notifies you of the an opt-in or opt-out status change for each number or email address subscribed to your campaigns. 

<h3>Mobile Subscribe</h3>

This postback notification triggers when a mobile phone number subscribes to a specific campaign.

| Variable | Description |
| -------- | ----------- |
| CODE | N301|
| ORIGIN | SUB | 
| MOBILE | subscriber's mobile number|
| CAMPAIGNID | ID of the campaign |
| SUBID | subscription ID |

```xml
<?xml version='1.0'?>
<POSTBACK>
  <ORIGIN>SUB</ORIGIN>
  <CODE>N301</CODE>
  <MOBILE>16501112222</MOBILE>
  <CAMPAIGNID>1478</CAMPAIGNID>
  <SUBID>656655</SUBID>
</POSTBACK>
```

<h3>Mobile Unsubscribe</h3>
This postback notification triggers when a mobile phone number unsubscribes to a specific campaign.

| Variable | Description |
| -------- | ----------- |
| CODE | N302 |
| ORIGIN | SUB | 
| MOBILE | subscriber's mobile number |
| CAMPAIGNID | ID of the campaign |
| SUBID | subscription ID |

```xml
<?xml version='1.0'?>
<POSTBACK>
  <ORIGIN>SUB</ORIGIN>
  <CODE>N302</CODE>
  <MOBILE>16502424956</MOBILE>
  <CAMPAIGNID>1478</CAMPAIGNID>
  <SUBID>656655</SUBID>
</POSTBACK>
```

<h3>Email Subscribe</h3>
This postback notification triggers when an email address subscribes to a specific campaign.</p>

| Variable | Description |
| -------- | ----------- |
| CODE | N303 |
| ORIGIN | EMAIL_SUB | 
| EMAIL | subscriber's emai |
| CAMPAIGNID | ID of the campaign |
| SUBID | subscription ID |

```xml
<?xml version='1.0'?>
<POSTBACK>
  <ORIGIN>EMAIL_SUB</ORIGIN>
  <CODE>N303</CODE>
  <EMAIL>info@skycore.com</EMAIL>
  <CAMPAIGNID>89</CAMPAIGNID>
  <SUBID>12913</SUBID>
</POSTBACK>
```

<h3>Email Unsubscribe</h3>

This postback notification triggers when an email address unsubscribes to a specific campaign.</p>

| Variable | Description |
| -------- | ----------- |
| CODE | N304 |
| ORIGIN | EMAIL_SUB | 
| EMAIL | email address of the subscriber |
| CAMPAIGNID | The ID of the campaign |
| SUBID | subscription ID |

```xml
<?xml version='1.0'?>
<POSTBACK>
  <ORIGIN>EMAIL_SUB</ORIGIN>
  <CODE>N304</CODE>
  <EMAIL>info@skycore.com</EMAIL>
  <CAMPAIGNID>89</CAMPAIGNID>
  <SUBID>12913</SUBID>
</POSTBACK>
```
