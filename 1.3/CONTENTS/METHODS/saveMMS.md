[Back to the Table of Contents](/1.3/README.md)

## saveMMS

__Synopsis:__  
This API stores an MMS from XML. The MMS may contain slides embedded with video, audio, images and text. Once the MMS is saved, it can be utilized by other functions through the MMSID returned. The legacy format is still supported at this time, but it is recommended that developers update to the most recent format at their earliest convenience.

__Request:__
```xml
<REQUEST>
    <ACTION>saveMMS</ACTION>
    <API_KEY>apiKey</API_KEY>
    <SUBJECT>Subject </SUBJECT>
    <NAME>Name to save it as</NAME>
    <SLIDE>
        <IMAGE>
            <URL>URL</URL> 
        </IMAGE>
        <TEXT>Plain Text</TEXT>
        <DURATION>Duration in seconds</DURATION>
    <SLIDE>
    </SLIDE>
        <AUDIO>
            <URL>URL</URL>
        </AUDIO>
        <TEXT>Plain Text</TEXT>
        <DURATION>Duration in seconds</DURATION>
    <SLIDE>
    </SLIDE>
        <VIDEO>
            <URL>URL</URL>
        </VIDEO>
        <TEXT>Plain Text</TEXT>
        <DURATION>Duration in seconds</DURATION>
    <SLIDE>
    </SLIDE>
        <VCARD>
            <URL>URL</URL>
        </VCARD>
        <TEXT>Plain Text</TEXT>
        <DURATION>Duration in seconds</DURATION>
    <SLIDE>
    </SLIDE>
        <ICAL>
            <URL>URL</URL>
        </ICAL>
        <TEXT>Plain Text</TEXT>
        <DURATION>Duration in seconds</DURATION>
        <SLIDE>
    </SLIDE>
        <PDF>
            <URL>URL</URL>
        </PDF>
        <TEXT>Plain Text</TEXT>
        <DURATION>Duration in seconds</DURATION>
    <SLIDE>
    </SLIDE>
        <PASSBOOK>
            <URL>URL</URL>
        </PASSBOOK>    
        <TEXT>Plain Text</TEXT>
        <DURATION>Duration in seconds</DURATION>
    </SLIDE>
    <SLIDE>
        ...
    </SLIDE>
</REQUEST>
```

__Request Parameters:__

    Mandatory: action, api_key, subject, name, slide
    Optional: image, audio, video, url, text, duration, vcard, ical, pdf, passbook

__Response Parameters:__

    status, mmsId, errorCode, errorInfo

__Related Error Codes:__

    E223, E224, E225, E226, E227, E228, E229, E230, E301, E302, E303, E304, E331, E332, E333, E334, E341, E351, E352, E353, E355, E356, E357, E358

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
    <SLIDE>
        <TEXT>This is my contact</TEXT>
        <VCARD><URL>http://www.yoursite.com/vcard/2.vcf</URL></VCARD>
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
<POSTBACK>
    <ORIGIN>MMS_MT</ORIGIN>
    <CODE>N003</CODE>
    <MMSID>35674</MMSID>
</POSTBACK>
```

If there was an error encoding the MMS audio/video, the system will generate a notification:
```xml
<?xml version='1.0'?>
<POSTBACK>
    <ORIGIN>MMS_MT</ORIGIN>
    <CODE>E002</CODE>
    <MMSID>35674</MMSID>
    <AUDIONAME>http://www.yoursite.com/audio/1.mp3</AUDIONAME>
</POSTBACK>
```

__Merge Tags:__

You can save an MMS Template with merge tags and those tags will be replaced during delivery of the MMS as long as you pass the variables in the SendSavedMMS request. 

For example:
```
<REQUEST>
    <ACTION>saveMMS</ACTION>
    <API_KEY>*********************************************</API_KEY>
        <SUBJECT>Text with the dynamic variables</SUBJECT>
        <NAME>MMS with DynVars</NAME>
            <SLIDE>
                <IMAGE>
                    <URL>http://www.destination360.com/caribbean/bahamas/images/s/bahamas-boat-rental.jpg</URL>
                </IMAGE>
                <TEXT >
                    Hello {$firstname|Sir}, your gender is {$gender|unknown}.
                </TEXT>
            </SLIDE>
    </REQUEST>
```

Then inside sendsavedMMS we do call this:

```

<REQUEST>
    <ACTION>sendsavedMMS</ACTION>
    <API_KEY>*********************************************</API_KEY>
    <MMSID>43615</MMSID>
    <FROM>66666</FROM>
    <TO>16502426058</TO>
    <CAMPAIGNREF>1807</CAMPAIGNREF>
    <DATA>
        <FIRSTNAME>Bill</FIRSTNAME>
        <GENDER>Male</GENDER>
    </DATA>
</REQUEST>
```
and within the delivered MMS we will have this:
"Hello Bill, your gender is male."

__Special Considerations for saveMMS:__  
* The API SHALL reformat the content when necessary so that it can be delivered to the end users handset in the best 
possible way.
* Delivery success takes precedence over audio and video content quality and occasionally the picture quality
will be reduced to fit handset message size requirements.
* Video SHALL be reduced in quality to fit delivery limitations and if it still does not fit it will be delivered as XHTML/SMS.
* Each request MUST contain at least one slide which MAY contain text and/or image and/or video and/or audio and/or objects (vcard/ical/pdf/passbook).
* The API SHALL support up to 80 characters in the MMS subject.
* The API SHALL support up to 8 slides for each MMS submission.
* The API SHALL NOT support multiple files of the same MIME type on the same slide.
* Slides with image SHALL NOT support video but SHALL support audio.
* Slides with audio SHALL NOT support video. Slides with video SHALL only support text.
* Slides with text SHALL support up to 5000 characters in any slide.
* Slide with vcard/ical/pdf/passbook object SHALL NOT support media type audio/video/image and vice-versa.
* All slides MAY contain a duration for playback.
* Default slide duration is 10 seconds.
* Slide duration will be overwritten with the audio/video file duration after encoding is completed.
* URLs provided MUST contain the full path to the mime files.
* Slide Duration SHOULD NOT exceed 30 seconds.
* MMS subject is required. 
* MMS containing audio/video can be used only when audio/video encoding is completed.
* After submission you will not be given a successful acknowledgement of audio/video encoding when a message is submitted
* The HTTP status of audio/video encoding after it has been completed will be sent to your Postback URL.
* Supported Media: TEXT/PLAIN, GIF/JPG/PNG, MP3/WAV, 3GP, MP4, MPEG, MPG, AVI, WMV.
* There is a maximum source file size for each supported source file submitted.
* You can find out what the current maximum is by visiting your API settings.
* MMS messages are delivered in B64 encoding To estimate the final size of Base64-encoded binary data multiply the filesize by 1.37 times the original data size + 814 bytes (for headers). 
