[Back to the Table of Contents](/1.3/README.md)

## getPassTemplate

__Synopsis:__  
This API function returns the pass template information when given passTemplateId or mmsId or emailId.

__Request: XML__
```xml
<REQUEST>
    <ACTION>getPassTemplate</ACTION>
    <API_KEY>apiKey</API_KEY>
    <PASSTEMPLATEID>passTemplateId</PASSTEMPLATEID>
</REQUEST>
```

```xml
<REQUEST>
    <ACTION>getPassTemplate</ACTION>
    <API_KEY>apiKey</API_KEY>
    <MMSID>mmsId</MMSID>
</REQUEST>
```

```xml
<REQUEST>
    <ACTION>getPassTemplate</ACTION>
    <API_KEY>apiKey</API_KEY>
    <EMAILID>emailId</EMAILID>
</REQUEST>
```

__Request: GET__
<pre>API_URL?action=getpasstemplate&amp;api_key=apiKey&amp;passtemplateid=passTemplateId</pre>
<pre>API_URL?action=getpasstemplate&amp;api_key=apiKey&amp;emailid=emailId</pre>
<pre>API_URL?action=getpasstemplate&amp;api_key=apiKey&amp;mmsid=mmsId</pre>

__Request Parameters:__

    Mandatory: action, api_key, passTemplateId, mmsId, emailId
    Optional: N/A

__Response Parameters:__

    status, passTemplateId, passTemplate, errorCode, errorInfo

__Related Error Codes:__

    E174, E402, E802, E822, E823, E828, E827

__Request Example:__
```xml
<REQUEST>
    <ACTION>getPassTemplateIds</ACTION>
    <API_KEY>qTFkykO9JTfahCOqJ0V2Wf5Cg1t8iWlZ</API_KEY>
    <PASSTEMPLATEID>234</PASSTEMPLATEID>
</REQUEST>
```

__Response Example: Success__
```xml
<RESPONSE>
    <STATUS>Success</STATUS>
    <PASSTEMPLATEID>1233</PASSTEMPLATEID>
    <PASSTEMPLATE>
        <PASSNAME>PizzaCoupon-X12</PASSNAME>
        <PASSTYPE>Coupon</PASSTYPE>
        <ORGANIZATION>Pizza Den</ORGANIZATION>
        <DESCRIPTION>$10 off $35 purchase</DESCRIPTION>
        <BARCODEVALUE>XXXX-XXXX</BARCODEVALUE>
        <BARCODETEXT>XXXX-XXXX</BARCODETEXT>
        <HEADERFIELDS>1</HEADERFIELDS>
        <HEADERLABEL1></HEADERLABEL1>
        <HEADERVALUE1></HEADERVALUE1>
        <PRIMARYFIELDS>1</PRIMARYFIELDS>
        <PRIMARYLABEL1>$10 off $35</PRIMARYLABEL1>
        <PRIMARYVALUE1>(Conditions apply.)</PRIMARYVALUE1> 
        <SECFIELDS>1</SECFIELDS>
        <SECLABEL1>Expires</SECLABEL1>
        <SECVALUE1>July 31, 2013</SECVALUE1>
        <AUXFIELDS>1</AUXFIELDS>
        <AUXLABEL1>Terms</AUXLABEL1>
        <AUXVALUE1>Excludes TX,FL,RI,VT,UT,WA,WI</AUXVALUE1>
        <BACKFIELDS>1</BACKFIELDS>
        <BACKLABEL1>Terms and Conditions</BACKLABEL1>
        <BACKVALUE1>1 coupon valid for one family.</BACKVALUE1>
    </PASSTEMPLATE>
</RESPONSE>
```

__Response Example: Failure__
```xml
<RESPONSE>
    <STATUS>Failure</STATUS>
    <ERRORCODE>E802</ERRORCODE>
    <ERRORINFO>Invalid 'PassTemplateID'. Pass template is either deleted or do not belong to this user</ERRORINFO>
</RESPONSE>
```