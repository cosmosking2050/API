<a href="/1.3/README.md">Back to the Table of Contents</a>&nbsp;&nbsp;|&nbsp;&nbsp;<a href="/1.3/CONTENTS/POSTBACKS/POSTBACK_SYSTEM_OVERVIEW.md">Postback System Overview</a>

<h2>Subscribe and Unsubscribe Postbacks</h2>

The Subscribe / Unsubscribe Postback API notifies you of the an opt-in or opt-out status change for each number or email address subscribed to your campaigns. 

<a name="MobileSub"><strong>Mobile Subscribe</strong></a>

This postback notification triggers when a mobile phone number subscribes to a specific campaign.

| Variable | Description |
| -------- | ----------- |
| CODE | N301|
| ORIGIN | SUB | 
| MOBILE | subscriber's mobile |
| CAMPAIGNID | ID of the campaign |
| SUBID | subscription ID |

```xml
<?xml version='1.0'?>
<POSTBACK xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:noNamespaceSchemaLocation ="https://www.skycore.com/platform/platform/schema/pass-postback.xsd">
  <ORIGIN>SUB</ORIGIN>
  <CODE>N301</CODE>
  <MOBILE>16501112222</MOBILE>
  <CAMPAIGNID>1478</CAMPAIGNID>
  <SUBID>656655</SUBID>
</POSTBACK>
```

<a name="MobileUnsub"><strong>Mobile Unsubscribe</strong></a>
This postback notification triggers when a mobile phone number unsubscribes to a specific campaign.

| Variable | Description |
| -------- | ----------- |
| CODE | N302 |
| ORIGIN | SUB | 
| MOBILE | subscriber's mobile |
| CAMPAIGNID | ID of the campaign |
| SUBID | subscription ID |

```xml
<?xml version='1.0'?>
<POSTBACK xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:noNamespaceSchemaLocation ="https://www.skycore.com/platform/platform/schema/pass-postback.xsd">
  <ORIGIN>SUB</ORIGIN>
  <CODE>N302</CODE>
  <MOBILE>16502424956</MOBILE>
  <CAMPAIGNID>1478</CAMPAIGNID>
  <SUBID>656655</SUBID>
</POSTBACK>
```

<a name="EmailSub"><strong>Email Subscribe</strong></a>
This postback notification triggers when an email address subscribes to a specific campaign.</p>

| Variable | Description |
| -------- | ----------- |
| CODE | N303 |
| ORIGIN | EMAIL_SUB | 
| EMAIL | subscriber's mobile |
| CAMPAIGNID | ID of the campaign |
| SUBID | subscription ID |

```xml
<?xml version='1.0'?>
<POSTBACK xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:noNamespaceSchemaLocation ="https://www.skycore.com/platform/platform/schema/pass-postback.xsd">
  <ORIGIN>EMAIL_SUB</ORIGIN>
  <CODE>N303</CODE>
  <EMAIL>info@skycore.com</EMAIL>
  <CAMPAIGNID>89</CAMPAIGNID>
  <SUBID>12913</SUBID>
</POSTBACK>
```

<a name="EmailUnsub"><strong>Email Unsubscribe</strong></a>
This postback notification triggers when an email address unsubscribes to a specific campaign.</p>

| Variable | Description |
| -------- | ----------- |
| CODE | N304 |
| ORIGIN | EMAIL_SUB | 
| EMAIL | subscriber's mobile |
| CAMPAIGNID | ID of the campaign |
| SUBID | subscription ID |

```xml
<?xml version='1.0'?>
<POSTBACK xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:noNamespaceSchemaLocation ="https://www.skycore.com/platform/platform/schema/pass-postback.xsd">
  <ORIGIN>EMAIL_SUB</ORIGIN>
  <CODE>N304</CODE>
  <EMAIL>info@skycore.com</EMAIL>
  <CAMPAIGNID>89</CAMPAIGNID>
  <SUBID>12913</SUBID>
</POSTBACK>
```
