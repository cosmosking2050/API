[Back to the Table of Contents](/1.3/README.md)

## sendMMS

__Synopsis:__  
Sends an MMS defined in the XML containing slides of embedded with video, audio, images and/or text to a single or list of mobile numbers in international number format. SendMMS is a minor extension of the saveMMS function. This API function is only available on Dedicated Shortcodes.

Prototype:
```xml
<REQUEST>
	<ACTION>sendMMS</ACTION>
	<USER>Username</USER>
	<PASS>ea7966f90de2bf520e3f0042053e6ec3</PASS>
	<FROM>shortcode/longcode</FROM>
	<SPID>SPID</SPID>
	<TO>Receivers number</TO>
    <CAMPAIGNREF>Alert CampaignID</CAMPAIGNREF>
    <SUBJECT>Subject</SUBJECT>
    <CONTENT>
	    <NAME>Name in MMBox</NAME>
	    <SEQUENCE>
		    <SLIDE duration="Duration in seconds"> 
			    <IMAGE>
				    <URL>URL</URL>
			    </IMAGE>
			    <AUDIO >
				    <URL>URL</URL>
			    </AUDIO>
			    <TEXT>Plain Text</TEXT>
		    </SLIDE>
		    <SLIDE>
		    …
		    </SLIDE>
	    </SEQUENCE>
     </CONTENT> 
</REQUEST>
```

__Request Parameters:__

    Mandatory: Action, User, Pass, To, SPID, From, Name,, Content, Sequence, Slide
    Optional: Subject, SPID, From, Image, Audio, Video, URL, Text, Duration, Campaignref

__Response Parameters:__

    Status, To, TrackingID, Errorcode, Errorinfo, MMSID

__Related Errorcodes:__

    All saveMMS Error Codes plus E110, E111, E201, E628

__Request Example:__
```xml
<REQUEST>
    <ACTION>sendMMS</ACTION>
    <USER>rakowaty</USER>
    <PASS>ea7966f90de2bf520e3f0042053e6ec3</PASS>
    <TO>15551234888</TO>
    <FROM>60856</FROM>
    <SPID>000189</SPID>
    <SUBJECT>The subject</SUBJECT>
    <CAMPAIGNREF>323</CAMPAIGNREF>
    <CONTENT>
        <NAME>fishtank</NAME>
        <SEQUENCE>
            <SLIDE duration="5">
                <IMAGE>
                    <URL>http://www.yoursite.com/images/1.jpg</URL>
                </IMAGE>
                <AUDIO>
                    <URL>http://www.yoursite.com/audio/1.mp3</URL>
                </AUDIO>
                <TEXT>Here is some text tralalala....</TEXT>
            </SLIDE>
        </SEQUENCE>
    </CONTENT>
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
