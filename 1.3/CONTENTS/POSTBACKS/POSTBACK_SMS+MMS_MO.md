<a href="/1.3/README.md">Back to the Table of Contents</a>&nbsp;&nbsp;|&nbsp;&nbsp;<a href="/1.3/CONTENTS/POSTBACKS/POSTBACK_SYSTEM_OVERVIEW.md">Postback System Overview</a>
<h2>SMS/MMS MO Postbacks</h2>
<div id="page-content"><strong>Brief Overview:</strong>
This document will provide a technical description of the SMS/MMS MO postback API. Briefly, this API allows those with an SMS/MMS MO-enabled shortcode to forward received messages (SMS/MMS MO) to their server.

<strong>SMS/MMS MO-Specific URL:</strong>
A separate Postback URL specifically for SMS/MMS MO's(Mobile Originated) may be be set via the API Settings tab of your account.  If it is not set, all postbacks will be sent to the Postback URL that is set.

<strong>SMS MO General Information:</strong>
To receive SMS MO postback notifications you need to have that option enabled in your account. Once the SMS MO 
postback is enabled you will start receiving postbacks to the URL of your choice for each SMS MO received related to 
your account.

<strong>MMS MO General Information</strong>
To receive MMS MO postback notification you need to have that option enabled in your account and you need to 
configure it within the particular MMS MO campaign.  Once the MMS MO postback is enabled you will start receiving 
postbacks to the URL of your choice for each MMS MO received on the MMS MO Keyword. If you have opted to enable
the MMS MO moderation panel, then the postback notifictions will only be sent upon manual approval of the moderator.



<a name="SMS"><strong>The SMS MO</strong></a>
<p><strong>Synopsis: </strong>This postback provides a notification when SMS MO is received.</p>
<strong><p>This postback will contain the following nodes:</p></strong>

CODE, ORIGIN<BR/>
FROM &#8211; SMS sender mobile number<BR/>
TO &#8211; shortcode the SMS was sent to<BR/>
TEXT &#8211; this is actuall text that was sent by the sender<BR/>
RECEIVED &#8211; timestamp of the SMS received by our server<BR/>
TRANSACTIONID &#8211; transactionId for the SMS MO transaction that occurred<BR/>

<p><strong>This postback has the following anatomy:</strong></p>
<pre>
&lt;POSTBACK&gt;
  &lt;ORIGIN&gt;SMS_MO&lt;/ORIGIN&gt;
  &lt;CODE&gt;N211&lt;/CODE&gt;
  &lt;FROM&gt;15552312102&lt;/FROM&gt;
  &lt;TO&gt;86717&lt;/TO&gt;
  &lt;TEXT&gt;STOP&lt;/TEXT&gt;
  &lt;RECEIVED&gt;2011-09-28T17:31:02-04:00&lt;/RECEIVED&gt;
  &lt;TRANSACTIONID&gt;511XG-02294-192SA-482H8&lt;/TRANSACTIONID&gt;
&lt;/POSTBACK&gt;
</pre>


<a name="MMS"><p><strong>The MMS MO</strong></p></a>
<p><strong>Synopsis: </strong>This postback provides a notification when MMS MO is received.</p> 
<strong><p>This postback will contain the following nodes:</p></strong>

CODE, ORIGIN<BR/>
NOTIFICATION &#8211; SMS sender mobile number<BR/>
FROM &#8211; tags contain the phone number, including the country code, of the sender.<BR/>
TO &#8211; tags contain the destination shortcode.<BR/>
KEYWORD &#8211; tags contain the keyword recognized that was passed in the MMS.<BR/>
TRACKINGID &#8211; tags contain a tracking ID, which contains the ID we've assigned this MMS MO on our system.<BR/>
SPID &#8211; tags contain the SPID of the sender's carrier.<BR/>
TIMESTAMP &#8211; tags contain the timestamp that our system received the MMS MO.<BR/>
CONTENT &#8211; contains the file nodes sent in the MMS MO<BR/>
FILE &#8211; contains a single URL to a picture, video, audio or text file sent in the MMS MO.  The URL points to the location of the content on our servers. For those developing the back-end handling of the postback URL, you may choose to download/store these content files for whatever purpose you see fit. You may also choose to store the URLs for download at a future time.<BR/>
<p><strong>This postback has the following anatomy:</strong></p>
<pre>
&lt;POSTBACK&gt;
  &lt;NOTIFICATION&gt;
    &lt;ORIGIN&gt;MMS_MO&lt;/ORIGIN&gt;
    &lt;CODE&gt;N401&lt;/CODE&gt;
    &lt;FROM&gt;13217949521&lt;/FROM&gt;
    &lt;TO&gt;74700&lt;/TO&gt;
    &lt;KEYWORD&gt;all&lt;/KEYWORD>
    &lt;TRACKINGID&gt;MMS_MO_iLnCRrL6&lt;/TRACKINGID&gt;
    &lt;SPID&gt;0001470&lt;/SPID&gt;
    &lt;TIMESTAMP&gt;2014-02-03T11:19:49-05:00&lt;/TIMESTAMP&gt;
    &lt;CONTENT&gt;
      &lt;FILE&gt;URL of Content Here&lt;/FILE&gt;
      &lt;FILE&gt;URL of Content Here&lt;/FILE&gt;
      &lt;FILE&gt;URL of Content Here&lt;/FILE&gt;
    &lt;/CONTENT&gt;
  &lt;/NOTIFICATION&gt;
&lt;/POSTBACK&gt;
</pre>
