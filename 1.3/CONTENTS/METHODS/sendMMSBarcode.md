<a href="/1.3/README.md">Back to the Table of Contents</a>&nbsp;&nbsp;|&nbsp;&nbsp;<a href="API_METHODS.md">Back to API Methods</a>
<h2>sendMMSBarcode</h2>
<p><strong>Synopsis:</strong><br />
This API function sends stored MMS containing a barcode database template from a specified account using a MMSID to a one number. 
BarcodeID passed in the request along with the phone number is added to Database. 
The BarcodeID is encoded into a barcode image which is inserted into the MMS and delivered to the number.
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
<br />
<strong>NOTE:</strong> BarcodeID passed in an API call will always be used even for Databases with 'Always generate new IDs' switch set to 'Yes' <BR/>
<div><strong>Request:</strong></div>
<pre>&lt;REQUEST&gt;
  &lt;ACTION&gt;sendMMSBarcode&lt;/ACTION&gt;
	&lt;API_KEY&gt;API KEY&lt;/API_KEY&gt;
	&lt;MMSID&gt;MMSID&lt;/MMSID&gt;
	&lt;TO&gt;Number&lt;/TO&gt;
        &lt;FROM&gt;Shortcode&lt;/FROM&gt;
        &lt;BARCODEID&gt;BarcodeID&lt;/BARCODEID&gt;
        &lt;CAMPAIGNREF&gt;CampaignID&lt;/CAMPAIGNREF&gt;
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
&lt;/REQUEST&gt;</pre>
<div><strong>Request Parameters:</strong></div>
<pre><strong>Mandatory:</strong> action, api_key, mmsid, to, barcodeid, from
<strong>Optional: </strong>campaignref, ddmtitle, ddmtext, ddmtimeout, device, customsubject, customText, data </pre>
<strong>Response Parameters:</strong><br />
mmsid, status, to, trackingid, errorcode, errorinfo
<strong>Related Errorcodes: </strong><br />
E110, E111, E241, E620, E621, E623, E626, E628, E629, E630, E631, E632, E633, E713, E714, E715
  
<div><strong>Request Examples</strong></div>
XML:
<pre>&lt;REQUEST&gt;
	&lt;ACTION&gt;sendMMSBarcode&lt;/ACTION&gt;
	&lt;API_KEY&gt;qTFkykO9JTfahCOqJ0V2Wf5Cg1t8iWlZ&lt;/API_KEY&gt;
	&lt;TO&gt;16501234123&lt;/TO&gt;
        &lt;FROM&gt;60856&lt;/FROM&gt;
        &lt;BARCODEID&gt;Ticket_12345&lt;/BARCODEID&gt;
        &lt;CAMPAIGNREF&gt;12333&lt;/CAMPAIGNREF&gt;
	&lt;MMSID&gt;35674&lt;/MMSID&gt;
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
&lt;/REQUEST&gt;</pre>
GET:
<pre>https://secure.skycore.com/API/wxml/1.3/index.php?action=sendmmsbarcode&amp;api_key=qTFkykO9JTfahCOqJ0V2Wf5Cg1t8iWlZ
&amp;to=16501234123&amp;from=60856&amp;barcodeid=Ticket_12345&amp;campaignref=12333&amp;mmsid=35674&amp;ddmtitle=We+are+detecting+your+handset
&amp;ddmtext=This+message+is+free+of+charge+and+will+allow+us+to+deliver+your+content+nice+and+smooth&amp;ddmtimeout=5
&amp;device=iPhoneOS&amp;customtext_1=My+Custom+text+in+first+slide&amp;customsubject=My+Custom+Subject&amp;data_first_name=John
&amp;data_last_name=Smith&amp;data_age=30&amp;data_gender=male</pre>
<div><strong>Response Example: Success</strong></div>
<pre>&lt;RESPONSE&gt;
    &lt;STATUS&gt;Success&lt;/STATUS&gt;
    &lt;MMSID&gt;35674&lt;/MMSID&gt;
    &lt;TRACKINGID&gt;TU1TXzEyMzQ2&lt;/TRACKINGID&gt;
    &lt;TO&gt;16501234123&lt;/TO&gt;
&lt;/RESPONSE&gt;</pre>
<div><strong>Response Example: Failure</strong></div>
<pre>&lt;RESPONSE&gt;
    &lt;STATUS&gt;Failure&lt;/STATUS&gt;
    &lt;ERRORCODE&gt;E713&lt;/ERRORCODE&gt;
    &lt;TO&gt;16501234123&lt;/TO&gt;
    &lt;ERRORINFO&gt;There is billing problem on your account&lt;/ERRORINFO&gt;
&lt;/RESPONSE&gt;</pre>

<div><strong>Postback Notifications For SendMMSBarcode</strong></div>
<p>When the MMS delivery is processed successfully the system will generate a Postback notification.
For more details please visit <a href="https://github.com/SkycoreMobile/API/blob/master/1.3/CONTENTS/POSTBACK_NOTIFICATION_SYSTEM.md">postback doc</a></p>
<pre>&lt;?xml version='1.0'?&gt;
&lt;POSTBACK xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
xsi:noNamespaceSchemaLocation ="http://www.skycore.com/platform/schema/postback.xsd"&gt;
&lt;ORIGIN&gt;MMS_MT&lt;/ORIGIN&gt;
&lt;CODE&gt;N101&lt;/CODE&gt;
&lt;SENTAS&gt;MMS&lt;/SENTAS&gt;
&lt;STATUS&gt;Message Sent&lt;/STATUS&gt;
&lt;MMSID&gt;35674&lt;/MMSID&gt;
&lt;TO&gt;16501234123&lt;/TO&gt;
&lt;TRACKINGID&gt;TU1TXzEyMzQ2&lt;/TRACKINGID&gt;
&lt;SPID&gt;0001890&lt;/SPID&gt;
&lt;TIMESTAMP&gt;2011-08-02T07:20:44-04:00&lt;/TIMESTAMP&gt;
&lt;/POSTBACK&gt;
</pre>
<p>When an MMS delivery report is received the system will generate a Postback notification. Not all carriers provide MMS delivery receipts.</p>
<pre>&lt;?xml version='1.0'?&gt;
&lt;POSTBACK xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
xsi:noNamespaceSchemaLocation ="http://www.skycore.com/platform/schema/postback.xsd"&gt;
&lt;ORIGIN&gt;MMS_MT&lt;/ORIGIN&gt;
&lt;CODE&gt;N102&lt;/CODE&gt;
&lt;SENTAS&gt;MMS&lt;/SENTAS&gt;
&lt;STATUS&gt;Message Sent/Delivered&lt;/STATUS&gt;
&lt;MMSID&gt;35674&lt;/MMSID&gt;
&lt;TO&gt;16501234123&lt;/TO&gt;
&lt;TRACKINGID&gt;TU1TXzEyMzQ2&lt;/TRACKINGID&gt;
&lt;SPID&gt;0001890&lt;/SPID&gt;
&lt;TIMESTAMP&gt;2011-08-02T07:21:04-04:00&lt;/TIMESTAMP&gt;
&lt;HANDSET&gt;motol7c&lt;/HANDSET&gt;
&lt;AGGREGATORID&gt;11529-64807-97508-73852-97658&lt;/AGGREGATORID&gt;
&lt;/POSTBACK&gt;</pre>

