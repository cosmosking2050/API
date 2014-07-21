[Back to the Table of Contents](/1.3/README.md)

## addPassData


__Synopsis:__  
This API request is used to add dynamic pass data for the pass template. The fields which are set as dynamic on the Pass template are only allowed to be added. The pass data is added to the pass database and will be used to create the Passbook Pass whenever the pass generation is triggered. Based on the settings of the Pass Template the pass data need to be passed accordingly in the API request and all the other/extra data will be ignored. Additionally, Phone (or/and) Email (or/and) customDataId can be passed along with the pass data to lock down the pass data to the respective entity, that means that this pass data will used to generate a pass whenever it is delivered to that Email (via Email), Phone (via MMS). CustomPassId is your system generated Unique Id that will represent this pass data. You can optinally pass it along with pass data to be saved along with pass data and this can be used to refer this pass. In the case of Relevance, Relevant Text is considered only when Relevance lat,long values are passed in the API otherwise ignored. On success, it returns PassDataId which should be stored and kept in your database along with the data. For more info see below for Mandatory/Optional fields and Error codes.

__Request: XML__
```xml
<REQUEST>
    <ACTION>addPassData</ACTION>
    <API_KEY>apiKey</API_KEY>
    <PASSTEMPLATEID>passTemplateId</PASSTEMPLATEID>
    <PASSDATA>
        <CUSTOMPASSID>customPassId</CUSTOMPASSID>
        <THUMBNAILURL>thumbnailUrl</THUMBNAILURL>
        <BARCODEVALUE>barcodeValue</BARCODEVALUE>
        <BARCODETEXT>barcodeText</BARCODETEXT>
        <HEADERLABEL1>headerLabel1</HEADERLABEL1>
        <HEADERVALUE1>headerValue1</HEADERVALUE1>
        <PRIMARYLABEL1>primaryLabel1</PRIMARYLABEL1>
        <PRIMARYVALUE1>primaryValue1</PRIMARYVALUE1> 
        <PRIMARYLABEL2>primaryLabel2</PRIMARYLABEL2>
        <PRIMARYVALUE2>primaryValue2</PRIMARYVALUE2> 
        <SECLABEL1>secLabel1</SECLABEL1>
        <SECVALUE1>secValue1</SECVALUE1>
        <SECLABEL2>sedLabel2</SECLABEL2>
        <SECVALUE2>secValue2</SECVALUE2>
        <SECLABEL3>sedLabel3</SECLABEL3>
        <SECVALUE3>secValue3</SECVALUE3>
        <SECLABEL4>sedLabel4</SECLABEL4>
        <SECVALUE4>secValue4</SECVALUE4>
        <AUXLABEL1>auxLabel1</AUXLABEL1>
        <AUXVALUE1>auxValue1</AUXVALUE1>
        <AUXLABEL2>auxLabel2</AUXLABEL2>
        <AUXVALUE2>auxValue2</AUXVALUE2>
        <AUXLABEL3>auxLabel3</AUXLABEL3>
        <AUXVALUE3>auxValue3</AUXVALUE3>
        <AUXLABEL4>auxLabel4</AUXLABEL4>
        <AUXVALUE4>auxValue4</AUXVALUE4>
        <BACKLABEL1>backLabel1</BACKLABEL1>
        <BACKVALUE1>backValue1</BACKVALUE1>
        <BACKLABEL2>backLabel2</BACKLABEL2>
        <BACKVALUE2>backValue2</BACKVALUE2>
        <BACKLABEL3>backLabel3</BACKLABEL3>
        <BACKVALUE3>backValue3</BACKVALUE3>
        <BACKLABEL4>backLabel4</BACKLABEL4>
        <BACKVALUE4>backValue4</BACKVALUE4>
        <RELLATITUDE1>relLatitude1</RELLATITUDE1>
        <RELLONGITUDE1>relLongitude1</RELLONGITUDE1>
        <RELTEXT1>relText1</RELTEXT1>
        <RELLATITUDE2>relLatitude2</RELLATITUDE2>
        <RELLONGITUDE2>relLongitude2</RELLONGITUDE2>
        <RELTEXT2>relText2</RELTEXT2>
        <RELLATITUDE3>relLatitude3</RELLATITUDE3>
        <RELLONGITUDE3>relLongitude3</RELLONGITUDE3>
        <RELTEXT3>relText3</RELTEXT3>
        <RELLATITUDE4>relLatitude4</RELLATITUDE4>
        <RELLONGITUDE4>relLongitude4</RELLONGITUDE4>
        <RELTEXT4>relText4</RELTEXT4>
        <RELLATITUDE5>relLatitude5</RELLATITUDE5>
        <RELLONGITUDE5>relLongitude5</RELLONGITUDE5>
        <RELTEXT5>relText5</RELTEXT5>
        <RELLATITUDE6>relLatitude6</RELLATITUDE6>
        <RELLONGITUDE6>relLongitude6</RELLONGITUDE6>
        <RELTEXT6>relText6</RELTEXT6>
        <RELLATITUDE7>relLatitude7</RELLATITUDE7>
        <RELLONGITUDE7>relLongitude7</RELLONGITUDE7>
        <RELTEXT7>relText7</RELTEXT7>
        <RELLATITUDE8>relLatitude8</RELLATITUDE8>
        <RELLONGITUDE8>relLongitude8</RELLONGITUDE8>
        <RELTEXT8>relText8</RELTEXT8>
        <RELLATITUDE9>relLatitude9</RELLATITUDE9>
        <RELLONGITUDE9>relLongitude9</RELLONGITUDE9>
        <RELTEXT9>relText9</RELTEXT9>
        <RELLATITUDE10>relLatitude10</RELLATITUDE10>
        <RELLONGITUDE10>relLongitude10</RELLONGITUDE10>
        <RELTEXT10>relText10</RELTEXT10>
        <EMAIL>email</EMAIL>
        <PHONE>phone</PHONE>
        <CUSTOMID>customId</CUSTOMID>
    </PASSDATA>    
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
	<element name="PASSDATA">
	    <optional>
	        <element name="CUSTOMPASSID">
	            </text>
	        </element>
	    </optional>
	    <optional>
	        <element name="THUMBNAILURL">
	            </text>
	        </element>
	    </optional>
	    <element name="BARCODEVALUE">
	        </text>
	    </element>
	    <optional>
	        <element name="BARCODETEXT">
	            </text>
	        </element>
	    </optional>
	    <optional>
	        <element name="HEADERLABEL1">
	            </text>
	        </element>
	    </optional>
	    <optional>
	        <element name="HEADERVALUE1">
	            </text>
	        </element>
	    </optional>
	    <optional>
	        <element name="PRIMARYLABEL1">
	            </text>
	        </element>
	    </optional>
	    <optional>
	        <element name="PRIMARYVALUE1">
	            </text>
	        </element>
	    </optional>
	    <optional>
	        <element name="PRIMARYLABEL2">
	            </text>
	        </element>
	    </optional>
	    <optional>
	        <element name="PRIMARYVALUE2">
	            </text>
	        </element>
	    </optional>
	    <optional>
	        <element name="SECLABEL1">
	            </text>
	        </element>
	    </optional>
	    <optional>
	        <element name="SECVALUE1">
	            </text>
	        </element>
	    </optional>
	    <optional>
	        <element name="SECLABEL2">
	            </text>
	        </element>
	    </optional>
	    <optional>
	        <element name="SECVALUE2">
	            </text>
	        </element>
	    </optional>
	    <optional>
	        <element name="SECLABEL3">
	            </text>
	        </element>
	    </optional>
	    <optional>
	        <element name="SECVALUE3">
	            </text>
	        </element>
	    </optional>
	    <optional>
	        <element name="SECLABEL4">
	            </text>
	        </element>
	    </optional>
	    <optional>
	        <element name="SECVALUE4">
	            </text>
	        </element>
	    </optional>
	    <optional>
	        <element name="AUXLABEL1">
	            </text>
	        </element>
	    </optional>
	    <optional>
	        <element name="AUXVALUE1">
	            </text>
	        </element>
	    </optional>
	    <optional>
	        <element name="AUXLABEL2">
	            </text>
	        </element>
	    </optional>
	    <optional>
	        <element name="AUXVALUE2">
	            </text>
	        </element>
	    </optional>
	    <optional>
	        <element name="AUXLABEL3">
	            </text>
	        </element>
	    </optional>
	    <optional>
	        <element name="AUXVALUE3">
	            </text>
	        </element>
	    </optional>
	    <optional>
	        <element name="AUXLABEL4">
	            </text>
	        </element>
	    </optional>
	    <optional>
	        <element name="AUXVALUE4">
	            </text>
	        </element>
	    </optional>
	    <optional>
	        <element name="BACKLABEL1">
	            </text>
	        </element>
	    </optional>
	    <optional>
	        <element name="BACKVALUE1">
	            </text>
	        </element>
	    </optional>
	    <optional>
	        <element name="BACKLABEL2">
	            </text>
	        </element>
	    </optional>
	    <optional>
	        <element name="BACKVALUE2">
	            </text>
	        </element>
	    </optional>
	    <optional>
	        <element name="BACKLABEL3">
	            </text>
	        </element>
	    </optional>
	    <optional>
	        <element name="BACKVALUE3">
	            </text>
	        </element>
	    </optional>
	    <optional>
	        <element name="BACKLABEL4">
	            </text>
	        </element>
	    </optional>
	    <optional>
	        <element name="BACKVALUE4">
	            </text>
	        </element>
	    </optional>
	    <optional>
	        <element name="RELLATITUDE1">
	            </text>
	        </element>
	    </optional>
	    <optional>
	        <element name="RELLONGITUDE1">
	            </text>
	        </element>
	    </optional>
	    <optional>
	        <element name="RELTEXT1">
	            </text>
	        </element>
	    </optional>
	    <optional>
	        <element name="RELLATITUDE2">
	            </text>
	        </element>
	    </optional>
	    <optional>
	        <element name="RELLONGITUDE2">
	            </text>
	        </element>
	    </optional>
	    <optional>
	        <element name="RELTEXT2">
	            </text>
	        </element>
	    </optional>
	    <optional>
	        <element name="RELLATITUDE3">
	            </text>
	        </element>
	    </optional>
	    <optional>
	        <element name="RELLONGITUDE3">
	            </text>
	        </element>
	    </optional>
	    <optional>
	        <element name="RELTEXT3">
	            </text>
	        </element>
	    </optional>
	    <optional>
	        <element name="RELLATITUDE4">
	            </text>
	        </element>
	    </optional>
	    <optional>
	        <element name="RELLONGITUDE4">
	            </text>
	        </element>
	    </optional>
	    <optional>
	        <element name="RELTEXT4">
	            </text>
	        </element>
	    </optional>
	    <optional>
	        <element name="RELLATITUDE5">
	            </text>
	        </element>
	    </optional>
	    <optional>
	        <element name="RELLONGITUDE5">
	            </text>
	        </element>
	    </optional>
	    <optional>
	        <element name="RELTEXT5">
	            </text>
	        </element>
	    </optional>
	    <optional>
	        <element name="RELLATITUDE6">
	            </text>
	        </element>
	    </optional>
	    <optional>
	        <element name="RELLONGITUDE6">
	            </text>
	        </element>
	    </optional>
	    <optional>
	        <element name="RELTEXT6">
	            </text>
	        </element>
	    </optional>
	    <optional>
	        <element name="RELLATITUDE7">
	            </text>
	        </element>
	    </optional>
	    <optional>
	        <element name="RELLONGITUDE7">
	            </text>
	        </element>
	    </optional>
	    <optional>
	        <element name="RELTEXT7">
	            </text>
	        </element>
	    </optional>
	    <optional>
	        <element name="RELLATITUDE8">
	            </text>
	        </element>
	    </optional>
	    <optional>
	        <element name="RELLONGITUDE8">
	            </text>
	        </element>
	    </optional>
	    <optional>
	        <element name="RELTEXT8">
	            </text>
	        </element>
	    </optional>
	    <optional>
	        <element name="RELLATITUDE9">
	            </text>
	        </element>
	    </optional>
	    <optional>
	        <element name="RELLONGITUDE9">
	            </text>
	        </element>
	    </optional>
	    <optional>
	        <element name="RELTEXT9">
	            </text>
	        </element>
	    </optional>
	    <optional>
	        <element name="RELLATITUDE10">
	            </text>
	        </element>
	    </optional>
	    <optional>
	        <element name="RELLONGITUDE10">
	            </text>
	        </element>
	    </optional>
	    <optional>
	        <element name="RELTEXT10">
	            </text>
	        </element>
	    </optional>
	    <optional>
	        <element name="EMAIL">
	            </text>
	        </element>
	    </optional>
	    <optional>
	        <element name="PHONE">
	            </text>
	        </element>
	    </optional>
	    <optional>
	        <element name="CUSTOMID">
	        	</text>
	    	</element>
		</optional>
    </element>
</element>
```

__Request: GET__

    API_URL?action=addpassdata&api_key=apiKey&passtemplateid=passTemplateId
    &pd_custompassid=customPassId&pd_thumbnailurl=thumbnailUrl
    &pd_barcodevalue=barcodeValue&pd_barcodetext=barcodeText
    &pd_headerlabel1=headerLabel1&pd_headervalue1=headerValue1
    &pd_primarylabel1=primaryLabel1&pd_primaryvalue1=primaryValue1
    &pd_primarylabel2=primaryLabel2&pd_primaryvalue2=primaryValue2
    &pd_seclabel1=secLabel1&pd_secvalue1=secValue1&pd_seclabel2=secLabel2
    &pd_secvalue2=secValue2&pd_seclabel3=secLabel3&pd_secvalue3=secValue3
    &pd_seclabel4=secLabel4&pd_secvalue4=secValue4&pd_auxlabel1=auxLabel1
    &pd_auxvalue1=auxValue1&pd_auxlabel2=auxLabel2&pd_auxvalue2=auxValue2
    &pd_auxlabel3=auxLabel3&pd_auxvalue3=auxValue3&pd_auxlabel4=auxLabel4
    &pd_auxvalue4=auxValue4&pd_backlabel1=backLabel1&pd_backvalue1=backValue1
    &pd_backlabel2=backLabel2&pd_backvalue2=backValue2&pd_backlabel3=backLabel3
    &pd_backvalue3=backValue3&pd_backlabel4=backLabel4&pd_backvalue4=backValue4
    &pd_rellatitude1=relLatitude1&pd_rellongitude1=relLongitude1&pd_reltext1=relText1
    &pd_rellatitude2=relLatitude2&pd_rellongitude2=relLongitude2&pd_reltext2=relText2
    &pd_rellatitude3=relLatitude3&pd_rellongitude3=relLongitude3&pd_reltext3=relText3
    &pd_rellatitude4=relLatitude4&pd_rellongitude4=relLongitude4&pd_reltext4=relText4
    &pd_rellatitude5=relLatitude5&pd_rellongitude5=relLongitude5&pd_reltext5=relText5
    &pd_rellatitude6=relLatitude6&pd_rellongitude6=relLongitude6&pd_reltext6=relText6
    &pd_rellatitude7=relLatitude7&pd_rellongitude7=relLongitude7&pd_reltext7=relText7
    &pd_rellatitude8=relLatitude8&pd_rellongitude8=relLongitude8&pd_reltext8=relText8
    &pd_rellatitude9=relLatitude9&pd_rellongitude9=relLongitude9&pd_reltext9=relText9
    &pd_rellatitude10=relLatitude10&pd_rellongitude10=relLongitude10&pd_reltext10=relText10
    &pd_email=email&pd_phone=phone&pd_customid=customId

__Request Parameters:__

    Mandatory: action, apiKey, passTemplateId,
    barcodeValue (if "Barcode=Allowed" && "BarcodeType=Dynamic" && "BarcodeValueSource=Dynamic Value" for Pass Template otherwise IGNORED)
    Optional: customPassId, thumbnailUrl,
    barcodeText (if "Barcode = Allowed" && "Barcode Alternate Text = Dynamic Text" for Pass Template otherwise IGNORED), 
    headerLabel1, headerValue1, 
    primaryLabel1, primaryValue1, 
    primaryLabel2, primaryValue2 - if "Pass Template Type = Boarding Pass" otherwise IGNORED, 
    secLabel1, secValue1, secLabel2, secValue2, secLabel3, secValue3, secLabel4, secValue4, 
    auxLabel1, auxValue1, auxLabel2, auxValue2, auxLabel3, auxValue3, auxLabel4, auxValue4, 
    backLabel1, backValue1, backLabel2, backValue2, backLabel3, backValue3, backLabel4, backValue4,
    relLatitude1, relLongitude1, relText1,
    relLatitude2, relLongitude2, relText2,
    relLatitude3, relLongitude3, relText3,
    relLatitude4, relLongitude4, relText4,
    relLatitude5, relLongitude5, relText5,
    relLatitude6, relLongitude6, relText6,
    relLatitude7, relLongitude7, relText7,
    relLatitude8, relLongitude8, relText8,
    relLatitude9, relLongitude9, relText9,
    relLatitude10, relLongitude10, relText10,
    email, phone, customId

__Response Parameters:__

    status, passDataID, passTemplateId, Errorcode, Errorinfo

__Related Errorcodes:__

    E801, E802, E803, E804, E805, E806, E829, E833, E840, E841, E842, E843, E844, E845, E846, E847, E848, E849, E850,
    E851, E852, E853, E854, E855, E856, E857, E858, E859, E860, E861, E862, E863, E864, E865, E866, E867, E868, E869,
    E870, E871, E872, E873, E874, E875, E876, E877, E878, E879, E880, E881, E882, E883, E884, E885, E886, E887, E888,
    E889, E890, E891, E892, E893, E894, E895, E896, E897, E898, E899

__Request Example:__
```xml
<REQUEST>
    <ACTION>addPassData</ACTION>
    <API_KEY>qTFkykO9JTfahCOqJ0V2Wf5Cg1t8iWlZ</API_KEY>
    <PASSTEMPLATEID>100</PASSTEMPLATEID>
    <PASSDATA>
        <CUSTOMPASSID>GM-12345-M</CUSTOMPASSID>
        <THUMBNAILURL>http://andreas.com/pixs/steve-jobs.png</THUMBNAILURL>
        <BARCODEVALUE>1234578961A</BARCODEVALUE>
        <BARCODETEXT>PASS-123-457</BARCODETEXT>
        <HEADERLABEL1>SEAT</HEADERLABEL1>
        <HEADERVALUE1>1C</HEADERVALUE1>
        <PRIMARYLABEL1>Name</PRIMARYLABEL1>
        <PRIMARYVALUE1>Vikram Muthyala</PRIMARYVALUE1> 
        <SECLABEL1>Date</SECLABEL1>
        <SECVALUE1>4th July, 2013</SECVALUE1>
        <SECLABEL2>Auditorium</SECLABEL2>
        <SECVALUE2>Gold Room</SECVALUE2>
        <AUXLABEL1>Address</AUXLABEL1>
        <AUXVALUE1>Hynes Convention Centre, Boston MA</AUXVALUE1>
        <BACKLABEL1>Terms and Conditions</BACKLABEL1>
        <BACKVALUE1>Valid for 1 person only. Expires July 6th, 2013. Valid ID required if requested.</BACKVALUE1>
        <BACKLABEL2>Snacks and Drinks</BACKLABEL2>
        <BACKVALUE2>Free Drinks and Snacks are available in the main lobby.</BACKVALUE2>
        <BACKLABEL3>Take a Survey to win free ticket</BACKLABEL3>
        <BACKVALUE3>https://www.survey.com/event/12748493fgh/</BACKVALUE3>
        <RELLATITUDE1>42.347888</RELLATITUDE1>
        <RELLONGITUDE1>-71.087903</RELLONGITUDE1>
        <RELTEXT1>Event at HYNES CONVENTION CENTRE</RELTEXT1>
        <EMAIL>vik.muth@mail.com</EMAIL>
        <PHONE>16501234123</PHONE>
        <CUSTOMID>AC34573</CUSTOMID>
    </PASSDATA>    
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
	<element name="PASSDATA">
		<optional>
		    <element name="CUSTOMPASSID">
		        </text>
	        </element>
        </optional>
        <optional>
            <element name="THUMBNAILURL">
                </text>
            </element>
        </optional>
        <element name="BARCODEVALUE">
            </text>
        </element>
        <optional>
            <element name="BARCODETEXT">
                </text>
            </element>
        </optional>
        <optional>
            <element name="HEADERLABEL1">
                </text>
            </element>
        </optional>
        <optional>
            <element name="HEADERVALUE1">
                </text>
            </element>
    	</optional>
        <optional>
            <element name="PRIMARYLABEL1">
                </text>
            </element>
        </optional>
        <optional>
            <element name="PRIMARYVALUE1">
                </text>
            </element>
        </optional>
        <optional>
            <element name="SECLABEL1">
                </text>
            </element>
        </optional>
        <optional>
            <element name="SECVALUE1">
                </text>
            </element>
        </optional>
        <optional>
            <element name="SECLABEL2">
                </text>
            </element>
        </optional>
        <optional>
            <element name="SECVALUE2">
                </text>
            </element>
        </optional>
        <optional>
            <element name="AUXLABEL1">
                </text>
            </element>
        </optional>
        <optional>
            <element name="AUXVALUE1">
                </text>
            </element>
        </optional>
        <optional>
            <element name="BACKLABEL1">
                </text>
            </element>
        </optional>
        <optional>
            <element name="BACKVALUE1">
                </text>
            </element>
        </optional>
        <optional>
            <element name="BACKLABEL2">
                </text>
            </element>
        </optional>
        <optional>
            <element name="BACKVALUE2">
                </text>
            </element>
        </optional>
        <optional>
            <element name="BACKLABEL3">
                </text>
            </element>
        </optional>
        <optional>
            <element name="BACKVALUE3">
                </text>
            </element>
        </optional>
        <optional>
            <element name="RELLATITUDE1">
                </text>
            </element>
        </optional>
        <optional>
            <element name="RELLONGITUDE1">
                </text>
            </element>
        </optional>
        <optional>
            <element name="RELTEXT1">
                </text>
            </element>
        </optional>
        <optional>
            <element name="EMAIL">
                </text>
            </element>
        </optional>
        <optional>
            <element name="PHONE">
                </text>
            </element>
        </optional>
        <optional>
            <element name="CUSTOMID">
                </text>
            </element>
        </optional>
    </element>
</element>
```

__Response Example: Success__
```xml
<RESPONSE>
    <STATUS>Success</STATUS>
    <PASSTEMPLATEID>100</PASSTEMPLATEID>
    <PASSDATAID>63202e8e947626dae377abh6hd56ehs64aeeeb0</PASSDATAID>
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
	<element name="PASSDATAID">
		</text>
	</element>
</element>
```

__Response Example: Failure__
```xml
<RESPONSE>
    <STATUS>Failure</STATUS>
    <ERRORCODE>E806</ERRORCODE>
    <ERRORINFO>PassDataId was not created. Internal error occurred.</ERRORINFO>
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
d
