[Back to the Table of Contents](/1.3/README.md)

## getPassTemplate

__Synopsis:__  
This API function returns the pass template information when given passTemplateId or mmsId or emailId.

__Request: XML__
```xml
<REQUEST>
    <ACTION>getPassTemplate</ACTION>
    <API_KEY>apiKey</API_KEY>
    <PASSTEMPLATEID>passTemplateId</PASSTEMPLATEID>
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
	<element name="PASSTEMPLATEID">
		</text>
	</element>
</element>
```

```xml
<REQUEST>
    <ACTION>getPassTemplate</ACTION>
    <API_KEY>apiKey</API_KEY>
    <MMSID>mmsId</MMSID>
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
	<element name="MMSID">
		</text>
	</element>
</element>
```

```xml
<REQUEST>
    <ACTION>getPassTemplate</ACTION>
    <API_KEY>apiKey</API_KEY>
    <EMAILID>emailId</EMAILID>
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
	<element name="EMAILID">
		</text>
	</element>
</element>
```

__Request: GET__
<pre>API_URL?action=getpasstemplate&amp;api_key=apiKey&amp;passtemplateid=passTemplateId</pre>
<pre>API_URL?action=getpasstemplate&amp;api_key=apiKey&amp;emailid=emailId</pre>
<pre>API_URL?action=getpasstemplate&amp;api_key=apiKey&amp;mmsid=mmsId</pre>

__Request Parameters:__

    Mandatory: action, apikey, mmsid, emailid, passtemplateid
    Optional: N/A

__Response Parameters:__

    status, Errorcode, Errorinfo, passTemplateId, passTemplate

__Related Errorcodes:__

    E174, E402, E802, E822, E823, E828, E827

__Request Example:__
```xml
<REQUEST>
    <ACTION>getPassTemplateIds</ACTION>
    <API_KEY>qTFkykO9JTfahCOqJ0V2Wf5Cg1t8iWlZ</API_KEY>
    <PASSTEMPLATEID>234</PASSTEMPLATEID>
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
	<element name="PASSTEMPLATEID">
		</text>
	</element>
</element>
```

__Response Example: Success__
```xml
<RESPONSE>
    <STATUS>Success</STATUS>
    <PASSTEMPLATEID>1233</PASSTEMPLATEID>
    <PASSTEMPLATE>
        <PASSNAME>PizzaCoupon-X12</PASSNAME>
        <PASSTYPE>Coupon</PASSTYPE>
        <ORGANIZATION>Pizza Den</ORGANIZATION>
        <DESCRIPTION>$10 off $35 purchase</DESCRIPTION>
        <BARCODEVALUE>XXXX-XXXX</BARCODEVALUE>
        <BARCODETEXT>XXXX-XXXX</BARCODETEXT>
        <HEADERFIELDS>1</HEADERFIELDS>
        <HEADERLABEL1></HEADERLABEL1>
        <HEADERVALUE1></HEADERVALUE1>
        <PRIMARYFIELDS>1</PRIMARYFIELDS>
        <PRIMARYLABEL1>$10 off $35</PRIMARYLABEL1>
        <PRIMARYVALUE1>(Conditions apply.)</PRIMARYVALUE1> 
        <SECFIELDS>1</SECFIELDS>
        <SECLABEL1>Expires</SECLABEL1>
        <SECVALUE1>July 31, 2013</SECVALUE1>
        <AUXFIELDS>1</AUXFIELDS>
        <AUXLABEL1>Terms</AUXLABEL1>
        <AUXVALUE1>Excludes TX,FL,RI,VT,UT,WA,WI</AUXVALUE1>
        <BACKFIELDS>1</BACKFIELDS>
        <BACKLABEL1>Terms and Conditions</BACKLABEL1>
        <BACKVALUE1>1 coupon valid for one family.</BACKVALUE1>
    </PASSTEMPLATE>
</RESPONSE>
```

```xml
<element name="RESPONSE">
	<element name="STATUS">
		</text>
	</element>
	<element name="PASSTEMPLATEID">
		</text>
	</element>
	<element name="PASSTEMPLATE">
	    <element name="PASSNAME">
            </text>
        </element>
        <element name="PASSTYPE">
            </text>
        </element>
        <element name="ORGANIZATION">
            </text>
        </element>
        <element name="DESCRIPTION">
            </text>
        </element>
        <element name="BARCODEVALUE">
            </text>
        </element>
        <element name="BARCODETEXT">
            </text>
        </element>
        <element name="HEADERFIELDS">
            </text>
        </element>
        <element name="HEADERLABEL1">
            </text>
        </element>
        <element name="HEADERVALUE1">
            </text>
        </element>
        <element name="PRIMARYFIELDS">
            </text>
        </element>
        <element name="PRIMARYLABEL1">
            </text>
        </element>
        <element name="PRIMARYVALUE1">
            </text>
        </element>
        <element name="SECFIELDS">
            </text>
        </element>
        <element name="SECLABEL1">
            </text>
        </element>
        <element name="SECVALUE1">
            </text>
        </element>
        <element name="AUXFIELDS">
            </text>
        </element>
        <element name="AUXLABEL1">
            </text>
        </element>
        <element name="AUXVALUE1">
            </text>
        </element>
        <element name="BACKFIELDS">
            </text>
        </element>
        <element name="BACKLABEL1">
            </text>
        </element>
        <element name="BACKVALUE1">
            </text>
        </element>
    </element>
</element>
```

__Response Example: Failure__
```xml
<RESPONSE>
    <STATUS>Failure</STATUS>
    <ERRORCODE>E802</ERRORCODE>
    <ERRORINFO>Invalid 'PassTemplateID'. Pass template is either deleted or do not belong to this user</ERRORINFO>
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
	<element name="ERRORINFO">
		</text>
	</element>
</element>
```

