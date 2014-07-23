[Back to the Table of Contents](/1.3/README.md)

## saveMMS

__Synopsis:__  
This API stores an MMS from XML. The MMS may contain slides embedded with video, audio, images and text. Once the MMS is saved, it can be utilized by other functions through the MMSID returned. The legacy format is still supported at this time, but it is recommended that developers update to the most recent format at their earliest convenience.

__Request:__
```xml
<REQUEST>
    <ACTION>saveMMS</ACTION>
    <API_KEY>API KEY</API_KEY>
    <SUBJECT>Subject </SUBJECT>
    <NAME>Name to save it as</NAME>
    <SLIDE>
        <IMAGE><URL>URL</URL></IMAGE>
        <AUDIO><URL>URL</URL></AUDIO>
        <TEXT>Plain Text</TEXT>
        <DURATION>Duration in seconds</DURATION>
    </SLIDE>
    <SLIDE>
        ...
    </SLIDE>
</REQUEST>
```

__Request Parameters:__

    Mandatory: Action, API_KEY, Name, Subject, Slide
    Optional: Image, Audio, Video, URL, Text, Duration

__Response Parameters:__

    Status, TrackingID, Errorcode, Errorinfo, MMSID

__Related Errorcodes:__

    E225, E226, E227, E228, E229, E230, E331, E332, E333, E334, E341, E351

__Request Example:__
```xml
<REQUEST>
    <ACTION>saveMMS</ACTION>
    <API_KEY>qTFkykO9JTfahCOqJ0V2Wf5Cg1t8iWlZ</API_KEY>
    <SUBJECT>The subject </SUBJECT>
    <NAME>fishtank</NAME>
    <SLIDE>
        <IMAGE><URL>http://www.yoursite.com/images/1.jpg</URL></IMAGE>
        <AUDIO><URL>http://www.yoursite.com/audio/1.mp3</URL></AUDIO>
        <TEXT>Here is some text</TEXT>
        <DURATION>5</DURATION>
    </SLIDE>
</REQUEST>
```

__Response Example: Success__
```xml
<RESPONSE>
    <STATUS>Success</STATUS>
    <MMSID>35674</MMSID>
</RESPONSE>
```

__Response Example: Failure__
```xml
<RESPONSE>
    <STATUS>Failure</STATUS>
    <ERRORCODE>E111</ERRORCODE>
    <ERRORINFO>Invalid shortcode</ERRORINFO>
</RESPONSE>
```

__Postback Notifications__  
When an MMS is saved, the system will generate a Postback notification and unlock MMS for further use. If an MMS contain audio/video, Postback will be sent when the encoding of the MMS audio/video is finished, otherwise Postback notification will be sent instantly. Below is an example of Postback notification when an MMS is saved successfully:

```xml
<?xml version='1.0'?>
<POSTBACK xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
xsi:noNamespaceSchemaLocation ="http://www.skycore.com/platform/schema/postback.xsd">
    <ORIGIN>MMS_MT</ORIGIN>
    <CODE>N003</CODE>
    <MMSID>35674</MMSID>
</POSTBACK>
```

If there was an error encoding the MMS audio/video, the system will generate a notification:
```xml
<?xml version='1.0'?>
<POSTBACK xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
xsi:noNamespaceSchemaLocation ="http://www.skycore.com/platform/schema/postback.xsd">
    <ORIGIN>MMS_MT</ORIGIN>
    <CODE>E002</CODE>
    <MMSID>35674</MMSID>
    <AUDIONAME>1.mp3</AUDIONAME>
</POSTBACK>
```

__Special Considerations for saveMMS:__  
* The API SHALL reformat the content when necessary so that it can be delivered to the end users handset in the best 
possible way.
* Delivery success takes precedence over audio and video content quality and occasionally the picture quality
will be reduced to fit handset message size requirements.
* Video SHALL be reduced in quality to fit delivery limitations and if it still does not fit it will be delivered as XHTML/SMS.
* Each request MUST contain at least one slide which MAY contain text and/or image and/or video and/or sound.
* The API SHALL support up to 80 characters in the MMS subject.
* The API SHALL support up to 8 slides for each MMS submission.
* The API SHALL NOT support multiple files of the same MIME type on the same slide.
* Slides with image SHALL NOT support video but SHALL support audio.
* Slides with audio SHALL NOT support video. Slides with video SHALL only support text.
* Slides with text SHALL support up to 5000 characters in any slide.
* All slides MAY contain a duration for playback.
* Default slide duration is 5 seconds.
* Slide duration will be overwritten if the file duration exceeds the xml duration.
* URLs provided MUST contain the full path to the mime files.
* Slide Duration SHOULD NOT exceed 30 seconds and SHALL NOT exceeds 60 seconds.
* MMS subject is required. 
* MMS containing audio/video can be used only when audio/video encoding is completed.
* After submission you will not be given a successful acknowledgement of audio/video encoding when a message is submitted
* The HTTP status of audio/video encoding after it has been completed will be sent to your Postback URL.
* Supported Media: TEXT/PLAIN, GIF/JPG/PNG, MP3/WAV, 3GP, MP4, MPEG, MPG, AVI, WMV.
* There is a maximum source file size for each supported source file submitted.
* You can find out what the current maximum is by visiting your API settings.
* MMS messages are delivered in B64 encoding To estimate the final size of Base64-encoded binary data multiply the filesize by 1.37 times the original data size + 814 bytes (for headers). 
