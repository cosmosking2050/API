<a href="/1.3/README.md">Back to the Table of Contents</a>&nbsp;&nbsp;|&nbsp;&nbsp;<a href="API_METHODS.md">Back to API Methods</a>
<h2>sendPassInMMS</h2>
<p><strong>Synopsis:</strong><br />
This API request triggers sending an MMS with Dynamic Pass. Dynamic pass data passed in the API request will be used to create a Passbook pass sent via MMS. 
The pass data gets locked with the Phone number in the request and is used in limitation to the Pass Template settings. All the other/extra pass data is ignored.
CustomPassId is your system generated Unique Id that will represent this pass data. You can optinally pass it along with pass data to be saved along with pass data and this can be used to refer this pass.
In the case of Relevance, Relevant Text is considered only when Relevance lat,long values are passed in the API otherwise ignored.
MMS is sent from a specified account using a MMSID to a single mobile number. 
FROM must be one of shortcodes allowed for your account. 
In case the number is from a different country than the FROM shortcode is assigned to &#8211; default shortcode for those countries will be used.</p>
<p><strong>Content Transcoding:</strong><br />
Every binary MMS we deliver can be transcoded for the destination handset and every web page we deliver is transcoded for the browsing handset. 
To transcode a binary MMS we must know what type of handset the user has. 
We are able to obtain this handset type information from delivery receipts and store the record in a handset cache for later use. 
We have a database of attributes which we manually match to every new handset in the cache so we can adapt the content during MMS delivery.</p>
<p>Our API allows you to dynamically change each slide text by setting up CUSTOMTEXT (value, slide) and MMS Subject by setting CUSTOMSUBJECT.
<p>A Device Discovery Message (DDM) is a short textual MMS message that is sent to the number to discover what handset the end user is using. 
We store this handset information in our system and reuse it, so a DDM is sent only to new numbers. 
If the DDM settings are not included within your API call and the number is not in the handset cache we will deliver the MMS with generic settings. 
If the handset is in the handset cache the DDM will not be sent and the MMS message will be transcoded and delivered immediately.</p>
<p>Our API allows you to customize DDM by setting 3 parameters:<br />
DDMTITLE &#8211; this is the DDM title<br />
DDMTEXT &#8211; this is the DDM body<br />
DDMTIMEOUT &#8211; when we send DDM we wait for the Delivery Report which contain the handset profile. In some cases we don&#8217;t receive it or it takes very long (handset turned off or out of range). This variable tells the system how long should it wait for DDM Delivery Report before sending actual content using Default parameters. Default value of this parameter is 5 minutes.</p>
<p>This API allow you to pass DeviceId/HandsetId inside DEVICE parameter. We will store this information and (if HandsetID is recognized by our system) use handset profile to adapt content for current and future MMS delivery.
<br />
NOTE: Once we receive Delivery Receipt with HandsetId we overwrite current value assigned to that number, we consider HandsetId from Delivery Receipt more up-to-date.
<br />
DEVICE parameter can be used with DDM as a fallback mechanism. If HandsetId passed in API call is not recognized by our system, it will send DDM (if specified in the request) to the handset to detect it. If there was no DDM specified in the request, system will use generic settings for MMS delivery.</p>
On success, it will return the MMSTrackingID. For more info see below for Mandatory/Optional fields and Error codes.</p>

<div><strong>Request: XML</strong></div>
<pre>&lt;REQUEST&gt;
    &lt;ACTION&gt;sendPassInMMS&lt;/ACTION&gt;
    &lt;API_KEY&gt;apiKey&lt;/API_KEY&gt;
    &lt;MMSID&gt;mmsId&lt;/MMSID&gt;
    &lt;TO&gt;phone&lt;/TO&gt;
    &lt;FROM&gt;shortcode&lt;/FROM&gt;
    &lt;CAMPAIGNREF&gt;campaignId&lt;/CAMPAIGNREF&gt;
    &lt;DDMTITLE&gt;DDMTitle&lt;/DDMTITLE&gt;
	&lt;DDMTEXT&gt;DDMText&lt;/DDMTEXT&gt;
	&lt;DDMTIMEOUT&gt;DDMTimeout (in mins)&lt;/DDMTIMEOUT&gt;
	&lt;DEVICE&gt;handsetId&lt;/DEVICE&gt;
	&lt;CUSTOMTEXT&gt;
		&lt;VALUE&gt;customText&lt;/VALUE&gt;
		&lt;SLIDE&gt;slideId&lt;/SLIDE&gt;
	&lt;/CUSTOMTEXT&gt;
	&lt;/CUSTOMSUBJECT&gt;MMSCustomSubject&lt;/CUSTOMSUBJECT&gt;
	&lt;DATA&gt;
		&lt;FIRST_NAME&gt;firstName&lt;/FIRST_NAME&gt;
		&lt;LAST_NAME&gt;lastName&lt;/LAST_NAME&gt;
		&lt;GENDER&gt;gender&lt;/GENDER&gt;
		...
	&lt;/DATA&gt;
    &lt;PASSDATA&gt;
    	&lt;CUSTOMPASSID&gt;customPassId&lt;/CUSTOMPASSID&gt;
    	&lt;THUMBNAILURL&gt;thumbnailUrl&lt;/THUMBNAILURL&gt;
        &lt;BARCODEVALUE&gt;barcodeValue&lt;/BARCODEVALUE&gt;
        &lt;BARCODETEXT&gt;barcodeText&lt;/BARCODETEXT&gt;
        &lt;HEADERLABEL1&gt;headerLabel1&lt;/HEADERLABEL1&gt;
        &lt;HEADERVALUE1&gt;headerValue1&lt;/HEADERVALUE1&gt;
        &lt;PRIMARYLABEL1&gt;primaryLabel1&lt;/PRIMARYLABEL1&gt;
        &lt;PRIMARYVALUE1&gt;primaryValue1&lt;/PRIMARYVALUE1&gt; 
        &lt;PRIMARYLABEL2&gt;primaryLabel2&lt;/PRIMARYLABEL2&gt;
        &lt;PRIMARYVALUE2&gt;primaryValue2&lt;/PRIMARYVALUE2&gt; 
        &lt;SECLABEL1&gt;secLabel1&lt;/SECLABEL1&gt;
        &lt;SECVALUE1&gt;secValue1&lt;/SECVALUE1&gt;
        &lt;SECLABEL2&gt;sedLabel2&lt;/SECLABEL2&gt;
        &lt;SECVALUE2&gt;secValue2&lt;/SECVALUE2&gt;
        &lt;SECLABEL3&gt;sedLabel3&lt;/SECLABEL3&gt;
        &lt;SECVALUE3&gt;secValue3&lt;/SECVALUE3&gt;
        &lt;SECLABEL4&gt;sedLabel4&lt;/SECLABEL4&gt;
        &lt;SECVALUE4&gt;secValue4&lt;/SECVALUE4&gt;
        &lt;AUXLABEL1&gt;auxLabel1&lt;/AUXLABEL1&gt;
        &lt;AUXVALUE1&gt;auxValue1&lt;/AUXVALUE1&gt;
        &lt;AUXLABEL2&gt;auxLabel2&lt;/AUXLABEL2&gt;
        &lt;AUXVALUE2&gt;auxValue2&lt;/AUXVALUE2&gt;
        &lt;AUXLABEL3&gt;auxLabel3&lt;/AUXLABEL3&gt;
        &lt;AUXVALUE3&gt;auxValue3&lt;/AUXVALUE3&gt;
        &lt;AUXLABEL4&gt;auxLabel4&lt;/AUXLABEL4&gt;
        &lt;AUXVALUE4&gt;auxValue4&lt;/AUXVALUE4&gt;
        &lt;BACKLABEL1&gt;backLabel1&lt;/BACKLABEL1&gt;
        &lt;BACKVALUE1&gt;backValue1&lt;/BACKVALUE1&gt;
        &lt;BACKLABEL2&gt;backLabel2&lt;/BACKLABEL2&gt;
        &lt;BACKVALUE2&gt;backValue2&lt;/BACKVALUE2&gt;
        &lt;BACKLABEL3&gt;backLabel3&lt;/BACKLABEL3&gt;
        &lt;BACKVALUE3&gt;backValue3&lt;/BACKVALUE3&gt;
        &lt;BACKLABEL4&gt;backLabel4&lt;/BACKLABEL4&gt;
        &lt;BACKVALUE4&gt;backValue4&lt;/BACKVALUE4&gt;
        &lt;RELLATITUDE1&gt;relLatitude1&lt;/RELLATITUDE1&gt;
        &lt;RELLONGITUDE1&gt;relLongitude1&lt;/RELLONGITUDE1&gt;
        &lt;RELTEXT1&gt;relText1&lt;/RELTEXT1&gt;
        &lt;RELLATITUDE2&gt;relLatitude2&lt;/RELLATITUDE2&gt;
        &lt;RELLONGITUDE2&gt;relLongitude2&lt;/RELLONGITUDE2&gt;
        &lt;RELTEXT2&gt;relText2&lt;/RELTEXT2&gt;
        &lt;RELLATITUDE3&gt;relLatitude3&lt;/RELLATITUDE3&gt;
        &lt;RELLONGITUDE3&gt;relLongitude3&lt;/RELLONGITUDE3&gt;
        &lt;RELTEXT3&gt;relText3&lt;/RELTEXT3&gt;
        &lt;RELLATITUDE4&gt;relLatitude4&lt;/RELLATITUDE4&gt;
        &lt;RELLONGITUDE4&gt;relLongitude4&lt;/RELLONGITUDE4&gt;
        &lt;RELTEXT4&gt;relText4&lt;/RELTEXT4&gt;
        &lt;RELLATITUDE5&gt;relLatitude5&lt;/RELLATITUDE5&gt;
        &lt;RELLONGITUDE5&gt;relLongitude5&lt;/RELLONGITUDE5&gt;
        &lt;RELTEXT5&gt;relText5&lt;/RELTEXT5&gt;
        &lt;RELLATITUDE6&gt;relLatitude6&lt;/RELLATITUDE6&gt;
        &lt;RELLONGITUDE6&gt;relLongitude6&lt;/RELLONGITUDE6&gt;
        &lt;RELTEXT6&gt;relText6&lt;/RELTEXT6&gt;
        &lt;RELLATITUDE7&gt;relLatitude7&lt;/RELLATITUDE7&gt;
        &lt;RELLONGITUDE7&gt;relLongitude7&lt;/RELLONGITUDE7&gt;
        &lt;RELTEXT7&gt;relText7&lt;/RELTEXT7&gt;
        &lt;RELLATITUDE8&gt;relLatitude8&lt;/RELLATITUDE8&gt;
        &lt;RELLONGITUDE8&gt;relLongitude8&lt;/RELLONGITUDE8&gt;
        &lt;RELTEXT8&gt;relText8&lt;/RELTEXT8&gt;
        &lt;RELLATITUDE9&gt;relLatitude9&lt;/RELLATITUDE9&gt;
        &lt;RELLONGITUDE9&gt;relLongitude9&lt;/RELLONGITUDE9&gt;
        &lt;RELTEXT9&gt;relText9&lt;/RELTEXT9&gt;
        &lt;RELLATITUDE10&gt;relLatitude10&lt;/RELLATITUDE10&gt;
        &lt;RELLONGITUDE10&gt;relLongitude10&lt;/RELLONGITUDE10&gt;
        &lt;RELTEXT10&gt;relText10&lt;/RELTEXT10&gt;
    &lt;/PASSDATA&gt;    
&lt;/REQUEST&gt;</pre>
<div><strong>Request: GET</strong></div>
<pre>
API_URL?action=sendpassinmms&amp;api_key=apiKey&amp;mmsid=mmsId&amp;to=phone
&amp;from=shortcode&amp;campaignref=campaignId&amp;ddmtitle=ddmTitle&amp;ddmtext=ddmText&amp;ddmtimeout=ddmTimeout&amp;device=deviceId
&amp;customtext_1=customTextSlide1&amp;customsubject=customSubject
&amp;data_first_name=firstName&amp;data_last_name=lastName&amp;data_age=age&amp;pd_custompassid=customPassId
&amp;pd_barcodevalue=barcodeValue&amp;pd_barcodetext=barcodeText&amp;pd_headerlabel1=headerLabel1
&amp;pd_headervalue1=headerValue1&amp;pd_primarylabel1=primaryLabel1
&amp;pd_primaryvalue1=primaryValue1&amp;pd_primarylabel2=primaryLabel2
&amp;pd_primaryvalue2=primaryValue2&amp;pd_seclabel1=secLabel1&amp;pd_secvalue1=secValue1
&amp;pd_seclabel2=secLabel2&amp;pd_secvalue2=secValue2&amp;pd_seclabel3=secLabel3
&amp;pd_secvalue3=secValue3&amp;pd_seclabel4=secLabel4&amp;pd_secvalue4=secValue4
&amp;pd_auxlabel1=auxLabel1&amp;pd_auxvalue1=auxValue1&amp;pd_auxlabel2=auxLabel2
&amp;pd_auxvalue2=auxValue2&amp;pd_auxlabel3=auxLabel3&amp;pd_auxvalue3=auxValue3
&amp;pd_auxlabel4=auxLabel4&amp;pd_auxvalue4=auxValue4&amp;pd_backlabel1=backLabel1
&amp;pd_backvalue1=backValue1&amp;pd_backlabel2=backLabel2&amp;pd_backvalue2=backValue2
&amp;pd_backlabel3=backLabel3&amp;pd_backvalue3=backValue3&amp;pd_backlabel4=backLabel4&amp;pd_backvalue4=backValue4
&amp;pd_rellatitude1=relLatitude1&amp;pd_rellongitude1=relLongitude1&amp;pd_reltext1=relText1
&amp;pd_rellatitude2=relLatitude2&amp;pd_rellongitude2=relLongitude2&amp;pd_reltext2=relText2
&amp;pd_rellatitude3=relLatitude3&amp;pd_rellongitude3=relLongitude3&amp;pd_reltext3=relText3
&amp;pd_rellatitude4=relLatitude4&amp;pd_rellongitude4=relLongitude4&amp;pd_reltext4=relText4
&amp;pd_rellatitude5=relLatitude5&amp;pd_rellongitude5=relLongitude5&amp;pd_reltext5=relText5
&amp;pd_rellatitude6=relLatitude6&amp;pd_rellongitude6=relLongitude6&amp;pd_reltext6=relText6
&amp;pd_rellatitude7=relLatitude7&amp;pd_rellongitude7=relLongitude7&amp;pd_reltext7=relText7
&amp;pd_rellatitude8=relLatitude8&amp;pd_rellongitude8=relLongitude8&amp;pd_reltext8=relText8
&amp;pd_rellatitude9=relLatitude9&amp;pd_rellongitude9=relLongitude9&amp;pd_reltext9=relText9
&amp;pd_rellatitude10=relLatitude10&amp;pd_rellongitude10=relLongitude10&amp;pd_reltext10=relText10
</pre>
<div><strong>Request Parameters:</strong></div>
<pre><strong>Mandatory:</strong> 
action, apiKey, mmsid, to, from, 
barcodevalue (if "Barcode=Allowed" &amp;&amp; "BarcodeType=Dynamic" &amp;&amp; "Barcode value source=Dynamic Value" for Pass Template otherwise IGNORED),

<strong>Optional: </strong>
campaignref, ddmtitle, ddmtext, ddmtimeout, device, customsubject, customText, data, 
thumbnailUrl,
barcodetext (if "Barcode = Allowed" &amp;&amp; "Barcode Alternate Text = Dynamic Text" for Pass Template otherwise IGNORED), 
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
rellatitude10, rellongitude10, reltext10</pre>

<strong>Response Parameters:</strong><br />
status, to, mmsid, trackingid, errorcode, errorinfo

<strong>Related Errorcodes: </strong><br />
E110, E111, E241, E620, E621, E626, E628, E629, E713, E714, E715, E802, E803, E806, E822, E840, E841, E842, E843, E844, E845, E846, E847, E848, E849, E850, E851, E852, E853, E854, E855, E856, E857, E858, E859, E860, E861, E862, E863, E864, E865, E866, E867, E868, E869
E870, E871, E872, E873, E874, E875, E876, E877, E878, E879, E880, E881, E882, E883, E884, E885, E886, E887, E888, E889, E890, E891, E892, E893, E894, E895, E896, E897, E898, E899

<div><strong>Request Example:</strong></div>
<pre>&lt;REQUEST&gt;
    &lt;ACTION&gt;sendPassInMMS&lt;/ACTION&gt;
    &lt;API_KEY&gt;qTFkykO9JTfahCOqJ0V2Wf5Cg1t8iWlZ&lt;/API_KEY&gt;
    &lt;MMSID&gt;45633&lt;/MMSID&gt;
    &lt;TO&gt;16501234123&lt;/TO&gt;
    &lt;FROM&gt;11111&lt;/FROM&gt;
    &lt;CAMPAIGNREF&gt;12333&lt;/CAMPAIGNREF&gt;
    &lt;DDMTITLE&gt;We are detecting your handset&lt;/DDMTITLE&gt;
        &lt;DDMTEXT&gt;This message is free of charge and will allow us to deliver your content nice and smooth&lt;/DDMTEXT&gt;
        &lt;DDMTIMEOUT&gt;10&lt;/DDMTIMEOUT&gt;
        &lt;DEVICE&gt;iPhoneOS&lt;/DEVICE&gt;
        &lt;CUSTOMTEXT&gt;
        	&lt;VALUE&gt;Hyes Convention Event Ticket&lt;/VALUE&gt;
        	&lt;SLIDE&gt;1&lt;/SLIDE&gt;
        &lt;/CUSTOMTEXT&gt;
        &lt;/CUSTOMSUBJECT&gt;Your Event Ticket&lt;/CUSTOMSUBJECT&gt;
	&lt;DATA&gt;
		&lt;FIRST_NAME&gt;John&lt;/FIRST_NAME&gt;
		&lt;LAST_NAME&gt;Smith&lt;/LAST_NAME&gt;
		&lt;AGE&gt;30&lt;/AGE&gt;
		&lt;GENDER&gt;Male&lt;/GENDER&gt;
	&lt;/DATA&gt;        
    &lt;PASSDATA&gt;
    	&lt;THUMBNAILURL&gt;http://andreas.com/pixs/steve-jobs.png&lt;/THUMBNAILURL&gt;
        &lt;BARCODEVALUE&gt;1234578961A&lt;/BARCODEVALUE&gt;
        &lt;BARCODETEXT&gt;PASS-123-457&lt;/BARCODETEXT&gt;
        &lt;HEADERLABEL1&gt;SEAT&lt;/HEADERLABEL1&gt;
        &lt;HEADERVALUE1&gt;1C&lt;/HEADERVALUE1&gt;
        &lt;PRIMARYLABEL1&gt;Name&lt;/PRIMARYLABEL1&gt;
        &lt;PRIMARYVALUE1&gt;John Smith&lt;/PRIMARYVALUE1&gt; 
        &lt;SECLABEL1&gt;Date&lt;/SECLABEL1&gt;
        &lt;SECVALUE1&gt;4th July, 2013&lt;/SECVALUE1&gt;
        &lt;SECLABEL2&gt;Auditorium&lt;/SECLABEL2&gt;
        &lt;SECVALUE2&gt;Gold Room&lt;/SECVALUE2&gt;
        &lt;AUXLABEL1&gt;Address&lt;/AUXLABEL1&gt;
        &lt;AUXVALUE1&gt;Hyes Convention Centre, Boston MA 02144&lt;/AUXVALUE1&gt;
        &lt;BACKLABEL1&gt;Terms and Conditions&lt;/BACKLABEL1&gt;
        &lt;BACKVALUE1&gt;Valid for 1 person only. Expires July 6th, 2013. Valid ID required if requested.&lt;/BACKVALUE1&gt;
        &lt;BACKLABEL2&gt;Snacks and Drinks&lt;/BACKLABEL2&gt;
        &lt;BACKVALUE2&gt;Free Drinks and Snacks are available in the main lobby.&lt;/BACKVALUE2&gt;
        &lt;BACKLABEL3&gt;Please take a small survey to win a free ticket for our next event. &lt;/BACKLABEL3&gt;
        &lt;BACKVALUE3&gt;https://www.survey.com/event/12748493fgh/&lt;/BACKVALUE3&gt;
        &lt;RELLATITUDE2&gt;42.347888&lt;/RELLATITUDE2&gt;
        &lt;RELLONGITUDE2&gt;-71.087903&lt;/RELLONGITUDE2&gt;
        &lt;RELTEXT2&gt;Event at HYES CONVENTION CENTRE&lt;/RELTEXT2&gt;
    &lt;/PASSDATA&gt;    
&lt;/REQUEST&gt;</pre>
<div><strong>Response Example: Success</strong></div>
<pre>&lt;RESPONSE&gt;
    &lt;STATUS&gt;Success&lt;/STATUS&gt;
    &lt;MMSID&gt;35674&lt;/MMSID&gt;
    &lt;TRACKINGID&gt;TU1TXzEyMzQ2&lt;/TRACKINGID&gt;
    &lt;TO&gt;16501234123&lt;/TO&gt;
    &lt;FROM&gt;11111&lt;/FROM&gt;
&lt;/RESPONSE&gt;</pre>
<div><strong>Response Example: Failure</strong></div>
<pre>&lt;RESPONSE&gt;
    &lt;STATUS&gt;Failure&lt;/STATUS&gt;
    &lt;ERRORCODE&gt;E713&lt;/ERRORCODE&gt;
    &lt;TO&gt;16501234123&lt;/TO&gt;
    &lt;ERRORINFO&gt;There is billing problem on your account.&lt;/ERRORINFO&gt;
&lt;/RESPONSE&gt;</pre>

<div><strong>Postback Notifications For SendPassInMMS</strong></div>
<p>When the MMS delivery is processed successfully the system will generate a Postback notification.
For more details please visit <a href="https://github.com/SkycoreMobile/API/blob/master/1.3/CONTENTS/POSTBACK_NOTIFICATION_SYSTEM.md">postback doc</a></p>
<pre>&lt;?xml version='1.0'?&gt;
&lt;POSTBACK xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
xsi:noNamespaceSchemaLocation ="http://www.skycore.com/schema/postback.xsd"&gt;
&lt;ORIGIN&gt;MMS_MT&lt;/ORIGIN&gt;
&lt;CODE&gt;N101&lt;/CODE&gt;
&lt;SENTAS&gt;MMS&lt;/SENTAS&gt;
&lt;STATUS&gt;Message Sent&lt;/STATUS&gt;
&lt;MMSID&gt;35674&lt;/MMSID&gt;
&lt;TO&gt;16501234123&lt;/TO&gt;
&lt;TRACKINGID&gt;TU1TXzEyMzQ2&lt;/TRACKINGID&gt;
&lt;SPID&gt;0001890&lt;/SPID&gt;
&lt;TIMESTAMP&gt;2011-08-02T07:20:44-04:00&lt;/TIMESTAMP&gt;
&lt;/POSTBACK&gt;</pre>
<p>When an MMS delivery report is received the system will generate a Postback notification. Not all carriers provide MMS delivery receipts.</p>
<pre>
&lt;?xml version='1.0'?&gt;
&lt;POSTBACK xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
xsi:noNamespaceSchemaLocation ="http://www.skycore.com/schema/postback.xsd"&gt;
&lt;ORIGIN&gt;MMS_MT&lt;/ORIGIN&gt;
&lt;CODE&gt;N102&lt;/CODE&gt;
&lt;SENTAS&gt;MMS&lt;/SENTAS&gt;
&lt;STATUS&gt;Message Sent/Delivered&lt;/STATUS&gt;
&lt;MMSID&gt;35674&lt;/MMSID&gt;
&lt;TO&gt;16501234123&lt;/TO&gt;
&lt;TRACKINGID&gt;TU1TXzEyMzQ2&lt;/TRACKINGID&gt;
&lt;SPID&gt;0001890&lt;/SPID&gt;
&lt;TIMESTAMP&gt;2011-08-02T07:20:49-04:00&lt;/TIMESTAMP&gt;
&lt;HANDSET&gt;motol7c&lt;/HANDSET&gt;
&lt;AGGREGATORID&gt;11529-64807-97508-73852-97658&lt;/AGGREGATORID&gt;
&lt;/POSTBACK&gt;</pre>
