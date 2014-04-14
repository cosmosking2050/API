<a href="/1.3/README.md">Back to the Table of Contents</a>&nbsp;&nbsp;|&nbsp;&nbsp;<a href="API_METHODS.md">Back to API Methods</a>
<h2>saveMMS</h2>
<b>Synopsis</b>:
&nbsp;
This API stores an MMS from XML. The MMS may contain slides embedded with video, audio, images and text. 
Once the MMS is saved it can be utilized by other functions through the MMSID returned.  The legacy format is still supported at this time, but it is recommended that developers update to the most recent format at their earliest convenience.

<b>Request</b>:
<pre>&lt;REQUEST&gt;
    &lt;ACTION&gt;saveMMS&lt;/ACTION&gt;
    &lt;API_KEY&gt;API KEY&lt;/API_KEY&gt;
    &lt;SUBJECT&gt;Subject &lt;/SUBJECT&gt;
    &lt;NAME&gt;Name to save it as&lt;/NAME&gt;
    &lt;SLIDE&gt;
    	&lt;IMAGE&gt;&lt;URL&gt;URL&lt;/URL&gt;&lt;/IMAGE&gt;
    	&lt;AUDIO&gt;&lt;URL&gt;URL&lt;/URL&gt;&lt;/AUDIO&gt;
    	&lt;TEXT&gt;Plain Text&lt;/TEXT&gt;
    	&lt;DURATION&gt;Duration in seconds&lt;/DURATION&gt;
    &lt;/SLIDE&gt;
    &lt;SLIDE&gt;
    	...
    &lt;/SLIDE&gt;
&lt;/REQUEST&gt;
</pre>

<div><strong>Request Parameters:</strong></div>
<pre><strong>Mandatory:</strong> Action, API_KEY, Name, Subject, Slide
<strong>Optional:</strong>Image, Audio, Video, URL, Text, Duration</pre>

<strong>Response Parameters:</strong><br/>
Status, TrackingID, Errorcode, Errorinfo, MMSID

<strong>Related Errorcodes:</strong><br/> 
E225, E226, E227, E228, E229, E230, E331, E332, E333, E334, E341, E351

<div><strong>Request Example:</strong></div>
<pre>&lt;REQUEST&gt;
	&lt;ACTION&gt;saveMMS&lt;/ACTION&gt;
	&lt;API_KEY&gt;qTFkykO9JTfahCOqJ0V2Wf5Cg1t8iWlZ&lt;/API_KEY&gt;
	&lt;SUBJECT&gt;The subject &lt;/SUBJECT&gt;
	&lt;NAME&gt;fishtank&lt;/NAME&gt;
	&lt;SLIDE&gt;
		&lt;IMAGE&gt;&lt;URL&gt;http://www.yoursite.com/images/1.jpg&lt;/URL&gt;&lt;/IMAGE&gt;
		&lt;AUDIO&gt;&lt;URL&gt;http://www.yoursite.com/audio/1.mp3&lt;/URL&gt;&lt;/AUDIO&gt;
		&lt;TEXT&gt;Here is some text&lt;/TEXT&gt;
		&lt;DURATION&gt;5&lt;/DURATION&gt;
	&lt;/SLIDE&gt;
&lt;/REQUEST&gt;
</pre>

<div><strong>Response Example:</strong></div> 
Success
<pre>&lt;RESPONSE&gt;
	&lt;STATUS&gt;Success&lt;/STATUS&gt;
	&lt;MMSID&gt;35674&lt;/MMSID&gt;
&lt;/RESPONSE&gt;		
</pre>

<div><strong>Response Example:</b> Failure</strong></div>
<pre>&lt;RESPONSE&gt;
	&lt;STATUS&gt;Failure&lt;/STATUS&gt;
	&lt;ERRORCODE&gt;E111&lt;/ERRORCODE&gt;
	&lt;ERRORINFO&gt;Invalid shortcode&lt;/ERRORINFO&gt;
&lt;/RESPONSE&gt;
</pre>

<div><strong>Postback Notifications</strong></div>
	When the MMS is saved system will generate a Postback notification and unlock MMS for further use. 
	If MMS contain audio/video Postback will be sent when encoding of MMS Audio/Video is finished, otherwise 
	Postback notification will be sent instantly. Below is example of Postback notification when MMS saved 
	successfully:
<pre>&lt;NOTIFICATION CREATED="2011-01-01 20:09:12.975911-04"ID="325"&gt;
	&lt;ORIGIN&gt;MMS_MT&lt;/ORIGIN&gt;
	&lt;CODE&gt;N003&lt;/CODE&gt;
	&lt;BODY&gt;
	    &lt;MMSID&gt;35674&lt;/MMSID&gt;
	&lt;/BODY&gt;
&lt;/NOTIFICATION&gt;	
</pre>

If there was an error encoding MMS audio/video system will generate notification:
<pre>&lt;NOTIFICATION ID="325" CREATED="2011-01-01 20:09:12.975911-04"&gt;
	&lt;ORIGIN&gt;MMS_MT&lt;/ORIGIN&gt;
    	&lt;CODE&gt;E002&lt;/CODE&gt;
    	&lt;BODY&gt;
    		&lt;MMSID&gt;35674&lt;/MMSID&gt;
        	&lt;AUDIONAME&gt;sample.mp3&lt;/AUDIONAME&gt;
    	&lt;/BODY&gt;
&lt;/NOTIFICATION&gt;
</pre>

<strong>Special Considerations for saveMMS:</strong><br/>
The API SHALL reformat the content when necessary so that it can be delivered to the end users handset in the best 
possible way.Delivery success takes precedence over audio and video content quality and occasionally the picture quality
will be reduced to fit handset message size requirements. Video SHALL be reduced in quality to fit delivery limitations 
and if it still does not fit it will be delivered as XHTML/SMS. Each request MUST contain at least one slide which MAY 
contain text and/or image and/or video and/or sound. The API SHALL support up to 80 characters in the MMS subject. The API SHALL support up to 8 slides for each MMS submission.
The API SHALL NOT support multiple files of the same MIME type on the same slide. Slides with image SHALL NOT support 
video but SHALL support audio. Slides with audio SHALL NOT support video. Slides with video SHALL only support text. 
Slides with text SHALL support up to 5000 characters in any slide.
URLS within the text MAY be replaced by a link shortening URL depending on the API account settings.
All slides MAY contain a duration for playback. Default slide duration is 5 seconds. Slide duration will be overwritten 
if the file duration exceeds the xml duration.
URLs provided MUST contain the full path to the mime files.
Slide Duration SHOULD NOT exceed 30 seconds and SHALL NOT exceeds 60 seconds.
MMS is delivered to the handset using title: NAME from ACCOUNT, if SUBJECT is not passed.
MMS containing audio/video can be used only when audio/video encoding is completed. After submission you will not be given a successful acknowledgement of audio/video encoding when a message is submitted. The HTTP status of audio/video encoding after it has been completed will be sent to your Postback URL.
Supported Media: TEXT/PLAIN, GIF/JPG/PNG, MP3/WAV, 3GP, MP4, MPEG, MPG, AVI, WMV
There is a maximum source file size for each supported source file submitted. You can find out what the current maximum is by visiting your API settings.
