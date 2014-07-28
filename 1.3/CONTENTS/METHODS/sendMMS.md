[Back to the Table of Contents](/1.3/README.md)

## sendMMS

__Synopsis:__  
Sends an MMS defined in the XML containing slides of embedded with video, audio, images and/or text to a single or list of mobile numbers in international number format. SendMMS is a minor extension of the saveMMS function. This API function is only available on Dedicated Shortcodes.

Prototype:
```xml
<REQUEST>
    <ACTION>sendMMS</ACTION>
    <API_KEY>apiKey</API_KEY>
    <TO>Receivers number</TO>
    <FROM>shortcode</FROM>
    <SPID>SPID</SPID>
    <CAMPAIGNREF>CampaignID</CAMPAIGNREF>
    <SUBJECT>MMS Subject</SUBJECT>
    <NAME>Name in MMBox</NAME>
    <SLIDE> 
        <IMAGE>
            <URL>URL</URL> 
        </IMAGE>
        <AUDIO>
            <URL>URL</URL>
        </AUDIO>
        <VIDEO>
            <URL>URL</URL>
        </AUDIO>
	    <TEXT>Plain Text</TEXT>
        <DURATION>Duration in seconds</DURATION>
    </SLIDE>
    <SLIDE>
       ...
    </SLIDE>
</REQUEST>
```

__Request Parameters:__

    Mandatory: action, api_key, to, from, name, slide
    Optional: spid, campaignRef, subject, image, audio, video, url, text, duration

```xml
element REQUEST {
    element ACTION { “sendMMS” } &
    element API_KEY { text } &
    element TO { text } &
    element FROM { text } &
    element SPID { text }? &
    element CAMPAIGNREF { text }? &
    element SUBJECT { text }? &
    element NAME { text } &
    element SLIDE {
        element IMAGE {
            element URL { text }
        }? &
        element AUDIO {
            element URL { text }
        }? &
        element VIDEO {
            element URL { text }
        }? &
        element TEXT { text }? &
        element DURATION { xsd:nonNegativeInteger }?    # in seconds
    }+
}
```

__Response Parameters:__

    status, to, mmsId, trackingId, errorCode, errorInfo

```xml
element RESPONSE {
    element STATUS { text } &
    element TO { text }? &
    element MMSID { text }? &
    element TRACKINGID { text }? &
    element ERRORCODE { text }? &
    element ERRORINFO { text }?
}
```

__Related Error Codes:__

    All saveMMS Error Codes plus E110, E111, E201, E628

__Request Example:__
```xml
<REQUEST>
    <ACTION>sendMMS</ACTION>
    <API_KEY>ea7966f90de2bf520e3f0042053e6ec3</API_KEY>
    <TO>15551234888</TO>
    <FROM>60856</FROM>
    <SPID>000189</SPID>
    <SUBJECT>The subject</SUBJECT>
    <CAMPAIGNREF>323</CAMPAIGNREF>
    <NAME>my fishtank</NAME>
        <SLIDE duration="5">
            <IMAGE>
                <URL>http://www.yoursite.com/images/1.jpg</URL>
            </IMAGE>
            <AUDIO>
                <URL>http://www.yoursite.com/audio/1.mp3</URL>
            </AUDIO>
            <TEXT>Here is some text tralalala....</TEXT>
        </SLIDE>
</REQUEST>
```

__Response Example: Success__
```xml
<RESPONSE>
	<STATUS>Success</STATUS>
	<TO>15551234888</TO>
    <MMSID>35674</MMSID>
	<TRACKINGID>MMS_12345</TRACKINGID>
</RESPONSE>
```

__Response Example: Failure__
```xml
<RESPONSE>
	<STATUS>Failure</STATUS>
	<ERRORCODE>E111</ERRORCODE>
	<TO>15551234888</TO>
	<ERRORINFO>Invalid shortcode</ERRORINFO>
</RESPONSE>
```
