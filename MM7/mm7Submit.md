[Back to the Table of Contents](/MM7/)

## MM7_Submit (Submit MMS MT)

To send a multimedia message, you send an MT message as a submit request to Skycore and supply the multimedia message as the payload. 
When Skycore accepts your MT message, we respond to you with a success status using "SubmitRsp" response. 
This indicates that your message was accepted for delivery. 
It does not, however, indicate that your message was delivered to the device.
If the MT message was received in error, we respond to you with a failure status using SOAP fault "RSErrorRsp" response.

__Using the mobile operator ID in an MM7 request__

You can supply the mobile operator details as an ID in the request header of an MM7 "SubmitReq" request. 
If you do not supply the mobile operator, Skycore would look it up (this may be a separately charged fee, depending on your contract). 
The same mobile operator ID is returned in the HTTP header of delivery reports and MO requests. 
For the best throughput performance, you should include the mobile operator ID in each request, otherwise an operator lookup is needed before we can forward the message to the mobile operator.

| Header Name | Description | Mandatory |
| -------------- | ------------------- | -------- |
| X-Skycore-Carrier-Id | Skycore Mobile Operator ID.<br/>Examples: AT&T=0001470, Verizon=0001890.<br/>[See all Skycore Operator IDs] (/MM7/skycoreOperatorIDs.md).  | No |

<h3>SubmitReq</h3>
__Supported MM7 SOAP envelope request elements__

| Element | Description | Mandatory
| ------------- | ------------------------ | --------- |
| TransactionID | The identification of the MM7 SubmitReq/SubmitRsp pair. It is located in the SOAP header. You supply this in the MM7 SubmitReq and Skycore returns it in the corresponding SubmitRsp. | Yes |
| SubmitReq | Identifies the message as an MMS MT submit. This is the message type for an MT request. | Yes |
| MM7Version | Identifies the MM7 Version.<br/>[See all supported MM7 Versions] (/MM7/supportedMM7Versions.md) | Yes |
| VASPID | Skycore provides an API key after your account is provisioned which is your VASPID. | Yes |
| VASID | Your account manager will provide you with a VASID for each shortcode. It is mandatory for accounts using shared shortcodes, otherwise optional. | No |
| SenderAddress | This is your shortcode. Should be provisioned and configured to your account and service. | Yes | 
| Recipients | The mobile phone number of the end user. This must be a valid mobile number in international format without a leading + symbol; for example: 12515550123 (US) and 447700900750 (UK). Multiple numbers are NOT supported. | Yes |
| Subject | Title of the whole multimedia message. Recommended size is 80 characters. | No |
| Content | Content of the multimedia message. href:cid attribute links to attachment. | Yes |
| allowAdaptations | Indicates if you wish to allow the mobile operator to re-encode (transcode) the content to make the content more suitable to the target handset. Each mobile operator may choose to obey or ignore this field; for example, some mobile operators assume or require by default the option to transcode content. AllowAdaptations is an attribute of Content element. The value must be Boolean (either true or false). The default is true. | No |
[See Unsupported request elements] (/MM7/unsupportedMM7Elements.md)

__Example__

```xml
<?xml version="1.0" encoding="UTF-8"?>
<soap-env:Envelope xmlns:soap-env="http://schemas.xmlsoap.org/soap/envelope/">
    <soap-env:Header>
        <TransactionID xmlns="http://www.3gpp.org/ftp/Specs/archive/23_series/23.140/schema/REL-6-MM7-1-4" soap-env:mustUnderstand="1">1000001</TransactionID>
    </soap-env:Header>
    <soap-env:Body>
        <SubmitReq xmlns="http://www.3gpp.org/ftp/Specs/archive/23_series/23.140/schema/REL-6-MM7-1-4">
            <MM7Version>6.8.0</MM7Version>
            <SenderIdentification>
                <VASPID>skfdjslkjfdslkfj434das</VASPID>
                <VASID>126273</VASID>
                <SenderAddress>
                    <ShortCode>111122</ShortCode>
                </SenderAddress>
            </SenderIdentification>
            <Recipients>
                <To>
                    <Number>16172383232</Number>
                </To>
            </Recipients>
            <Subject>My first MM7 Message</Subject>
            <Content allowAdaptations="false" href="cid:generic" />
        </SubmitReq>
    </soap-env:Body>
</soap-env:Envelope>
```

<h3>SubmitRsp</h3>
__Supported MM7 SOAP envelope response elements__

| Element | Description |
| ------------- | ------------------------ |
| TransactionID | The identification of the MM7 SubmitReq/SubmitRsp pair. It is located in the SOAP header. You supply this in the MM7 SubmitReq and Skycore returns it in the corresponding SubmitRsp. |
| SubmitRsp | Identifies the message as a MM7 Submit Response. This is the message type for an MT response. |
| MM7Version | Identifies the MM7 Version.<br/>[See all supported MM7 Versions] (/MM7/supportedMM7Versions.md) |
| StatusCode | MT message submit acception/rejection is based on Success/Failure status code. "Success" response does not mean the message was delivered to the handset.<br/>[See all Status Codes] (/MM7/Statuses/MmsStatuses.md) |
| StatusText | Description of the status code. |
| MessageId | If the MT message submit is successful then this contains the Skycore generated ID of the submitted message. This ID is expected in the delivery reports relating to this message. |

__Example: Success__

```xml
<?xml version="1.0" encoding="UTF-8" standalone="yes"?>
<soap-env:Envelope xmlns:soap-env="http://schemas.xmlsoap.org/soap/envelope/" xmlns=
"http://www.3gpp.org/ftp/Specs/archive/23_series/23.140/schema/REL-6-MM7-1-4">
   <soap-env:Header>
      <TransactionID soap-env:mustUnderstand="1">1000001</TransactionID>
   </soap-env:Header>
   <soap-env:Body>
      <SubmitRsp>
         <MM7Version>6.8.0</MM7Version>
         <Status>
            <StatusCode>1000</StatusCode>
            <StatusText>Successfully parsed and validated request</StatusText>
         </Status>
         <MessageID>369500617770864640</MessageID>
      </SubmitRsp>
   </soap-env:Body>
</soap-env:Envelope>
```

__Example: Failure__
```xml
<?xml version="1.0" encoding="UTF-8" standalone="yes"?>
<soap-env:Envelope xmlns:soap-env="http://schemas.xmlsoap.org/soap/envelope/" xmlns=
"http://www.3gpp.org/ftp/Specs/archive/23_series/23.140/schema/REL-6-MM7-1-4">
   <soap-env:Header>
      <TransactionID soap-env:mustUnderstand="1">1000001</TransactionID>
   </soap-env:Header>
   <soap-env:Body>
       <soap-env:Fault>
            <faultcode>soap-env:Client</faultcode>
            <faultstring>Client error</faultstring>
            <detail>
                  <RSErrorRsp>
                    <MM7Version>6.8.0</MM7Version>
                    <Status>
                        <StatusCode>2007</StatusCode>
                        <StatusText>Unable to parse request</StatusText>
                        <Details>Message format corrupt</Details>
                    </Status>
                  </RSErrorRsp>
            </detail>
        <soap-env:Fault>    
   </soap-env:Body>
</soap-env:Envelope>
```

<h3>MT Submit Full Example</h3>

__Request:__
```xml
POST /mm7/v1 HTTP/1.1
Authorization: Basic dW5pdmyc2FsLXZhcj2YWwtdmFzcC1wd2Q=
Host: api.skycore.com
Accept: */*
Content-Type: multipart/related; boundary="mainBoundary"; type="text/xml"; start="<mm7-start>"
SOAPAction: "http://www.3gpp.org/ftp/Specs/archive/23_series/23.140/schema/REL-6-MM7-1-4"
Content-Length: 45454
X-Skycore-Carrier-Id: 0001890
Expect: 100-continue

--mainBoundary
Content-Type: text/xml
Content-ID: <mm7-start>

<?xml version="1.0" encoding="UTF-8"?>
<soap-env:Envelope xmlns:soap-env="http://schemas.xmlsoap.org/soap/envelope/">
    <soap-env:Header>
        <TransactionID xmlns="http://www.3gpp.org/ftp/Specs/archive/23_series/23.140/schema/REL-6-MM7-1-4" soap-env:mustUnderstand="1">1000001</TransactionID>
    </soap-env:Header>
    <soap-env:Body>
        <SubmitReq xmlns="http://www.3gpp.org/ftp/Specs/archive/23_series/23.140/schema/REL-6-MM7-1-4">
            <MM7Version>6.8.0</MM7Version>
            <SenderIdentification>
                <VASPID>skfdjslkjfdslkfj434das</VASPID>
                <VASID>126273</VASID>
                <SenderAddress>
                    <ShortCode>111122</ShortCode>
                </SenderAddress>
            </SenderIdentification>
            <Recipients>
                <To>
                    <Number>16172383232</Number>
                </To>
            </Recipients>
            <Subject>My first MM7 Message</Subject>
            <Content allowAdaptations="false" href="cid:generic" />
        </SubmitReq>
    </soap-env:Body>
</soap-env:Envelope>

--mainBoundary
Content-Type: multipart/mixed; boundary="subBoundary"
Content-ID: <mm7Content>

--subBoundary
Content-Type: text/plain
Content-Transfer-Encoding: binary
Content-ID: text.txt
Hi! This is my first MMS MT message.

--subBoundary
Content-Type: image/png
Content-Transfer-Encoding: base64
Content-ID: image.png
iVBORw0KGgoAAAANSUhEUgAAABAAAAAQCAYAAAAf8/9hAAAABGdBTUEAAK/INwWK6QAAABl0RVh0
U29mdHdhcmUAQWRvYmUgSW1hZ2VSZWFkeXHJZTwAAAFUSURBVDjLrZM/SAJxGIZdWwuDlnCplkAE
m1zkaIiGFFpyMIwGK5KGoK2lphDKkMDg3LLUSIJs...

--subBoundary--

--mainBoundary--
```

__Response:__
```xml
HTTP/1.1 200 OK
Content-Type: application/xml; charset=utf-8
Date: Mon, 16 Mar 2015 17:46:59 GMT
Server: Apache
Vary: Accept-Encoding,User-Agent
Content-Length: 715
Connection: keep-alive

<?xml version="1.0" encoding="UTF-8" standalone="yes"?>
<soap-env:Envelope xmlns:soap-env="http://schemas.xmlsoap.org/soap/envelope/" xmlns=
"http://www.3gpp.org/ftp/Specs/archive/23_series/23.140/schema/REL-6-MM7-1-4">
   <soap-env:Header>
      <TransactionID soap-env:mustUnderstand="1">1000001</TransactionID>
   </soap-env:Header>
   <soap-env:Body>
      <SubmitRsp>
         <MM7Version>6.8.0</MM7Version>
         <Status>
            <StatusCode>1000</StatusCode>
            <StatusText>Successfully parsed and validated request</StatusText>
         </Status>
         <MessageID>369500617770864640</MessageID>
      </SubmitRsp>
   </soap-env:Body>
</soap-env:Envelope>
```
