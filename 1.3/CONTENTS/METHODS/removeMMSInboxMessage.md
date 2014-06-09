<a href="/1.3/README.md">Back to the Table of Contents</a>&nbsp;&nbsp;|&nbsp;&nbsp;<a href="API_METHODS.md">Back to API Methods</a>
<h2>removeMMSInboxMessage</h2>
<p><strong>Synopsis:</strong><br />
Immediately removes all stored inbox content and text files attached to the MMS inbox and return the status of operation. Removing content files does not remove the transaction record. The content to remove is identified using the mmsinboxid tag, which can be obtained from MMS MO Postback notification XML inside TRACKINGID node (for details go to <a href="https://github.com/SkycoreMobile/API/blob/master/1.3/CONTENTS/POSTBACKS/POSTBACK_SMS+MMS_MO.md">SMS MO / MMS MO</a>) or from UI under MMS Inbox &gt;&gt; Moderation Panel</p>
<div><strong>Request:</strong></div>
<pre>&lt;REQUEST&gt;
  &lt;ACTION&gt;removeMMSInboxMessage&lt;/ACTION&gt;
	&lt;API_KEY&gt;API KEY&lt;/API_KEY&gt;
	&lt;MMSINBOXID&gt;MMS Inbox ID&lt;/MMSINBOXID&gt;
&lt;/REQUEST&gt;</pre>
<div><strong>Request Parameters:</strong></div>
<pre><strong>Mandatory:</strong> Action, API_KEY, MMSInboxID
<strong>Optional:</strong> N/A</pre>
<strong>Response Parameters:</strong><br />
Status, MMSInboxID, Errorcode, Errorinfo
<strong>Related Error codes: </strong><br />
E640, E641, E642, E643
<div><strong>Request Examples</strong></div>
XML:
<pre>&lt;REQUEST&gt;
    &lt;ACTION&gt;removeMMSInboxMessage&lt;/ACTION&gt;
    &lt;API_KEY&gt;qTFkykO9JTfahCOqJ0V2Wf5Cg1t8iWlZ&lt;/API_KEY&gt;
    &lt;MMSINBOXID&gt;MMS_MO_iG7Ksa31&lt;/MMSINBOXID&gt;
&lt;/REQUEST&gt;</pre>
GET:
<pre>https://secure.skycore.com/API/wxml/1.3/index.php?action=removemmsinboxmessage&api_key=qTFkykO9JTfahCOqJ0V2Wf5Cg1t8iWlZ
&mmsinboxid=MMS_MO_iG7Ksa31</pre>
<div><strong>Response Example: Success</strong></div>
<pre>&lt;RESPONSE&gt;
    &lt;STATUS&gt;Success&lt;/STATUS&gt;
    &lt;MMSINBOXID&gt;MMS_MO_iG7Ksa31&lt;/MMSINBOXID&gt;
&lt;/RESPONSE&gt;</pre>
<div><strong>Response Example: Failure</strong></div>
<pre>&lt;RESPONSE&gt;
    &lt;STATUS&gt;Failure&lt;/STATUS&gt;
    &lt;ERRORCODE&gt;E641&lt;/ERRORCODE&gt;
    &lt;ERRORINFO&gt;Invalid MMS Inbox ID&lt;/ERRORINFO&gt;
&lt;/RESPONSE&gt;</pre>
