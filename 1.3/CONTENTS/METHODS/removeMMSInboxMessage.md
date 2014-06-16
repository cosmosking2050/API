[Back to the Table of Contents](/1.3/README.md)&nbsp;&nbsp;|&nbsp;&nbsp;[Back to API Methods](API_METHODS.md)
## removeMMSInboxMessage
__Synopsis:__  
Immediately removes stored MMS inbox content and text files for the specified message ID (mmsinboxid), and returns the status of operation. Removing content files does not remove the transaction record. The content to remove is identified using the mmsinboxid tag, which can be obtained from MMS MO Postback notification XML inside TRACKINGID node (for details go to [SMS MO / MMS MO](https://github.com/SkycoreMobile/API/blob/master/1.3/CONTENTS/POSTBACKS/POSTBACK_SMS+MMS_MO.md)) or from UI under MMS Inbox >> Moderation Panel.

__Request:__
```xml
<REQUEST>
  <ACTION>removeMMSInboxMessage</ACTION>
    <API_KEY>API KEY</API_KEY>
    <MMSINBOXID>MMS Inbox ID</MMSINBOXID>
</REQUEST>
```

__Request Parameters:__
<pre>
<strong>Mandatory:</strong>
Action, API_KEY, MMSInboxID
<strong>Optional:</strong>
N/A
</pre>

__Response Parameters:__  
Status, MMSInboxID, Errorcode, Errorinfo

__Related Error codes:__  
E640, E641, E642, E643

__Request Example:__  
XML:
```xml
<REQUEST>
    <ACTION>removeMMSInboxMessage</ACTION>
    <API_KEY>qTFkykO9JTfahCOqJ0V2Wf5Cg1t8iWlZ</API_KEY>
    <MMSINBOXID>MMS_MO_iG7Ksa31</MMSINBOXID>
</REQUEST>
```

GET:

    https://secure.skycore.com/API/wxml/1.3/index.php?action=removemmsinboxmessage&api_key=qTFkykO9JTfahCOqJ0V2Wf5Cg1t8iWlZ
    &mmsinboxid=MMS_MO_iG7Ksa31
    
__Response Example: Success__
```xml
<RESPONSE>
    <STATUS>Success</STATUS>
    <MMSINBOXID>MMS_MO_iG7Ksa31</MMSINBOXID>
</RESPONSE>
```

__Response Example: Failure__
```xml
<RESPONSE>
    <STATUS>Failure</STATUS>
    <ERRORCODE>E641</ERRORCODE>
    <ERRORINFO>Invalid MMS Inbox Message ID</ERRORINFO>
</RESPONSE>
```
