<a href="/1.3/README.md">Back to the Table of Contents</a>&nbsp;&nbsp;|&nbsp;&nbsp;<a href="API_METHODS.md">Back to API Methods</a>
<h2>sendPassInEmail</h2>
<p><strong>Synopsis:</strong><br />
'sendPassInEmail' API triggers sending a stored email template with embedded Passbook Pass in it. Pass data passed in the API will be used to create this passbook pass. 
The pass data gets locked with the email address in the request and is used in limitation to the pass template settings. All the other/extra pass data is ignored. 
Custom pass ID is your system generated unique ID that will represent this pass data. In the case of Relevance, Relevant Text is considered only when Relevance Lat and Long values are passed in the API otherwise ignored.
Also, it requires a reference email campaign to which this email address will be subscribed to. If any case, the subscription fails then the email address is added to the email campaign's audience manager as 'unsubscribed'. Subscription to the campaign may fail if: <br/>
<ol>
<li>The <i>email address</i> has already opted-out of a campaign in your account.</li>
<li>The <i>email address</i> has unsubscribed from any campaign associated with the SMTP server you are using.</li>
<li>The <i>email address</i> has filed a spam complaint.</li>
<li>The <i>email address</i> bounced during a previous delivery.</li>
</ol><br/>
On success, it will return the tracking ID referenced by 'TRACKINGID'. For more info see below for Mandatory/Optional fields and Error codes.<br/>
The email template is referenced by 'EMAILTEMPLATEID', email address is referenced by 'EMAIL', email campaign is referenced by CAMPAIGNID and the pass data is referenced by PASSDATA in the API.
</p>
<div><strong>Request: XML</strong></div>
<pre>&lt;REQUEST&gt;
    &lt;ACTION&gt;sendPassInEmail&lt;/ACTION&gt;
    &lt;API_KEY&gt;apiKey&lt;/API_KEY&gt;
    &lt;EMAILTEMPLATEID&gt;emailTemplateId&lt;/EMAILTEMPLATEID&gt;
    &lt;EMAIL&gt;email&lt;/EMAIL&gt;
    &lt;CAMPAIGNID&gt;campaignId&lt;/CAMPAIGNID&gt;
       &lt;DATA&gt;
	      &lt;FIRST_NAME&gt;First Name&lt;/FIRST_NAME&gt;
		  &lt;LAST_NAME&gt;Last Name&lt;/LAST_NAME&gt;
		  &lt;GENDER&gt;Gender&lt;/GENDER&gt;
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
API_URL?action=sendpassinemail&amp;api_key=apiKey&amp;emailtemplateid=emailTemplateId
&amp;email=email&amp;campaignid=campaignId
&amp;data_first_name=firstName&amp;data_last_name=lastname&amp;data_age=age
&amp;pd_custompassid=customPassId&amp;pd_thumbnailurl=thumbnailUrl
&amp;pd_barcodevalue=barcodeValue
&amp;pd_barcodetext=barcodeText&amp;pd_headerlabel1=headerLabel1
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
action, apiKey, email, emailTemplateId, campaignId,
barcodeValue (if "Barcode=Allowed" &amp;&amp; "BarcodeType=Dynamic" &amp;&amp; "BarcodeValueSource=Dynamic Value" for Pass Template otherwise IGNORED),

<strong>Optional: </strong>
customPassId, thumbnailUrl,
barcodeText (if "Barcode = Allowed" &amp;&amp; "Barcode Alternate Text = Dynamic Text" for Pass Template otherwise IGNORED), 
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
relLatitude10, relLongitude10, relText10</pre>
<strong>Response Parameters:</strong><br />
status, email, emailtemplateid, trackingID, Errorcode, Errorinfo

<strong>Related Errorcodes: </strong><br />
E401, E402, E713, E714, E802, E803, E806, E823, E840, E841, E842, E843, E844, E845, E846, E847, E848, E849, E850, E851, E852, E853, E854, E855, E856, E857, E858, E859, E860, E861, E862, E863, E864, E865, E866, E867, E868, E869
E870, E871, E872, E873, E874, E875, E876, E877, E878, E879, E880, E881, E882, E883, E884, E885, E886, E887, E888, E889, E890, E891, E892, E893, E894, E895, E896, E897, E898, E899, E915, E916, E917

<div><strong>Request Example:</strong></div>
<pre>&lt;REQUEST&gt;
    &lt;ACTION&gt;sendPassInEmail&lt;/ACTION&gt;
    &lt;API_KEY&gt;qTFkykO9JTfahCOqJ0V2Wf5Cg1t8iWlZ&lt;/API_KEY&gt;
    &lt;EMAILTEMPLATEID&gt;45633&lt;/EMAILTEMPLATEID&gt;
    &lt;EMAIL&gt;vik.muth@mail.com&lt;/EMAIL&gt;
    &lt;CAMPAIGNID&gt;1233&lt;/CAMPAIGNID&gt;
       &lt;DATA&gt;
    	  &lt;FIRST_NAME&gt;John&lt;/FIRST_NAME&gt;
    	  &lt;LAST_NAME&gt;Smith&lt;/LAST_NAME&gt;
    	  &lt;AGE&gt;29&lt;/AGE&gt;
    	  &lt;PET&gt;Dog&lt;/PET&gt;
       &lt;/DATA&gt;
    &lt;PASSDATA&gt;
    	&lt;THUMBNAILURL&gt;http://andreas.com/pixs/steve-jobs.png&lt;/THUMBNAILURL&gt;
        &lt;BARCODEVALUE&gt;1234578961A&lt;/BARCODEVALUE&gt;
        &lt;BARCODETEXT&gt;PASS-123-457&lt;/BARCODETEXT&gt;
        &lt;HEADERLABEL1&gt;SEAT&lt;/HEADERLABEL1&gt;
        &lt;HEADERVALUE1&gt;1C&lt;/HEADERVALUE1&gt;
        &lt;PRIMARYLABEL1&gt;Name&lt;/PRIMARYLABEL1&gt;
        &lt;PRIMARYVALUE1&gt;Vikram Muthyala&lt;/PRIMARYVALUE1&gt; 
        &lt;SECLABEL1&gt;Date&lt;/SECLABEL1&gt;
        &lt;SECVALUE1&gt;4th July, 2013&lt;/SECVALUE1&gt;
        &lt;SECLABEL2&gt;Auditorium&lt;/SECLABEL2&gt;
        &lt;SECVALUE2&gt;Gold Room&lt;/SECVALUE2&gt;
        &lt;AUXLABEL1&gt;Address&lt;/AUXLABEL1&gt;
        &lt;AUXVALUE1&gt;Biz Convention Center, Boston MA 02144&lt;/AUXVALUE1&gt;
        &lt;BACKLABEL1&gt;Terms and Conditions&lt;/BACKLABEL1&gt;
        &lt;BACKVALUE1&gt;Valid for 1 person only. Valid for 1 visit only. Expires July 6th, 2013. Valid ID required if requested.&lt;/BACKVALUE1&gt;
        &lt;BACKLABEL2&gt;Snacks and Drinks&lt;/BACKLABEL2&gt;
        &lt;BACKVALUE2&gt;Free Drinks and Snacks are available in the main lobby.&lt;/BACKVALUE2&gt;
        &lt;BACKLABEL3&gt;Please take a small survey to win a free ticket for our next event&lt;/BACKLABEL3&gt;
        &lt;BACKVALUE3&gt;https://www.survey.com/event/12748493fgh/&lt;/BACKVALUE3&gt;
        &lt;RELLATITUDE2&gt;42.347888&lt;/RELLATITUDE2&gt;
        &lt;RELLONGITUDE2&gt;-71.087903&lt;/RELLONGITUDE2&gt;
        &lt;RELTEXT2&gt;Event at HYNES CONVENTION CENTRE&lt;/RELTEXT2&gt;
    &lt;/PASSDATA&gt;    
&lt;/REQUEST&gt;</pre>
<div><strong>Response Example: Success</strong></div>
<pre>&lt;RESPONSE&gt;
    &lt;STATUS&gt;Success&lt;/STATUS&gt;
    &lt;EMAILTEMPLATEID&gt;35674&lt;/EMAILTEMPLATEID&gt;
    &lt;TRACKINGID&gt;EMAIL_12346&lt;/TRACKINGID&gt;
    &lt;EMAIL&gt;vik.muth@mail.com&lt;/EMAIL&gt;
    &lt;CAMPAIGNID&gt;1233&lt;/CAMPAIGNID&gt;
&lt;/RESPONSE&gt;</pre>
<div><strong>Response Example: Failure</strong></div>
<pre>&lt;RESPONSE&gt;
    &lt;STATUS&gt;Failure&lt;/STATUS&gt;
    &lt;EMAILTEMPLATEID&gt;35674&lt;/EMAILTEMPLATEID&gt;
    &lt;ERRORCODE&gt;E713&lt;/ERRORCODE&gt;
    &lt;ERRORINFO&gt;There is billing problem on your account.&lt;/ERRORINFO&gt;
    &lt;EMAIL&gt;vik.muth@mail.com&lt;/EMAIL&gt;
    &lt;CAMPAIGNID&gt;1233&lt;/CAMPAIGNID&gt;
&lt;/RESPONSE&gt;</pre>
