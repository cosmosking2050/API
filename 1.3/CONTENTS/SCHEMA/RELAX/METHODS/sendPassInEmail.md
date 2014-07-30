[Back to the Table of Contents](/1.3/README.md)

## sendPassInEmail

__Synopsis:__  
'sendPassInEmail' API triggers sending a stored email template with embedded Passbook Pass in it. Pass data passed in the API will be used to create this passbook pass. The pass data gets locked with the email address in the request and is used in limitation to the pass template settings. All the other/extra pass data is ignored. Custom pass ID is your system generated unique ID that will represent this pass data. In the case of Relevance, Relevant Text is considered only when Relevance Lat and Long values are passed in the API otherwise ignored. Also, it requires a reference email campaign to which this email address will be subscribed to. If any case, the subscription fails then the email address is added to the email campaign's audience manager as 'unsubscribed'. Subscription to the campaign may fail if:

1. The *email address* has already opted-out of a campaign in your account.
2. The *email address* has unsubscribed from any campaign associated with the SMTP server you are using.
3. The *email address* has filed a spam complaint.
4. The *email address* bounced during a previous delivery.


On success, it will return the tracking ID referenced by 'TRACKINGID'. For more info see below for Mandatory/Optional fields and Error codes.  
The email template is referenced by 'EMAILTEMPLATEID', email address is referenced by 'EMAIL', email campaign is referenced by CAMPAIGNID and the pass data is referenced by PASSDATA in the API.

__Request: XML__
```xml
<REQUEST>
    <ACTION>sendPassInEmail</ACTION>
    <API_KEY>apiKey</API_KEY>
    <EMAILTEMPLATEID>emailTemplateId</EMAILTEMPLATEID>
    <EMAIL>email</EMAIL>
    <CAMPAIGNID>campaignId</CAMPAIGNID>
    <DATA>
        <FIRST_NAME>First Name</FIRST_NAME>
        <LAST_NAME>Last Name</LAST_NAME>
        <GENDER>Gender</GENDER>
        ...
    </DATA>
    <PASSDATA>
        <CUSTOMPASSID>customPassId</CUSTOMPASSID>
        <THUMBNAILURL>thumbnailUrl</THUMBNAILURL>
        <BARCODEVALUE>barcodeValue</BARCODEVALUE>
        <BARCODETEXT>barcodeText</BARCODETEXT>
        <HEADERLABEL1>headerLabel1</HEADERLABEL1>
        <HEADERVALUE1>headerValue1</HEADERVALUE1>
        <PRIMARYLABEL1>primaryLabel1</PRIMARYLABEL1>
        <PRIMARYVALUE1>primaryValue1</PRIMARYVALUE1> 
        <PRIMARYLABEL2>primaryLabel2</PRIMARYLABEL2>
        <PRIMARYVALUE2>primaryValue2</PRIMARYVALUE2> 
        <SECLABEL1>secLabel1</SECLABEL1>
        <SECVALUE1>secValue1</SECVALUE1>
        <SECLABEL2>sedLabel2</SECLABEL2>
        <SECVALUE2>secValue2</SECVALUE2>
        <SECLABEL3>sedLabel3</SECLABEL3>
        <SECVALUE3>secValue3</SECVALUE3>
        <SECLABEL4>sedLabel4</SECLABEL4>
        <SECVALUE4>secValue4</SECVALUE4>
        <AUXLABEL1>auxLabel1</AUXLABEL1>
        <AUXVALUE1>auxValue1</AUXVALUE1>
        <AUXLABEL2>auxLabel2</AUXLABEL2>
        <AUXVALUE2>auxValue2</AUXVALUE2>
        <AUXLABEL3>auxLabel3</AUXLABEL3>
        <AUXVALUE3>auxValue3</AUXVALUE3>
        <AUXLABEL4>auxLabel4</AUXLABEL4>
        <AUXVALUE4>auxValue4</AUXVALUE4>
        <BACKLABEL1>backLabel1</BACKLABEL1>
        <BACKVALUE1>backValue1</BACKVALUE1>
        <BACKLABEL2>backLabel2</BACKLABEL2>
        <BACKVALUE2>backValue2</BACKVALUE2>
        <BACKLABEL3>backLabel3</BACKLABEL3>
        <BACKVALUE3>backValue3</BACKVALUE3>
        <BACKLABEL4>backLabel4</BACKLABEL4>
        <BACKVALUE4>backValue4</BACKVALUE4>
        <RELLATITUDE1>relLatitude1</RELLATITUDE1>
        <RELLONGITUDE1>relLongitude1</RELLONGITUDE1>
        <RELTEXT1>relText1</RELTEXT1>
        <RELLATITUDE2>relLatitude2</RELLATITUDE2>
        <RELLONGITUDE2>relLongitude2</RELLONGITUDE2>
        <RELTEXT2>relText2</RELTEXT2>
        <RELLATITUDE3>relLatitude3</RELLATITUDE3>
        <RELLONGITUDE3>relLongitude3</RELLONGITUDE3>
        <RELTEXT3>relText3</RELTEXT3>
        <RELLATITUDE4>relLatitude4</RELLATITUDE4>
        <RELLONGITUDE4>relLongitude4</RELLONGITUDE4>
        <RELTEXT4>relText4</RELTEXT4>
        <RELLATITUDE5>relLatitude5</RELLATITUDE5>
        <RELLONGITUDE5>relLongitude5</RELLONGITUDE5>
        <RELTEXT5>relText5</RELTEXT5>
        <RELLATITUDE6>relLatitude6</RELLATITUDE6>
        <RELLONGITUDE6>relLongitude6</RELLONGITUDE6>
        <RELTEXT6>relText6</RELTEXT6>
        <RELLATITUDE7>relLatitude7</RELLATITUDE7>
        <RELLONGITUDE7>relLongitude7</RELLONGITUDE7>
        <RELTEXT7>relText7</RELTEXT7>
        <RELLATITUDE8>relLatitude8</RELLATITUDE8>
        <RELLONGITUDE8>relLongitude8</RELLONGITUDE8>
        <RELTEXT8>relText8</RELTEXT8>
        <RELLATITUDE9>relLatitude9</RELLATITUDE9>
        <RELLONGITUDE9>relLongitude9</RELLONGITUDE9>
        <RELTEXT9>relText9</RELTEXT9>
        <RELLATITUDE10>relLatitude10</RELLATITUDE10>
        <RELLONGITUDE10>relLongitude10</RELLONGITUDE10>
        <RELTEXT10>relText10</RELTEXT10>
    </PASSDATA>    
</REQUEST>
```

__Request: GET__

    API_URL?action=sendpassinemail&api_key=apiKey&emailtemplateid=emailTemplateId
    &email=email&campaignid=campaignId
    &data_first_name=firstName&data_last_name=lastname&data_age=age
    &pd_custompassid=customPassId&pd_thumbnailurl=thumbnailUrl
    &pd_barcodevalue=barcodeValue
    &pd_barcodetext=barcodeText&pd_headerlabel1=headerLabel1
    &pd_headervalue1=headerValue1&pd_primarylabel1=primaryLabel1
    &pd_primaryvalue1=primaryValue1&pd_primarylabel2=primaryLabel2
    &pd_primaryvalue2=primaryValue2&pd_seclabel1=secLabel1&pd_secvalue1=secValue1
    &pd_seclabel2=secLabel2&pd_secvalue2=secValue2&pd_seclabel3=secLabel3
    &pd_secvalue3=secValue3&pd_seclabel4=secLabel4&pd_secvalue4=secValue4
    &pd_auxlabel1=auxLabel1&pd_auxvalue1=auxValue1&pd_auxlabel2=auxLabel2
    &pd_auxvalue2=auxValue2&pd_auxlabel3=auxLabel3&pd_auxvalue3=auxValue3
    &pd_auxlabel4=auxLabel4&pd_auxvalue4=auxValue4&pd_backlabel1=backLabel1
    &pd_backvalue1=backValue1&pd_backlabel2=backLabel2&pd_backvalue2=backValue2
    &pd_backlabel3=backLabel3&pd_backvalue3=backValue3&pd_backlabel4=backLabel4&pd_backvalue4=backValue4
    &pd_rellatitude1=relLatitude1&pd_rellongitude1=relLongitude1&pd_reltext1=relText1
    &pd_rellatitude2=relLatitude2&pd_rellongitude2=relLongitude2&pd_reltext2=relText2
    &pd_rellatitude3=relLatitude3&pd_rellongitude3=relLongitude3&pd_reltext3=relText3
    &pd_rellatitude4=relLatitude4&pd_rellongitude4=relLongitude4&pd_reltext4=relText4
    &pd_rellatitude5=relLatitude5&pd_rellongitude5=relLongitude5&pd_reltext5=relText5
    &pd_rellatitude6=relLatitude6&pd_rellongitude6=relLongitude6&pd_reltext6=relText6
    &pd_rellatitude7=relLatitude7&pd_rellongitude7=relLongitude7&pd_reltext7=relText7
    &pd_rellatitude8=relLatitude8&pd_rellongitude8=relLongitude8&pd_reltext8=relText8
    &pd_rellatitude9=relLatitude9&pd_rellongitude9=relLongitude9&pd_reltext9=relText9
    &pd_rellatitude10=relLatitude10&pd_rellongitude10=relLongitude10&pd_reltext10=relText10

__Request Parameters:__

    Mandatory: action, api_key, email, emailTemplateId, campaignId,
    barcodeValue (if "Barcode=Allowed" &amp;&amp; "BarcodeType=Dynamic" &amp;&amp; "BarcodeValueSource=Dynamic Value" for Pass Template otherwise IGNORED)
    Optional: data, customPassId, thumbnailUrl,
    barcodeText (if "Barcode = Allowed" && "Barcode Alternate Text = Dynamic Text" for Pass Template otherwise IGNORED), 
    headerLabel1, headerValue1, 
    primaryLabel1, primaryValue1, 
    primaryLabel2, primaryValue2 - if "Pass Template Type = Boarding Pass" otherwise IGNORED, 
    secLabel1, secValue1, secLabel2, secValue2, secLabel3, secValue3, secLabel4, secValue4, 
    auxLabel1, auxValue1, auxLabel2, auxValue2, auxLabel3, auxValue3, auxLabel4, auxValue4, 
    backLabel1, backValue1, backLabel2, backValue2, backLabel3, backValue3, backLabel4, backValue4,
    relLatitude1, relLongitude1, relText1,
    relLatitude2, relLongitude2, relText2,
    relLatitude3, relLongitude3, relText3,
    relLatitude4, relLongitude4, relText4,
    relLatitude5, relLongitude5, relText5,
    relLatitude6, relLongitude6, relText6,
    relLatitude7, relLongitude7, relText7,
    relLatitude8, relLongitude8, relText8,
    relLatitude9, relLongitude9, relText9,
    relLatitude10, relLongitude10, relText10

```xml
element REQUEST {
    element ACTION { "sendPassInEmail" } &
    element API_KEY { text } &
    element EMAILTEMPLATEID { text } &
    element EMAIL { text } &
    element CAMPAIGNID { text } &
    element DATA {
        element FIRST_NAME { text }? &
        element LAST_NAME { text }? &
        element GENDER { text }? &
        ...
    }? &
    element PASSDATA {
        element CUSTOMPASSID { text }? &
        element THUMBNAILURL { text }? &
        element BARCODEVALUE { text } &
        element BARCODETEXT { text }? &
        element HEADERLABEL1 { text }? &
        element HEADERVALUE1 { text }? &
        element PRIMARYLABEL1 { text }? &
        element PRIMARYVALUE1  { text }? &
        element PRIMARYLABEL2 { text }? &
        element PRIMARYVALUE2  { text }? &
        element SECLABEL1 { text }? &
        element SECVALUE1 { text }? &
        element SECLABEL2 { text }? &
        element SECVALUE2 { text }? &
        element SECLABEL3 { text }? &
        element SECVALUE3 { text }? &
        element SECLABEL4 { text }? &
        element SECVALUE4 { text }? &
        element AUXLABEL1 { text }? &
        element AUXVALUE1 { text }? &
        element AUXLABEL2 { text }? &
        element AUXVALUE2 { text }? &
        element AUXLABEL3 { text }? &
        element AUXVALUE3 { text }? &
        element AUXLABEL4 { text }? &
        element AUXVALUE4 { text }? &
        element BACKLABEL1 { text }? &
        element BACKVALUE1 { text }? &
        element BACKLABEL2 { text }? &
        element BACKVALUE2 { text }? &
        element BACKLABEL3 { text }? &
        element BACKVALUE3 { text }? &
        element BACKLABEL4 { text }? &
        element BACKVALUE4 { text }? &
        element RELLATITUDE1 { text }? &
        element RELLONGITUDE1 { text }? &
        element RELTEXT1 { text }? &
        element RELLATITUDE2 { text }? &
        element RELLONGITUDE2 { text }? &
        element RELTEXT2 { text }? &
        element RELLATITUDE3 { text }? &
        element RELLONGITUDE3 { text }? &
        element RELTEXT3 { text }? &
        element RELLATITUDE4 { text }? &
        element RELLONGITUDE4 { text }? &
        element RELTEXT4 { text }? &
        element RELLATITUDE5 { text }? &
        element RELLONGITUDE5 { text }? &
        element RELTEXT5 { text }? &
        element RELLATITUDE6 { text }? &
        element RELLONGITUDE6 { text }? &
        element RELTEXT6 { text }? &
        element RELLATITUDE7 { text }? &
        element RELLONGITUDE7 { text }? &
        element RELTEXT7 { text }? &
        element RELLATITUDE8 { text }? &
        element RELLONGITUDE8 { text }? &
        element RELTEXT8 { text }? &
        element RELLATITUDE9 { text }? &
        element RELLONGITUDE9 { text }? &
        element RELTEXT9 { text }? &
        element RELLATITUDE10 { text }? &
        element RELLONGITUDE10 { text }? &
        element RELTEXT10 { text }?
    }
}
```

__Response Parameters:__

    status, emailTemplateId, trackingId, email, campaignId, errorCode, errorInfo

```xml
element RESPONSE {
    element STATUS { text } &
    element EMAILTEMPLATEID { text }? &
    element TRACKINGID { text }? &
    element EMAIL { text }? &
    element CAMPAIGNID { text }? &
    element ERRORCODE { text }? &
    element ERRORINFO { text }?
}
```

__Related Error Codes:__

    E401, E402, E713, E714, E802, E803, E806, E823, E840, E841, E842, E843, E844, E845, E846, E847, E848, E849, E850,
    E851, E852, E853, E854, E855, E856, E857, E858, E859, E860, E861, E862, E863, E864, E865, E866, E867, E868, E869,
    E870, E871, E872, E873, E874, E875, E876, E877, E878, E879, E880, E881, E882, E883, E884, E885, E886, E887, E888,
    E889, E890, E891, E892, E893, E894, E895, E896, E897, E898, E899, E915, E916, E917

__Request Example:__
```xml
<REQUEST>
    <ACTION>sendPassInEmail</ACTION>
    <API_KEY>qTFkykO9JTfahCOqJ0V2Wf5Cg1t8iWlZ</API_KEY>
    <EMAILTEMPLATEID>45633</EMAILTEMPLATEID>
    <EMAIL>vik.muth@mail.com</EMAIL>
    <CAMPAIGNID>1233</CAMPAIGNID>
    <DATA>
        <FIRST_NAME>John</FIRST_NAME>
        <LAST_NAME>Smith</LAST_NAME>
        <AGE>29</AGE>
        <PET>Dog</PET>
    </DATA>
    <PASSDATA>
        <THUMBNAILURL>http://andreas.com/pixs/steve-jobs.png</THUMBNAILURL>
        <BARCODEVALUE>1234578961A</BARCODEVALUE>
        <BARCODETEXT>PASS-123-457</BARCODETEXT>
        <HEADERLABEL1>SEAT</HEADERLABEL1>
        <HEADERVALUE1>1C</HEADERVALUE1>
        <PRIMARYLABEL1>Name</PRIMARYLABEL1>
        <PRIMARYVALUE1>Vikram Muthyala</PRIMARYVALUE1> 
        <SECLABEL1>Date</SECLABEL1>
        <SECVALUE1>4th July, 2013</SECVALUE1>
        <SECLABEL2>Auditorium</SECLABEL2>
        <SECVALUE2>Gold Room</SECVALUE2>
        <AUXLABEL1>Address</AUXLABEL1>
        <AUXVALUE1>Biz Convention Center, Boston MA 02144</AUXVALUE1>
        <BACKLABEL1>Terms and Conditions</BACKLABEL1>
        <BACKVALUE1>Valid for 1 person only. Valid for 1 visit only. Expires July 6th, 2013. Valid ID required if requested.</BACKVALUE1>
        <BACKLABEL2>Snacks and Drinks</BACKLABEL2>
        <BACKVALUE2>Free Drinks and Snacks are available in the main lobby.</BACKVALUE2>
        <BACKLABEL3>Please take a small survey to win a free ticket for our next event</BACKLABEL3>
        <BACKVALUE3>https://www.survey.com/event/12748493fgh/</BACKVALUE3>
        <RELLATITUDE2>42.347888</RELLATITUDE2>
        <RELLONGITUDE2>-71.087903</RELLONGITUDE2>
        <RELTEXT2>Event at HYNES CONVENTION CENTRE</RELTEXT2>
    </PASSDATA>    
</REQUEST>
```

__Response Example: Success__
```xml
<RESPONSE>
    <STATUS>Success</STATUS>
    <EMAILTEMPLATEID>35674</EMAILTEMPLATEID>
    <TRACKINGID>EMAIL_12346</TRACKINGID>
    <EMAIL>vik.muth@mail.com</EMAIL>
    <CAMPAIGNID>1233</CAMPAIGNID>
</RESPONSE>
```

__Response Example: Failure__
```xml
<RESPONSE>
    <STATUS>Failure</STATUS>
    <EMAILTEMPLATEID>35674</EMAILTEMPLATEID>
    <ERRORCODE>E713</ERRORCODE>
    <ERRORINFO>There is billing problem on your account.</ERRORINFO>
    <EMAIL>vik.muth@mail.com</EMAIL>
    <CAMPAIGNID>1233</CAMPAIGNID>
</RESPONSE>
```
