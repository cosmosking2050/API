[Back to the Table of Contents](/1.3/README.md)

## createEmailCampaign


__Synopsis:__  
This API function creates new email campaign within the account holders account and returns a CampaignID. Campaign will be created under _campaignname_ in our system. _Campaignname_ will be sent to users in opt-in/opt-out emails. _Brandname_ will be used in 'from' field of all sent emails. _Mailingadress_ will be inserted into email footer.

__Request:__
```xml
<REQUEST>
  <ACTION>createEmailCampaign</ACTION>
    <API_KEY>API KEY</API_KEY>
    <CAMPAIGNNAME>Camapign Name</CAMPAIGNNAME>
    <BRANDNAME>Brand name</BRANDNAME>
        <MAILINGADDRESS>Mailing Address</MAILINGADDRESS>
</REQUEST>
```

```xml
<element name="REQUEST">
    <zeroOrMore>
        <element name="ACTION">
            <zeroOrMore>
                <element name="API_KEY">
                  </text>
                </element>
                <element name="CAMPAIGNNAME">
                    </text>
                </element>
                <element name="BRANDNAME">
                    <zeroOrMore>
                        <element name="MAILINGADDRESS">
                            </text>
                        </element>
                    </zeroOrMore>
                </element>
            </zeroOrMore>
        </element>
    </zeroOrMore>
</element>
```

__Request Parameters:__

    Mandatory: Action, API_KEY, CampaignName, BrandName, MailingAddress
    Optional: N/A

__Response Parameters:__

    CampaignID, CampaignName, BrandName, MailingAddress, ErrorInfo, Errorcode

__Related Errorcodes:__

    E170, E171, E172, E173    

__Request Example:__  
XML:
```xml
<REQUEST>
    <ACTION>createEmailCampaign</ACTION>
    <API_KEY>qTFkykO9JTfahCOqJ0V2Wf5Cg1t8iWlZ</API_KEY>
    <CAMPAIGNNAME>Winter Sale</CAMPAIGNNAME>
    <BRANDNAME>Codereadr</BRANDNAME>
        <MAILINGADDRESS>Skycore, LLC 
            214 Lincoln Street, Suite 360
            Allston, MA 02134</MAILINGADDRESS>
</REQUEST>
```

```xml
<element name="REQUEST">
    <zeroOrMore>
        <element name="ACTION">
            <zeroOrMore>
                <element name="API_KEY">
                  </text>
                </element>
                <element name="CAMPAIGNNAME">
                    </text>
                </element>
                <element name="BRANDNAME">
                    <zeroOrMore>
                        <element name="MAILINGADDRESS">
                            </text>
                        </element>
                    </zeroOrMore>
                </element>
            </zeroOrMore>
        </element>
    </zeroOrMore>
</element>
```

GET:

    https://secure.skycore.com/API/wxml/1.3/index.php?action=createemailcampaign&api_key=qTFkykO9JTfahCOqJ0V2Wf5Cg1t8iWlZ
    &campaignname=Winter+Sale&brandname=Codereadr
    &mailingaddress=Skycore%2C+LLC%0A214+Lincoln+Street%2C+Suite+360%0AAllston%2C+MA+02134

__Response Example: Success__
```xml
<RESPONSE>
    <STATUS>Success</STATUS>
    <CAMPAIGNID>1116</CAMPAIGNID>
    <CAMPAIGNNAME>Winter Sale</CAMPAIGNNAME>
    <BRANDNAME>Codereadr</BRANDNAME>
        <MAILINGADDRESS>Skycore, LLC 
            214 Lincoln Street, Suite 360
            Allston, MA 02134</MAILINGADDRESS>
</RESPONSE>
```

```xml
<element name="RESPONSE">
    <zeroOrMore>
        <element name="STATUS">
            </text>
        </element>
        <element name="CAMPAIGNID">
            </text>
        </element>
        <element name="CAMPAIGNNAME">
            </text>
        </element>
        <element name="BRANDNAME">
            <zeroOrMore>
                <element name="MAILINGADDRESS">
                    </text>
                </element>
            </zeroOrMore>
        </element>
    </zeroOrMore>
</element>
```
        
__Response Example: Failure__
```xml
<RESPONSE>
    <STATUS>Failure</STATUS>
    <ERRORCODE>E173</ERRORCODE>
    <ERRORINFO>mailingaddress is required</ERRORINFO>
</RESPONSE>
```

```xml
<element name="RESPONSE">
    <zeroOrMore>
        <element name="STATUS">
            </text>
        </element>
        <element name="ERRORCODE">
            </text>
        </element>
        <element name="ERRORINFO">
            </text>
        </element>
    </zeroOrMore>
</element>
```
