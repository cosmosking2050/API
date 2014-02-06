<a href="/1.3/README.md">Back to the Table of Contents</a>
<h2>Incoming&nbsp;SMS/MMS&nbsp;Postback</h2>
<div id="page-content"><p><strong>Brief Overview:</strong></p>
<p>This document will provide a technical description of the MMS/SMS MO POSTBACK API. In brief, this API allows those with an 
SMS/MMS MO-enabled shortcode to forward received messages (MMS/SMS MO) to your server.</p>
<p><strong>SMS MO</strong></p>
<p>To receive SMS MO postback notification you need to have that option enabled in your account. Once the SMS MO 
postback is enabled you will start receiving HTTP Posts on URL of your choice for each SMS MO received related to 
your account.</p>
<p><strong>MMS MO</strong></p>
<p>To receive MMS MO postback notification you need to have that option enabled in your account and you need to 
configure it within the particular MMS MO campaign.  Once the MMS MO postback is enabled you will start receiving 
HTTP Posts on URL of your choice for each MMS MO received on the MMS MO Keyword. If you have (optionally) enabled 
the MMS MO moderation panel then the postback notifictions will only be sent upon manual approval by the moderator.</p>
<p><a name="the_xml_bundle1"></a> <strong>The SMS MO XML:</strong></p>
<p>The XML has the following anatomy:</p>
<p>
<pre>
&lt;POSTBACK&gt;<br />
&lt;ORIGIN&gt;SMS_MO&lt;/ORIGIN&gt;<br />
&lt;CODE&gt;N211&lt;/CODE&gt;<br />
&lt;FROM&gt;15552312102&lt;/FROM&gt;<br />
&lt;TO&gt;86717&lt;/TO&gt;<br />
&lt;TEXT&gt;STOP&lt;/TEXT&gt;<br />
&lt;RECEIVED&gt;2011-09-28T17:31:02-04:00&lt;/RECEIVED&gt;<br />
&lt;/POSTBACK&gt;</p>
</pre>
<p><a name="the_xml_bundle"></a> <strong>The MMS MO XML:</strong></p>
<p>The XML has the following anatomy:</p>
<pre>
<p>&lt;POSTBACK&gt;<br />
&lt;ORIGIN&gt;MMS_MO&lt;/ORIGIN&gt;<br />
&lt;CODE&gt;N401&lt;/CODE&gt;<br />
&lt;FROM&gt;15552312102&lt;/FROM&gt;<br />
&lt;TO&gt;86717&lt;/TO&gt;<br />
&lt;KEYWORD&gt;testoffer&lt;/KEYWORD&gt;<br />
&lt;TRACKINGID&gt;MMS_MO_vp8Vsf2M&lt;/TRACKINGID&gt;<br />
&lt;SPID&gt;0001650&lt;/SPID&gt;<br />
&lt;TIMESTAMP&gt;2011-09-28T15:25:30-04:00&lt;/TIMESTAMP&gt;<br />
&lt;CONTENT&gt;<br />
&lt;FILE&gt;&#8230;URL of Content Here&#8230;&lt;/FILE&gt;<br />
&lt;FILE&gt;&#8230;URL of Content Here&#8230;&lt;/FILE&gt;<br />
&lt;FILE&gt;&#8230;URL of Content Here&#8230;&lt;/FILE&gt;<br />
&lt;/CONTENT&gt;<br />
&lt;/POSTBACK&gt;</p>
</pre>

<p>Each MMS MO message is represented by a &lt;POSTBACK&gt; tag and all of the nodes and data contained within. When
new MMS MO are received by our system, and approved in the moderation panel, postback message is generated and instantly sent to your postback URL.</p>

<p>The content node contains all of the pictures, videos, audio, text, and smil that compose the received MMS MO message. 
The URL points to the location of the content on our servers. For those developing the back-end handling of the postback
URL, you may choose to download/store these content files for whatever purpose you see fit. You may also choose to store
the URLs for download at a future time.</p>

<p><a name="breaking_down_each_notification"></a> <strong>Breaking down Each Notification</strong></p>
<p>Many of the tags are self-explanatory.</p>
<ul>
<li>&lt;FROM&gt;&lt;/FROM&gt; tags contain the phone number, including the country code, of the sender.</li>
<li>&lt;TO&gt;&lt;/TO&gt; tags contain the destination shortcode. In the above example, shortcode is 86717.</li>
<li>&lt;KEYWORD&gt;&lt;/KEYWORD&gt; tags contain the keyword recognized that was passed in the MMS.</li>
<li>&lt;TEXT&gt;&lt;/TEXT&gt; tags contain the full text that was sent in the SMS.</li>
<li>&lt;TRACKINGID&gt;&lt;/TRACKINGID&gt; tags contain a tracking ID, which contains the ID we&#8217;ve assigned this MMS MO on our system.</li>
<li>&lt;RECEIVED&gt;&lt;/RECEIVED&gt; tags contain the timestamp when the SMS MO was received by our side.</li>
<li>&lt;SPID&gt;&lt;/SPID&gt; tags contain the SPID of the sender&#8217;s carrier. In the above example, 0001650 
corresponds to the mobile carrier Sprint. For the full list of SPIDs and their corresponding carriers, please refer to 
the SPID reference table in the last section.</li>
<li>&lt;TIMESTAMP&gt;&lt;/TIMESTAMP&gt; tags contain the timestamp that our system received the MMS MO.</li>
</ul>
<p><a name="setting_your_postback_url"></a> <strong>Setting your Postback URL:</strong></p>
<p>You can set your postback URL by logging into your account and going to &#8216;Account&#8217; tab and selecting the 
&#8216;API settings&#8217; button. Enter the URL under the setting &#8216;API Postback URL&#8217; and make sure that the &#8216;enabled&#8217; and &#8216;MMS MO postback&#8217; checkboxes are selected. Hit the save button and any MMS MO campaign you&#8217;ve created with &#8216;Postback Processing&#8217; enabled will start sending messages to your URL in the XML format shown above.</p>
