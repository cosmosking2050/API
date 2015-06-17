[Back to the Table of Contents](/1.3/README.md)

## sendPassInMMS

__Synopsis:__  
This API request triggers sending an MMS with Dynamic Pass. Dynamic pass data passed in the API request will be used to create a Passbook pass sent via MMS. The pass data gets locked with the Phone number in the request and is used in limitation to the Pass Template settings. All the other/extra pass data is ignored. CustomPassId is your system generated Unique Id that will represent this pass data. You can optinally pass it along with pass data to be saved along with pass data and this can be used to refer this pass. In the case of Relevance, Relevant Text is considered only when Relevance lat,long values are passed in the API otherwise ignored. MMS is sent from a specified account using a MMSID to a single mobile number. FROM must be one of shortcodes allowed for your account. In case the number is from a different country than the FROM shortcode is assigned to, the default shortcode for those countries will be used.

__Content Transcoding:__  
Every binary MMS we deliver can be transcoded for the destination handset and every web page we deliver is transcoded for the browsing handset. To transcode a binary MMS we must know what type of handset the user has. We are able to obtain this handset type information from delivery receipts and store the record in a handset cache for later use. We have a database of attributes which we manually match to every new handset in the cache so we can adapt the content during MMS delivery.

Our API allows you to dynamically change each slide text by setting up CUSTOMTEXT (value, slide) and MMS Subject by setting CUSTOMSUBJECT.

A Device Discovery Message (DDM) is a short textual MMS message that is sent to the number to discover what handset the end user is using. We store this handset information in our system and reuse it, so a DDM is sent only to new numbers. If the DDM settings are not included within your API call and the number is not in the handset cache we will deliver the MMS with generic settings. If the handset is in the handset cache the DDM will not be sent and the MMS message will be transcoded and delivered immediately.

Our API allows you to customize DDM by setting 3 parameters:  
DDMTITLE - This is the DDM title.  
DDMTEXT - This is the DDM body.  
DDMTIMEOUT - When we send DDM we wait for the Delivery Report which contain the handset profile. In some cases we don't receive it or it takes very long (handset turned off or out of range). This variable tells the system how long should it wait for DDM Delivery Report before sending actual content using Default parameters. Default value of this parameter is 5 minutes.

__Request: XML__
```xml
<REQUEST>
    <ACTION>sendPassInMMS</ACTION>
    <API_KEY>apiKey</API_KEY>
    <MMSID>mmsId</MMSID>
    <TO>phone</TO>
    <FROM>shortcode</FROM>
   *<FROM_MASK>shortcodeMask</FROM_MASK>
    <CAMPAIGNREF>campaignId</CAMPAIGNREF>
    <DDMTITLE>DDMTitle</DDMTITLE>
    <DDMTEXT>DDMText</DDMTEXT>
    <DDMTIMEOUT>DDMTimeout (in mins)</DDMTIMEOUT>
    <CUSTOMTEXT>
        <VALUE>customText</VALUE>
        <SLIDE>slideId</SLIDE>
    </CUSTOMTEXT>
    <CUSTOMSUBJECT>MMSCustomSubject</CUSTOMSUBJECT>
    <DATA>
        <FIRST_NAME>firstName</FIRST_NAME>
        <LAST_NAME>lastName</LAST_NAME>
        <GENDER>gender</GENDER>
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
        <IBEACONUUID1>iBeaconUUID1</IBEACONUUID1>
        <IBEACONMAJOR1>iBeaconMajor1</IBEACONMAJOR1>
        <IBEACONMINOR1>iBeaconMinor1</IBEACONMINOR1>
        <IBEACONTEXT1>iBeaconText1</IBEACONTEXT1>
        <IBEACONUUID2>iBeaconUUID2</IBEACONUUID2>
        <IBEACONMAJOR2>iBeaconMajor2</IBEACONMAJOR2>
        <IBEACONMINOR2>iBeaconMinor2</IBEACONMINOR2>
        <IBEACONTEXT2>iBeaconText2</IBEACONTEXT2>
        <IBEACONUUID3>iBeaconUUID3</IBEACONUUID3>
        <IBEACONMAJOR3>iBeaconMajor3</IBEACONMAJOR3>
        <IBEACONMINOR3>iBeaconMinor3</IBEACONMINOR3>
        <IBEACONTEXT3>iBeaconText3</IBEACONTEXT3>
        <IBEACONUUID4>iBeaconUUID4</IBEACONUUID4>
        <IBEACONMAJOR4>iBeaconMajor4</IBEACONMAJOR4>
        <IBEACONMINOR4>iBeaconMinor4</IBEACONMINOR4>
        <IBEACONTEXT4>iBeaconText4</IBEACONTEXT4>
        <IBEACONUUID5>iBeaconUUID5</IBEACONUUID5>
        <IBEACONMAJOR5>iBeaconMajor5</IBEACONMAJOR5>
        <IBEACONMINOR5>iBeaconMinor5</IBEACONMINOR5>
        <IBEACONTEXT5>iBeaconText5</IBEACONTEXT5>
        <IBEACONUUID6>iBeaconUUID6</IBEACONUUID6>
        <IBEACONMAJOR6>iBeaconMajor6</IBEACONMAJOR6>
        <IBEACONMINOR6>iBeaconMinor6</IBEACONMINOR6>
        <IBEACONTEXT6>iBeaconText6</IBEACONTEXT6>
        <IBEACONUUID7>iBeaconUUID7</IBEACONUUID7>
        <IBEACONMAJOR7>iBeaconMajor7</IBEACONMAJOR7>
        <IBEACONMINOR7>iBeaconMinor7</IBEACONMINOR7>
        <IBEACONTEXT7>iBeaconText7</IBEACONTEXT7>
        <IBEACONUUID8>iBeaconUUID8</IBEACONUUID8>
        <IBEACONMAJOR8>iBeaconMajor8</IBEACONMAJOR8>
        <IBEACONMINOR8>iBeaconMinor8</IBEACONMINOR8>
        <IBEACONTEXT8>iBeaconText8</IBEACONTEXT8>
        <IBEACONUUID9>iBeaconUUID9</IBEACONUUID9>
        <IBEACONMAJOR9>iBeaconMajor9</IBEACONMAJOR9>
        <IBEACONMINOR9>iBeaconMinor9</IBEACONMINOR9>
        <IBEACONTEXT9>iBeaconText9</IBEACONTEXT9>
        <IBEACONUUID10>iBeaconUUID10</IBEACONUUID10>
        <IBEACONMAJOR10>iBeaconMajor10</IBEACONMAJOR10>
        <IBEACONMINOR10>iBeaconMinor10</IBEACONMINOR10>
        <IBEACONTEXT10>iBeaconText10</IBEACONTEXT10>
    </PASSDATA>    
</REQUEST>

*ShortcodeMask (Alphanumeric sender) is allowed only in few countries. Not supported in United States.
```

__Request: GET__

    API_URL?action=sendpassinmms&api_key=apiKey&mmsid=mmsId&to=phone
    &from=shortcode&campaignref=campaignId&ddmtitle=ddmTitle&ddmtext=ddmText&ddmtimeout=ddmTimeout
    &customtext_1=customTextSlide1&customsubject=customSubject
    &data_first_name=firstName&data_last_name=lastName&data_age=age&pd_custompassid=customPassId
    &pd_thumbnailurl=thumbnailUrl
    &pd_barcodevalue=barcodeValue&pd_barcodetext=barcodeText&pd_headerlabel1=headerLabel1
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
    &pd_ibeaconuuid1=ibeaconUUID1&pd_ibeaconmajor1=ibeaconMajor1&pd_ibeaconminor1=ibeaconMinor1&pd_ibeacontext1=ibeaconText1
    &pd_ibeaconuuid2=ibeaconUUID2&pd_ibeaconmajor2=ibeaconMajor2&pd_ibeaconminor2=ibeaconMinor2&pd_ibeacontext2=ibeaconText2
    &pd_ibeaconuuid3=ibeaconUUID3&pd_ibeaconmajor3=ibeaconMajor3&pd_ibeaconminor3=ibeaconMinor3&pd_ibeacontext3=ibeaconText3
    &pd_ibeaconuuid4=ibeaconUUID4&pd_ibeaconmajor4=ibeaconMajor4&pd_ibeaconminor4=ibeaconMinor4&pd_ibeacontext4=ibeaconText4
    &pd_ibeaconuuid5=ibeaconUUID5&pd_ibeaconmajor5=ibeaconMajor5&pd_ibeaconminor5=ibeaconMinor5&pd_ibeacontext5=ibeaconText5
    &pd_ibeaconuuid6=ibeaconUUID6&pd_ibeaconmajor6=ibeaconMajor6&pd_ibeaconminor6=ibeaconMinor6&pd_ibeacontext6=ibeaconText6
    &pd_ibeaconuuid7=ibeaconUUID7&pd_ibeaconmajor7=ibeaconMajor7&pd_ibeaconminor7=ibeaconMinor7&pd_ibeacontext7=ibeaconText7
    &pd_ibeaconuuid8=ibeaconUUID8&pd_ibeaconmajor8=ibeaconMajor8&pd_ibeaconminor8=ibeaconMinor8&pd_ibeacontext8=ibeaconText8
    &pd_ibeaconuuid9=ibeaconUUID9&pd_ibeaconmajor9=ibeaconMajor9&pd_ibeaconminor9=ibeaconMinor9&pd_ibeacontext9=ibeaconText9
    &pd_ibeaconuuid10=ibeaconUUID10&pd_ibeaconmajor10=ibeaconMajor10&pd_ibeaconminor10=ibeaconMinor10
    &pd_ibeacontext10=ibeaconText10
    
__Request Parameters:__

    Mandatory: action, api_key, mmsid, to, from, 
    barcodevalue (if "Barcode = Allowed" && "Barcode Type = Dynamic" && "Barcode Value Source = Dynamic Value" for Pass Template otherwise IGNORED)
    Optional: campaignref, ddmtitle, ddmtext, ddmtimeout, customsubject, customText, data, thumbnailUrl,
    barcodetext (if "Barcode = Allowed" && "Barcode Alternate Text = Dynamic Text" for Pass Template otherwise IGNORED), 
    headerlabel1, headervalue1, 
    primarylabel1, primaryvalue1, 
    primarylabel2, primaryvalue2 - if "Pass template type = Boarding Pass" otherwise IGNORED, 
    seclabel1, secvalue1, seclabel2, secvalue2, seclabel3, secvalue3, seclabel4, secvalue4, 
    auxlabel1, auxvalue1, auxlabel2, auxvalue2, auxlabel3, auxvalue3, auxlabel4, auxvalue4, 
    backlabel1, backvalue1, backlabel2, backvalue2, backlabel3, backvalue3, backlabel4, backvalue4,
    rellatitude1, rellongitude1, reltext1,
    rellatitude2, rellongitude2, reltext2,
    rellatitude3, rellongitude3, reltext3,
    rellatitude4, rellongitude4, reltext4,
    rellatitude5, rellongitude5, reltext5,
    rellatitude6, rellongitude6, reltext6,
    rellatitude7, rellongitude7, reltext7,
    rellatitude8, rellongitude8, reltext8,
    rellatitude9, rellongitude9, reltext9,
    rellatitude10, rellongitude10, reltext10,
    ibeaconUUID1, ibeaconMajor1, ibeaconMinor1, ibeaconText1,
    ibeaconUUID2, ibeaconMajor2, ibeaconMinor2, ibeaconText2,
    ibeaconUUID3, ibeaconMajor3, ibeaconMinor3, ibeaconText3,
    ibeaconUUID4, ibeaconMajor4, ibeaconMinor4, ibeaconText4,
    ibeaconUUID5, ibeaconMajor5, ibeaconMinor5, ibeaconText5,
    ibeaconUUID6, ibeaconMajor6, ibeaconMinor6, ibeaconText6,
    ibeaconUUID7, ibeaconMajor7, ibeaconMinor7, ibeaconText7,
    ibeaconUUID8, ibeaconMajor8, ibeaconMinor8, ibeaconText8,
    ibeaconUUID9, ibeaconMajor9, ibeaconMinor9, ibeaconText9,
    ibeaconUUID10, ibeaconMajor10, ibeaconMinor10, ibeaconText10

__Response Parameters:__

    status, to, from, mmsId, trackingId, errorCode, errorInfo

__Related Error Codes:__
    
    E110, E111, E241, E620, E621, E626, E628, E629, E713, E714, E715, E802, E803, E806, E822, E840, E841, E842, E843,
    E844, E845, E846, E847, E848, E849, E850, E851, E852, E853, E854, E855, E856, E857, E858, E859, E860, E861, E862,
    E863, E864, E865, E866, E867, E868, E869, E870, E871, E872, E873, E874, E875, E876, E877, E878, E879, E880, E881,
    E882, E883, E884, E885, E886, E887, E888, E889, E890, E891, E892, E893, E894, E895, E896, E897, E898, E899, E950, 
    E951, E952, E953, E954, E955, E956, E957, E958, E959, E960, E961, E962, E963, E964, E965, E966, E967, E968, E969, 
    E970, E971, E972, E973, E974, E975, E976, E977, E978, E979, E980, E981, E982, E983, E984, E985, E986, E987, E988,
    E989, E990, E991, E992, E993, E994, E995, E996, E997, E998, E999

__Request Example:__
```xml
<REQUEST>
    <ACTION>sendPassInMMS</ACTION>
    <API_KEY>qTFkykO9JTfahCOqJ0V2Wf5Cg1t8iWlZ</API_KEY>
    <MMSID>45633</MMSID>
    <TO>16501234123</TO>
    <FROM>11111</FROM>
    <CAMPAIGNREF>12333</CAMPAIGNREF>
    <DDMTITLE>We are detecting your handset</DDMTITLE>
    <DDMTEXT>This message is free of charge and will allow us to deliver your content nice and smooth</DDMTEXT>
    <DDMTIMEOUT>10</DDMTIMEOUT>
    <CUSTOMTEXT>
        <VALUE>Hyes Convention Event Ticket</VALUE>
        <SLIDE>1</SLIDE>
    </CUSTOMTEXT>
    <CUSTOMSUBJECT>Your Event Ticket</CUSTOMSUBJECT>
    <DATA>
        <FIRST_NAME>John</FIRST_NAME>
        <LAST_NAME>Smith</LAST_NAME>
        <AGE>30</AGE>
        <GENDER>Male</GENDER>
    </DATA>        
    <PASSDATA>
        <THUMBNAILURL>http://andreas.com/pixs/steve-jobs.png</THUMBNAILURL>
        <BARCODEVALUE>1234578961A</BARCODEVALUE>
        <BARCODETEXT>PASS-123-457</BARCODETEXT>
        <HEADERLABEL1>SEAT</HEADERLABEL1>
        <HEADERVALUE1>1C</HEADERVALUE1>
        <PRIMARYLABEL1>Name</PRIMARYLABEL1>
        <PRIMARYVALUE1>John Smith</PRIMARYVALUE1> 
        <SECLABEL1>Date</SECLABEL1>
        <SECVALUE1>4th July, 2013</SECVALUE1>
        <SECLABEL2>Auditorium</SECLABEL2>
        <SECVALUE2>Gold Room</SECVALUE2>
        <AUXLABEL1>Address</AUXLABEL1>
        <AUXVALUE1>Hyes Convention Centre, Boston MA 02144</AUXVALUE1>
        <BACKLABEL1>Terms and Conditions</BACKLABEL1>
        <BACKVALUE1>Valid for 1 person only. Expires July 6th, 2013. Valid ID required if requested.</BACKVALUE1>
        <BACKLABEL2>Snacks and Drinks</BACKLABEL2>
        <BACKVALUE2>Free Drinks and Snacks are available in the main lobby.</BACKVALUE2>
        <BACKLABEL3>Please take a small survey to win a free ticket for our next event. </BACKLABEL3>
        <BACKVALUE3>https://www.survey.com/event/12748493fgh/</BACKVALUE3>
        <RELLATITUDE2>42.347888</RELLATITUDE2>
        <RELLONGITUDE2>-71.087903</RELLONGITUDE2>
        <RELTEXT2>Event at HYES CONVENTION CENTRE</RELTEXT2>
    </PASSDATA>    
</REQUEST>
```

__Response Example: Success__
```xml
<RESPONSE>
    <STATUS>Success</STATUS>
    <MMSID>35674</MMSID>
    <TRACKINGID>TU1TXzEyMzQ2</TRACKINGID>
    <TO>16501234123</TO>
    <FROM>11111</FROM>
</RESPONSE>
```

__Response Example: Failure__
```xml
<RESPONSE>
    <STATUS>Failure</STATUS>
    <ERRORCODE>E713</ERRORCODE>
    <TO>16501234123</TO>
    <ERRORINFO>There is billing problem on your account.</ERRORINFO>
</RESPONSE>
```

__Postback Notifications For SendPassInMMS__  
When the MMS delivery is processed successfully the system will generate a Postback notification. For more details please visit [postback doc](https://github.com/SkycoreMobile/API/blob/master/1.3/CONTENTS/POSTBACKS/POSTBACK_DELIVERY_REPORTS.md).
```xml
<?xml version='1.0'?>
<POSTBACK>
    <ORIGIN>MMS_MT</ORIGIN>
    <CODE>N101</CODE>
    <SENTAS>MMS</SENTAS>
    <STATUS>Message Sent</STATUS>
    <MMSID>35674</MMSID>
    <TO>16501234123</TO>
    <TRACKINGID>TU1TXzEyMzQ2</TRACKINGID>
    <SPID>0001890</SPID>
    <TIMESTAMP>2011-08-02T07:20:44-04:00</TIMESTAMP>
</POSTBACK>
```

When an MMS delivery report is received the system will generate a Postback notification. Not all carriers provide MMS delivery receipts.
```xml
<?xml version='1.0'?>
<POSTBACK>
    <ORIGIN>MMS_MT</ORIGIN>
    <CODE>N102</CODE>
    <SENTAS>MMS</SENTAS>
    <STATUS>Message Sent/Delivered</STATUS>
    <MMSID>35674</MMSID>
    <TO>16501234123</TO>
    <TRACKINGID>TU1TXzEyMzQ2</TRACKINGID>
    <SPID>0001890</SPID>
    <TIMESTAMP>2011-08-02T07:20:49-04:00</TIMESTAMP>
    <HANDSET>motol7c</HANDSET>
    <AGGREGATORID>11529-64807-97508-73852-97658</AGGREGATORID>
</POSTBACK>
```
