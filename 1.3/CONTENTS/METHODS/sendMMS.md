[Back to the Table of Contents](/1.3/README.md)

## sendMMS

__Synopsis:__  
Sends an MMS defined in the XML containing slides of embedded with video, audio, images and/or text to a single or list of mobile numbers in international number format. SendMMS is a minor extension of the saveMMS function. This API function is only available on Dedicated Shortcodes.

Prototype:
```xml
<REQUEST>
    <ACTION>sendMMS</ACTION>
    <API_KEY>API KEY</API_KEY>
    <FROM>shortcode</FROM>
    <SPID>SPID</SPID>
    <TO>Receivers number</TO>
    <CAMPAIGNREF>CampaignID</CAMPAIGNREF>
    <SUBJECT>MMS Subject</SUBJECT>
    <NAME>Name in MMBox</NAME>
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
</REQUEST>
```

```xml
<element name="REQUEST">
	<element name="ACTION">
	    </text>
	</element>
    <element name="API_KEY">
        </text>
    </element>
    <element name="FROM">
        </text>
    </element>
    <optional>
        <element name="SPID">
            </text>
        </element>
    </optional>
    <element name="TO">
        </text>
    </element>
    <optional>
        <element name="CAMPAIGNREF">
	        </text>
        </element>
    </optional>
    <optional>
        <element name="SUBJECT">
	        </text>
        </element>
    </optional>
    <element name="NAME">
    	<oneOrMore>
            <element name="SLIDE">
                <optional>
                    <attribute name="duration">
                        </text>
                    </attribute>
                </optional>
                <optional>
    	            <element name="IMAGE">
        	            <optional>
            	            <element name="URL">
            	                </text>
            	            </element>
            	        </optional>
                    </element>
                </optional>
                <optional>
    	            <element name="AUDIO">
        	            <optional>
            	            <element name="URL">
            	                </text>
            	            </element>
            	        </optional>
                    </element>
                </optional>
                <optional>
    	            <element name="TEXT">
    	                </text>
                    </element>
                </optional>
            </element>
    	</oneOrMore>
    </element>
</element>
```

__Request Parameters:__

    Mandatory: Action, api_key, To, From, Name, Content, Slide
    Optional: Subject, SPID, Image, Audio, Video, URL, Text, Duration, CampaignRef

__Response Parameters:__

    Status, To, TrackingID, Errorcode, Errorinfo, MMSID

__Related Errorcodes:__

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

```xml
<element name="REQUEST">
    <element name="ACTION">
        </text>
    </element>
    <element name="API_KEY">
        </text>
    </element>
    <element name="TO">
        </text>
    </element>
    <element name="FROM">
        </text>
    </element>
    <optional>
        <element name="SPID">
            </text>
        </element>
    </optional>
    <optional>
        <element name="SUBJECT">
            </text>
        </element>
    </optional>
    <optional>
        <element name="CAMPAIGNREF">
            </text>
        </element>
    </optional>
    <element name="NAME">
        <oneOrMore>
            <element name="SLIDE">
                <optional>
                    <attribute name="duration">
                        </text>
                    </attribute>
                </optional>
                <optional>
                    <element name="IMAGE">
                        <optional>
                            <element name="URL">
                                </text>
                            </element>
                        </optional>
                    </element>
                </optional>
                <optional>
                    <element name="AUDIO">
                        <optional>
                            <element name="URL">
                                </text>
                            </element>
                        </optional>
                    </element>
                </optional>
                <optional>
                    <element name="TEXT">
                        </text>
                    </element>
                </optional>
            </element>
        </oneOrMore>
    </element>
</element>
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

```xml
<element name="RESPONSE">
	<element name="STATUS">
		</text>
	</element>
	<element name="TO">
		</text>
	</element>
	<element name="MMSID">
	    </text>
	</element>
	<element name="TRACKINGID">
		</text>
	</element>
</element>
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

```xml
<element name="RESPONSE">
	<element name="STATUS">
		</text>
	</element>
	<element name="ERRORCODE">
		</text>
	</element>
	<element name="TO">
		</text>
	</element>
	<element name="ERRORINFO">
		</text>
	</element>
</element>
```
