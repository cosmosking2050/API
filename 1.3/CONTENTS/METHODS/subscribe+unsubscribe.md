[Back to the Table of Contents](/1.3/README.md)&nbsp;&nbsp;|&nbsp;&nbsp;[Back to API Methods](API_METHODS.md)
## subscribe + unsubscribe

__Synopsis:__  
This API will subscribe or unsubscribe users to a particular campaign. Once a user is subscribed to a campaign they will receive all auto responders and scheduled messages for that campaign until they are unsubscribed through the API or through normal STOP or STOP ALL SMS request. You may not re-subscribe someone who has unsubscribed themselves from a campaign. You may re-subscribe someone who you have unsubscribed through the API.

__Request: subscribe__
```xml
<REQUEST>
  <ACTION>subscribe</ACTION>
    <API_KEY>API KEY</API_KEY>
    <CAMPAIGNID>Campaign ID</CAMPAIGNID>
    <MOBILE>Number to subscribe</MOBILE>
    <DATA>
        <FIRST_NAME>First Name</FIRST_NAME>
        <LAST_NAME>Last Name</LAST_NAME>
        <GENDER>Gender</GENDER>
        ...
    </DATA>   
    <NOTIFY>'yes/no' on whether to notify user on successful opt in</NOTIFY>
    <SPID> the carrier ID </SPID>
    <CTA>'yes/no' to request double opt in from the user to opt-in</CTA>
        <TIMEZONE>Timezone abbreviation: EST, CST, MST, PST, etc.</TIMEZONE>
</REQUEST>
```

__Request: unsubscribe__
```xml
<REQUEST>
    <ACTION>unsubscribe</ACTION>
    <API_KEY>API KEY</API_KEY>
    <CAMPAIGNID>Campaign ID</CAMPAIGNID>
    <MOBILE>Number to unsubscribe</MOBILE>
    <NOTIFY>'yes/no' on whether to notify user on opt-out</NOTIFY>
</REQUEST>
```

__Request Parameters:__

    Mandatory: Action, API_KEY, CAMPAIGNID, Mobile
    Optional: CTA, Notify, SPID, TZ

__Response Parameters:__

    CAMPAIGNID, Errorcode, Errorinfo, mobile, Status

__Related Errorcodes:__

    E901, E902, E903, E904, E905

__Request Example:__  
XML:
```xml
<REQUEST>
    <ACTION>subscribe</ACTION>
    <API_KEY>qTFkykO9JTfahCOqJ0V2Wf5Cg1t8iWlZ</API_KEY>
    <CAMPAIGNID>1116</CAMPAIGNID>
    <MOBILE>16502426055</MOBILE>
    <DATA>
        <FIRST_NAME>John</FIRST_NAME>
        <LAST_NAME>Smith</LAST_NAME>
        <AGE>29</AGE>
        <PET>Dog</PET>
    </DATA>   
    <NOTIFY>no</NOTIFY>
    <CTA>no</ CTA>
</REQUEST>
```

GET:

    https://secure.skycore.com/API/wxml/1.3/index.php?action=subscribe&api_key=qTFkykO9JTfahCOqJ0V2Wf5Cg1t8iWlZ
    &mobile=16502426055&campaignid=1116&notify=no&cta=no&data_first_name=John&data_last_name=Smith&data_age=29&
    data_pet=Dog
    
__Response Example: Success__
```xml
<RESPONSE>
    <STATUS>Success</STATUS>
    <CAMPAIGNID>1116</CAMPAIGNID>
    <MOBILE>16502426055</MOBILE>
</RESPONSE>
```

__Response Example: Failure__
```xml
<RESPONSE>
    <STATUS>Failure</STATUS>
    <ERRORCODE>E903</ERRORCODE>
    <ERRORINFO> Invalid CAMPAIGNID </ERRORINFO>
</RESPONSE>
```

__Postback Notifications__  
Upon subscribing/unsubscribing a number the system will generate a notification.

__On subscribe:__
```xml
<NOTIFICATION id="325" created="2011-01-01 20:09:12.975911-04">
    <ORIGIN>SUB</ORIGIN>
    <CODE>N301</CODE>
    <BODY>
        <MOBILE>16502426055</MOBILE>
        <CAMPAIGNID>1116</CAMPAIGNID>
    </BODY>
</NOTIFICATION>
```

__On unsubscribe:__
```xml
<NOTIFICATION id="325" created="2011-01-01 20:09:12.975911-04">
    <ORIGIN>SUB</ORIGIN>
    <CODE>N302</CODE>
    <BODY>
        <MOBILE>16502426055</MOBILE>
        <CAMPAIGNID>1116</CAMPAIGNID>
    </BODY>
</NOTIFICATION>
```
