<a href="/1.3/README.md">Back to the Table of Contents</a>&nbsp;&nbsp;|&nbsp;&nbsp;<a href="API_METHODS.md">Back to API Methods</a>
<h2>sendSavedMMS</h2>
<p><strong>Synopsis:</strong><br />
This API sends stored content from a specified account using a MMSID to a single mobile number. FROM must be one of shortcodes allowed for your account. In case the number is from a different country than the FROM shortcode is assigned to &#8211; default shortcode for those countries will be used.</p>
<p><strong>Content Transcoding:</strong><br />
Every binary MMS we deliver can be transcoded for the destination handset and every web page we deliver is transcoded for the browsing handset. To transcode a binary MMS we must know what type of handset the user has. We are able to obtain this handset type information from delivery receipts and store the record in a handset cache for later use. We have a database of attributes which we manually match to every new handset in the cache so we can adapt the content during MMS delivery.</p>
<p>Our API allows you to dynamically change each slide text by setting up CUSTOMTEXT (value, slide) and MMS Subject by setting CUSTOMSUBJECT.
<p>A Device Discovery Message (DDM) is a short textual MMS message that is sent to the number to discover what handset the end user is using. We store this handset information in our system and reuse it, so a DDM is sent only to new numbers. If the DDM settings are not included within your API call and the number is not in the handset cache we will deliver the MMS with generic settings. If the handset is in the handset cache the DDM will not be sent and the MMS message will be transcoded and delivered immediately.</p>
<p>Our API allows you to customize DDM by setting 3 parameters:<br />
DDMTITLE &#8211; this is the DDM title (optional, if not set default will be used)<br />
DDMTEXT &#8211; this is the DDM body (mandatory)<br />
DDMTIMEOUT &#8211; when we send DDM we wait for the Delivery Report which contain the handset profile. In some cases we don&#8217;t receive it or it takes very long (handset turned off or out of range). This variable tells the system how long should it wait for DDM Delivery Report before sending actual content using Default parameters. Default value of this parameter is 5 minutes.</p>

<p>SendSavedMMS allow you to pass HandsetID inside DEVICE parameter. 
We will store this information and (if HandsetID is recognized by our system) use handset profile to adapt content for current and future MMS delivery.
<br>
NOTE: Once we receive Delivery Receipt with HandsetID we overwrite current value assigned to that number, we consider HandsetID from Delivery Receipt more up-to-date.
<br>
DEVICE parameter can be used with DDM as a fallback mechanism. If HandsetID passed in API call is not recognized by our system, it will send DDM (if specified in the request) to the handset to detect it. If there was no DDM specified in the request, system will use generic settings for MMS delivery.</p>

<div><strong>Request:</strong></div>
<pre>&lt;REQUEST&gt;
	&lt;ACTION&gt;sendSavedMMS&lt;/ACTION&gt;
	&lt;API_KEY&gt;API KEY&lt;/API_KEY&gt;
	&lt;MMSID&gt;MMSID&lt;/MMSID&gt;
	&lt;TO&gt;Number&lt;/TO&gt;
	&lt;FROM&gt;Shortcode&lt;/FROM&gt;
	&lt;CAMPAIGNREF&gt;CampaignID&lt;/CAMPAIGNREF&gt;
	&lt;DDMTITLE&gt;DDM Title&lt;/DDMTITLE&gt;
	&lt;DDMTEXT&gt;DDM Body&lt;/DDMTEXT&gt;
	&lt;DDMTIMEOUT&gt;DDM Timeout in minutes&lt;/DDMTIMEOUT&gt;
	&lt;DEVICE&gt;HandsetID&lt;/DEVICE&gt;
	&lt;CUSTOMTEXT&gt;
		&lt;VALUE&gt;Custom Text for slide&lt;/VALUE&gt;
		&lt;SLIDE&gt;Slide ID&lt;/SLIDE&gt;
	&lt;/CUSTOMTEXT&gt;
	&lt;/CUSTOMSUBJECT&gt;MMS Custom Subject&lt;/CUSTOMSUBJECT&gt;
	&lt;DATA&gt;
		&lt;FIRST_NAME&gt;First Name&lt;/FIRST_NAME&gt;
		&lt;LAST_NAME&gt;Last Name&lt;/LAST_NAME&gt;
		&lt;GENDER&gt;Gender&lt;/GENDER&gt;
		...
	&lt;/DATA&gt;        
&lt;/REQUEST&gt;</pre>
<div><strong>Request Parameters:</strong></div>
<pre><strong>Mandatory:</strong> Action, API_KEY, MMSID, To, From
<strong>Optional: </strong>CampaignRef, CustomSubject, CustomText, Data, DDMTitle, DDMText, DDMTimeout, Device</pre>
<strong>Response Parameters:</strong><br />
MMSID, Status, To, TrackingID, Errorcode, Errorinfo

<strong>Related Errorcodes: </strong><br />
E110, E111, E241, E620, E621, E623, E626, E628, E629, E713, E714, E715

<div><strong>Request Examples</strong></div>
XML:
<pre>&lt;REQUEST&gt;
	&lt;ACTION&gt; sendSavedMMS &lt;/ACTION&gt;
	&lt;API_KEY&gt;qTFkykO9JTfahCOqJ0V2Wf5Cg1t8iWlZ&lt;/API_KEY&gt;
	&lt;TO&gt;16501234123&lt;/TO&gt;
	&lt;FROM&gt;60856&lt;/FROM&gt;
	&lt;CAMPAIGNREF&gt;12333&lt;/CAMPAIGNREF&gt;
	&lt;MMSID&gt;35674&lt;/MMSID&gt;
        &lt;DDMTITLE&gt;We are detecting your handset&lt;/DDMTITLE&gt;
        &lt;DDMTEXT&gt;This message is free of charge and will allow us to deliver your content nice and smooth&lt;/DDMTEXT&gt;
        &lt;DDMTIMEOUT&gt;10&lt;/DDMTIMEOUT&gt;
        &lt;DEVICE&gt;iPhoneOS&lt;/DEVICE&gt;
        &lt;CUSTOMTEXT&gt;
        	&lt;VALUE&gt;My Custom text in first slide&lt;/VALUE&gt;
        	&lt;SLIDE&gt;1&lt;/SLIDE&gt;
        &lt;/CUSTOMTEXT&gt;
        &lt;/CUSTOMSUBJECT&gt;My Custom Subject&lt;/CUSTOMSUBJECT&gt;
	&lt;DATA&gt;
		&lt;FIRST_NAME&gt;John&lt;/FIRST_NAME&gt;
		&lt;LAST_NAME&gt;Smith&lt;/LAST_NAME&gt;
		&lt;AGE&gt;30&lt;/AGE&gt;
		&lt;PET&gt;Dog&lt;/PET&gt;
	&lt;/DATA&gt;        
&lt;/REQUEST&gt;</pre>
GET:
<pre>https://secure.skycore.com/API/wxml/1.3/index.php?action=sendsavedmms&api_key=qTFkykO9JTfahCOqJ0V2Wf5Cg1t8iWlZ
&to=16501234123&from=60856&mmsid=35674&ddmtitle=We+are+detecting+your+handset
&ddmtext=This+message+is+free+of+charge+and+will+allow+us+to+deliver+your+content+nice+and+smooth&ddmtimeout=5
&device=iPhoneOS&customtext_1=My+Custom+text+in+first+slide&customsubject=My+Custom+Subject&data_first_name=John
&data_last_name=Smith
&data_age=30&data_pet=Dog</pre>
<div><strong>Response Example: Success</strong></div>
<pre>&lt;RESPONSE&gt;
    &lt;STATUS&gt;Success&lt;/STATUS&gt;
    &lt;MMSID&gt;35674&lt;/MMSID&gt;
    &lt;TRACKINGID&gt;TU1TXzU5Nzg3OQ==&lt;/TRACKINGID&gt;
    &lt;TO&gt;16501234123&lt;/TO&gt;
    &lt;FROM&gt;60586&lt;/FROM&gt;
&lt;/RESPONSE&gt;</pre>
<div><strong>Response Example: Failure</strong></div>
<pre>&lt;RESPONSE&gt;
	 &lt;STATUS&gt;Failure&lt;/STATUS&gt;
	 &lt;ERRORCODE&gt;E713&lt;/ERRORCODE&gt;
	 &lt;TO&gt;16501234123&lt;/TO&gt;
	 &lt;ERRORINFO&gt;There is billing problem on your account&lt;/ERRORINFO&gt;
&lt;/RESPONSE&gt;</pre>
<div><strong>Postback Notifications For SendSavedMMS</strong></div>
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
&lt;TRACKINGID&gt;TU1TXzU5Nzg3OQ==&lt;/TRACKINGID&gt;
&lt;SPID&gt;0001570&lt;/SPID&gt;
&lt;TIMESTAMP&gt;2012-06-07T07:27:29-05:00&lt;/TIMESTAMP&gt;
&lt;/POSTBACK&gt;</pre>
<p>When an MMS delivery report is received the system will generate a Postback notification. Not all carriers provide MMS delivery receipts.</p>
<pre>&lt;?xml version='1.0'?&gt;
&lt;POSTBACK xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
xsi:noNamespaceSchemaLocation ="http://www.skycore.com/schema/postback.xsd"&gt;
&lt;ORIGIN&gt;MMS_MT&lt;/ORIGIN&gt;
&lt;CODE&gt;N102&lt;/CODE&gt;
&lt;SENTAS&gt;MMS&lt;/SENTAS&gt;
&lt;STATUS&gt;Message Sent/Delivered&lt;/STATUS&gt;
&lt;MMSID&gt;35674&lt;/MMSID&gt;
&lt;TO&gt;16501234123&lt;/TO&gt;
&lt;TRACKINGID&gt;TU1TXzU5Nzg3OQ==&lt;/TRACKINGID&gt;
&lt;SPID&gt;0001570&lt;/SPID&gt;
&lt;TIMESTAMP&gt;2012-06-07T07:27:34-05:00&lt;/TIMESTAMP&gt;
&lt;HANDSET&gt;motol7c&lt;/HANDSET&gt;
&lt;AGGREGATORID&gt;11529-64807-97508-73852-97658&lt;/AGGREGATORID&gt;
&lt;/POSTBACK&gt;</pre>
