[Back to the Table of Contents](/1.3/README.md)

## updatePass

__Synopsis:__  
This API request updates the pass data for that passDataId if exists. If this pass data was already used to generate a Passbook Pass which is installed on the device, then this request will also trigger a pass update on that device. Only the dynamic pas data is allowed to be updated and rest of the data stays the same. If the pass template associated with this pass was updated with new images, colors, data types and number of fields then those updates will be also reflected in the pass update. All the data is updated in limitation to the settings on the pass template and all the other/extra data is ignored. You cannot update Email (or) Phone in this request but the pass data. On success, it will return the UpdateStatusId. For more info see below for Mandatory/Optional fields and Error codes.

__Request: XML__
```xml
<REQUEST>
    <ACTION>updatePass</ACTION>
    <API_KEY>apiKey</API_KEY>
    <PASSDATAID>passDataId</PASSDATAID>
    <PASSDATA>
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
```

__Request: GET__

    API_URL?action=updatepass&api_key=apiKey&passdataid=passDataId
    &pd_thumbnailurl=thumbnailUrl
    &pd_barcodevalue=barcodeValue&pd_barcodetext=barcodeText
    &pd_headerlabel1=headerLabel1&pd_headervalue1=headerValue1
    &pd_primarylabel1=primaryLabel1&pd_primaryvalue1=primaryValue1
    &pd_primarylabel2=primaryLabel2&pd_primaryvalue2=primaryValue2
    &pd_seclabel1=secLabel1&pd_secvalue1=secValue1&pd_seclabel2=secLabel2
    &pd_secvalue2=secValue2&pd_seclabel3=secLabel3&pd_secvalue3=secValue3
    &pd_seclabel4=secLabel4&pd_secvalue4=secValue4&pd_auxlabel1=auxLabel1
    &pd_auxvalue1=auxValue1&pd_auxlabel2=auxLabel2&pd_auxvalue2=auxValue2
    &pd_auxlabel3=auxLabel3&pd_auxvalue3=auxValue3&pd_auxlabel4=auxLabel4
    &pd_auxvalue4=auxValue4&pd_backlabel1=backLabel1&pd_backvalue1=backValue1
    &pd_backlabel2=backLabel2&pd_backvalue2=backValue2&pd_backlabel3=backLabel3
    &pd_backvalue3=backValue3&pd_backlabel4=backLabel4&pd_backvalue4=backValue4
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

    Mandatory: action, api_key, passDataId
    Optional: thumbnailUrl,
    barcodeValue (if "Barcode = Allowed" && "Barcode Type = Dynamic" && "Barcode Value Source = Dynamic Value" for Pass Template otherwise IGNORED),
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
    relLatitude10, relLongitude10, relText10,
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

    status, passDataId, updateStatusID, errorCode, errorInfo

__Related Error Codes:__

    E802, E803, E807, E808, E809, E840, E841, E842, E843, E844, E845, E846, E847, E848, E849, E850, E851, E852, E853,
    E854, E855, E856, E857, E858, E859, E860, E861, E862, E863, E864, E865, E866, E867, E868, E869, E870, E871, E872,
    E873, E874, E875, E876, E877, E878, E879, E880, E881, E882, E883, E884, E885, E886, E887, E888, E889, E890, E891,
    E892, E893, E894, E895, E896, E897, E898, E899, E950, E951, E952, E953, E954, E955, E956, E957, 
    E958, E959, E960, E961, E962, E963, E964, E965, E966, E967, E968, E969, E970, E971, E972, E973, E974, E975, E976, 
    E977, E978, E979, E980, E981, E982, E983, E984, E985, E986, E987, E988, E989, E990, E991, E992, E993, E994, E995, 
    E996, E997, E998, E999

__Request Example:__
```xml
<REQUEST>
    <ACTION>updatePass</ACTION>
    <API_KEY>qTFkykO9JTfahCOqJ0V2Wf5Cg1t8iWlZ</API_KEY>
    <PASSDATAID>1233</PASSDATAID>
    <PASSDATA>
        <THUMBNAILURL>http://andreas.com/pixs/steve-jobs.png</THUMBNAILURL>
        <BARCODEVALUE>3434578961A</BARCODEVALUE>
        <BARCODETEXT>PASS-343-457</BARCODETEXT>
        <HEADERLABEL1>SEAT</HEADERLABEL1>
        <HEADERVALUE1>100C</HEADERVALUE1>
        <SECLABEL1>Date</SECLABEL1>
        <SECVALUE1>3rd July, 2013</SECVALUE1>
        <BACKLABEL4>Important - Change</BACKLABEL4>
        <BACKVALUE4>New ticket issued. Schedule preponed by one day.</BACKVALUE4>
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
    <PASSDATAID>1233</PASSDATAID>
    <UPDATESTATUSID>1007</UPDATESTATUSID>
</RESPONSE>
```

__Response Example: Failure__
```xml
<RESPONSE>
    <STATUS>Failure</STATUS>
    <ERRORCODE>E809</ERRORCODE>
    <ERRORINFO>Pass was not updated. Internal error occured.</ERRORINFO>
</RESPONSE>
```
