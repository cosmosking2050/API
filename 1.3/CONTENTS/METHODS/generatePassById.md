[Back to the Table of Contents](/1.3/README.md)&nbsp;&nbsp;|&nbsp;&nbsp;[Back to API Methods](API_METHODS.md)
## generatePassById
__Synopsis:__  
This API function triggers the passbook pass generation for the given 'passDataID'. 'passDataID' is generated whenever pass data is added to the pass database using the addPassData () API request. On success, the API returns important values such as 'passDataId', 'serialNumber', 'customPassId', 'passLink' and 'downloadUrl'. All these values need to be stored along with passData on your side which will come in use for making pass updates in the future. More explanation about these values are given below:  
__serialNumber__ - This is the serial number generated for the pass which identifies this pass uniquely.  
__customPassId__ - This is the Identifier from your system to identify this pass or pass data uniquely. This value will be empty of it was never passed in addPassData() API request i.e., while generate passDataId.  
__passLink__ - This is the pass installation link which allow users to install or download pass to their phones based on User-Agent detection.  
__downloadUrl__ - This URL can be used to download PKPass directly to your server.

For more info see below for Mandatory/Optional fields and Error codes.

__Request:__
```xml
<REQUEST>
    <ACTION>generatePassById</ACTION>
    <API_KEY>apiKey</API_KEY>
    <PASSDATAID>passDataID</PASSDATAID>
</REQUEST>
```

__Request Parameters:__
<pre>
<strong>Mandatory:</strong>
action, apiKey, passDataId
<strong>Optional:</strong>
N/A
</pre>

__Response Parameters:__  
status, Errorcode, Errorinfo, passDownloadLink

__Related Errorcodes:__  
E807, E808, E830, E831
    
__Request Example:__
```xml
<REQUEST>
    <ACTION>generatePassById</ACTION>
    <API_KEY>qTFkykO9JTfahCOqJ0V2Wf5Cg1t8iWlZ</API_KEY>
    <PASSDATAID>63202e8e947626dae377ab2463ca31dhwtdjdien</PASSDATAID>
</REQUEST>
```

__Response Example: Success__
```xml
<RESPONSE>
    <STATUS>Success</STATUS>
    <PASSDATAID>63202e8e947626dae377ab2463ca31dhwtdjdien</PASSDATAID>
    <SERIALNUMBER>KJSD3432-232232-2323N32</SERIALNUMBER>
    <CUSTOMPASSID>CONT-ID-SKU:112324</CUSTOMPASSID>
    <PASSLINK>https://d2c.skycore.com/passes/downloadpass.php?pass=4jfjhsus</PASSLINK>
    <DOWNLOADURL>https://d2c.skycore.com/passes/downloadpass.php?pass=4jfjhsus&download=1</DOWNLOADURL>
</RESPONSE>
```

__Response Example: Failure__
```xml
<RESPONSE>
    <STATUS>Failure</STATUS>
    <ERRORCODE>E830</ERRORCODE>
    <ERRORINFO>Passbook Pass was not generated. Internal error occured.</ERRORINFO>
</RESPONSE>
```
