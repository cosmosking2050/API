[Back to the Table of Contents](/1.3/README.md)

## removeMMSInboxMessage

__Synopsis:__  
Immediately removes stored MMS inbox content and text files for the specified message ID (mmsinboxid), and returns the status of operation. Removing content files does not remove the transaction record. The content to remove is identified using the mmsinboxid tag, which can be obtained from MMS MO Postback notification XML inside TRACKINGID node (for details go to [SMS/MMS MO Postbacks](https://github.com/SkycoreMobile/API/blob/master/1.3/CONTENTS/POSTBACKS/POSTBACK_MESSAGE_INBOX.md)) or from UI under MMS Inbox >> Moderation Panel.

__Request:__
```xml
<REQUEST>
    <ACTION>removeMMSInboxMessage</ACTION>
    <API_KEY>apiKey</API_KEY>
    <MMSINBOXID>MMS Inbox ID</MMSINBOXID>
</REQUEST>
```

__Request Parameters:__

    Mandatory: action, api_key, mmsInboxId
    Optional: N/A

__Response Parameters:__

    status, mmsInboxId, errorCode, errorInfo

__Related Error Codes:__

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