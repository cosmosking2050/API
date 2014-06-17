[Back to the Table of Contents](/1.3/README.md)&nbsp;&nbsp;|&nbsp;&nbsp;[Back to API Methods](API_METHODS.md)
##getPassEmailTemplate
__Synopsis:__  
This API is used to get the stored email template html with an embedded passbook pass in it for the specified email address. The pass data in the request is used in limitation to the pass template settings to generate this pass.
Custom pass ID is your system generated unique ID that will represent this pass data. In the case of Relevance, Relevant Text is considered only when Relevance Lat and Long values are passed in the API otherwise ignored.
Also, it requires a reference email campaign to which this email address will be subscribed to. 
If any case, the subscription fails then the email address is added to the email campaign's audience manager as 'unsubscribed' and you will receive a warning code and warning status in the response. 
The subscriber's data passed in the request will be saved and profiled for this email address. The email campaign subscription might fail due to the following reasons:

1. The _email address_ has already opted-out of a campaign in your account.  
2. The _email address_ has unsubscribed from any campaign associated with the SMTP server you are using.  
3. The _email address_ has filed a spam complaint.  
4. The _email address_ bounced during a previous delivery.  
5. The _email address_ was opted by this user or account.  


The returned email template HTML can be directly plugged into the email body and can be sent from your email servers. Although, you need to set your email headers properly to support html sent in the email. The email html contains an 'unsubscription' link in the footer which could be used by subscriber or email address to unsubscribe from the email campaign to which it was subscribed to during this process. Also, contains a tracking link to keep track of opened/read emails.  
On success, it will return the email template HTML, warning code and warning info if any, along with the generated pass information such as custom pass ID if passed, pass data ID and serial number for the generated pass. For more info see below for Mandatory/Optional fields and Error codes.  
The email address is referenced by 'EMAIL', email campaign is referenced by 'CAMPAIGNID', email template is referenced by 'EMAILTEMPLATEID', subscriber's data is referenced by 'DATA' and the pass data is referenced by 'PASSDATA'.

__Request: XML__
```xml
<REQUEST>
    <ACTION>getPassEmailTemplate</ACTION>
    <API_KEY>apiKey</API_KEY>
    <EMAILTEMPLATEID>emailTemplateId</EMAILTEMPLATEID>
    <EMAIL>email</EMAIL>
    <CAMPAIGNID>emailCampaignId</CAMPAIGNID>
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
    </PASSDATA>    
</REQUEST>
```

__Request: GET__

    API_URL?action=getpassemailtemplate&api_key=apiKey&emailtemplateid=emailTemplateId&email=email&campaignid=emailCampaignId
    &data_first_name=firstName&data_last_name=lastName&data_age=age&data_pet=pet
    &pd_custompassid=customPassId&pd_thumbnailurl=thumbnailUrl
    &pd_barcodevalue=barcodeValue&pd_barcodetext=barcodeText
    &pd_headerlabel1=headerLabel1&pd_headervalue1=headerValue1
    &pd_primarylabel1=primaryLabel1&pd_primaryvalue1=primaryValue1&pd_primarylabel2=primaryLabel2
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
<pre>
<strong>Mandatory:</strong>
action, apiKey, email, emailTemplateId, emailCampaignId,
barcodeValue (if "Barcode=Allowed" && "BarcodeType=Dynamic" && "BarcodeValueSource=Dynamic Value" for Pass Template otherwise IGNORED)
<strong>Optional:</strong>
customPassId, thumbnailUrl,
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
</pre>

__Response Parameters:__  
status, email, emailTemplateId, passDataId, serialNumber, customPassId, warningCode, warningInfo, emailSubject, emailHtml, errorCode, errorInfo

__Related Errorcodes:__  
E401, E402, E713, E714, E802, E803, E806, E823, E840, E841, E842, E843, E844, E845, E846, E847, E848, E849, E850, E851, E852, E853, E854, E855, E856, E857, E858, E859, E860, E861, E862, E863, E864, E865, E866, E867, E868, E869, E870, E871, E872, E873, E874, E875, E876, E877, E878, E879, E880, E881, E882, E883, E884, E885, E886, E887, E888, E889, E890, E891, E892, E893, E894, E895, E896, E897, E898, E899

__Related Warningcodes:__  
E915, E916, E917, E918

__Request Example:__
```xml
<REQUEST>
    <ACTION>getPassEmailTemplate</ACTION>
    <API_KEY>qTFkykO9JTfahCOqJ0V2Wf5Cg1t8iWlZ</API_KEY>
    <EMAILTEMPLATEID>45633</EMAILTEMPLATEID>
    <EMAIL>vik.muth@mail.com</EMAIL>
    <CAMPAIGNID>1233</CAMPAIGNID>
    <PASSDATA>
        <CUSTOMPASSID>CONT-ID-SKU:112324</CUSTOMPASSID>
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
    <EMAIL>vik.muth@mail.com</EMAIL>
    <CAMPAIGNID>1233</CAMPAIGNID>
    <PASSDATAID>63202e8e947626dae377ab2463ca31dhwtdjdien</PASSDATAID>
    <SERIALNUMBER>KJSD3432-232232-2323N32</SERIALNUMBER>
    <CUSTOMPASSID>CONT-ID-SKU:112324</CUSTOMPASSID>
    <WARNINGCODE>E915</WARNINGCODE>
    <WARNINGINFO>E915</WARNINGINFO>
    <EMAILSUBJECT>Get Your Pass</EMAILSUBJECT>
    <EMAILHTML>
       <!DOCTYPE html ..... </html>
    </EMAILHTML>
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
