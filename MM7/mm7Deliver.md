[Back to the Table of Contents](/MM7/)

## MM7_Deliver

__Receive MMS MO submitted by end users to your platform__

Skycore delivers messages from end users to your platform by supplying the MMS as the payload of the request message. The deliver request is made using MM7 SOAP "DeliverReq". Message include identification of the request that is used by your platform to correlate a response to the message. Your platform must reply with a SOAP response "DeliverRsp", indicating that the message was successfully received and will be processed. If you cannot identify the requested content or if the delivered content does not fulfill the conditions you'd expect, then your platform should indicate a failure in the "DeliverRsp" status field.

<h3>DeliverReq</h3>
__MM7 MO deliver request elements__

__1. HTTP header elements__

| Header Name | Description | Mandatory |
| -------------- | ------------------- | -------- |
| X-Skycore-Carrier-Id | Skycore Mobile Operator ID.<br/>Examples: AT&T=0001470, Verizon=0001890.<br/>[See all Skycore Operator IDs] (/MM7/skycoreOperatorIDs.md).  | No |

__2. Elements in the SOAP header and body__

| Element | Description | Returned |
| ------------ | ------------------ | ------------------ |
| TransactionID | It is a Skycore generated transaction ID.Identifies the DeliverReq/DeliverRsp pair. | Always |
| DeliverReq | Identifies the message as an MM7 deliver request. | Always |
| MM7Version | Identifies the MM7 Version.<br/>[See all supported MM7 Versions] (/MM7/supportedMM7Versions.md) | Always |
| Sender | The mobile phone number of the end user. This must be a valid mobile number in international format without a leading + symbol; for example: 12515550123 (US) and 447700900750 (UK). | Always |
| Recipients | The address of the message recipients i.e., Shortcode/Longcode | Always | 
| LinkedID | Identifier for the MO message. This is a Skycore generated ID. | Always |
| TimeStamp | The date and time of the submission of the MO message. This value is in UTC. | Always |
| Priority | The priority (importance) of the message. Possible values: High, Normal, Low | Only when provided by mobile operator |
| Subject | Title of the whole multimedia message. | Only when provided by mobile operator |
| Content | A reference to the content of the MM7 message. Contains an "href:cid" attribute that links to the content ID of the first attachment in the MM7 message. | Only when provided by mobile operator |
| UACapabilities | Information about the capabilities of the MMS user agent that originated the multimedia message. In this context, the associated timestamp is not populated. | Only when provided by mobile operator |

[See Unsupported elements] (/MM7/unsupportedMM7Elements.md)

__Example__

```xml
<?xml version="1.0" encoding="UTF-8" standalone="yes"?>
<soap-env:Envelope xmlns:ns1="http://schemas.xmlsoap.org/soap/envelope/" xmlns=
"http://www.3gpp.org/ftp/Specs/archive/23_series/23.140/schema/REL-6-MM7-1-4">
<soap-env::Header>
   <TransactionID soap-env:mustUnderstand="1">1000001</TransactionID>
</soap-env::Header>
<soap-env::Body>
   <DeliverReq>
      <MM7Version>6.8.0</MM7Version>
      <LinkedID>1000001</LinkedID>
      <Sender>
         <Number>1617423433</Number>
      </Sender>
      <Recipients>
         <To>
         <Number displayOnly="false">111122</Number>
         </To>
      </Recipients>
      <TimeStamp>2014-04-14T16:15:23.414Z</TimeStamp>
      <Priority>Normal</Priority>
      <Content href="cid:default.cid" allowAdaptations="true"/>
   </DeliverReq>
</soap-env:Body>
</soap-env:Envelope>
```

<h3>DeliverRsp</h3>
__MM7 MO deliver response elements__

Your system should respond to the deliver request with a deliver response containing the elements described in the following table.

| Element | Description |
| ------------- | ------------------------ |
| TransactionID | Identifies the DeliverReq/DeliverRsp pair. It is part of the SOAP header. The value returned is the one provided in the request. |
| DeliverRsp | Identifies the message as a MM7 Deliver Response. |
| MM7Version | Identifies the MM7 Version.<br/>[See all supported MM7 Versions] (/MM7/supportedMM7Versions.md) |
| StatusCode | A code that indicates whether you recieved the MO message request successfully. The status code for successful deliver is 1000.<br/>[See all Status Codes] (/MM7/Statuses/MmsStatuses.md) |
| StatusText | Description of the status code. |

__Example__

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<soap-env:Envelope xmlns:soap-env="http://schemas.xmlsoap.org/soap/envelope/" xmlns:xsi=
"http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
<soap-env:Header>
   <TransactionID soap-env:mustUnderstand="1">1000001</TransactionID>
</soap-env:Header>
<soap-env:Body>
   <DeliverRsp xmlns="http://www.3gpp.org/ftp/Specs/archive/23_series/23.140/
   schema/REL-6-MM7-1-4">
      <MM7Version>6.8.0</MM7Version>
      <Status>
         <StatusCode>1000</StatusCode>
         <StatusText>Successfully received MMS</StatusText>
      </Status>
   </DeliverRsp>
</soap-env:Body>
</soap-env:Envelope>
```

<h3>Receive MMS MO Full Example</h3>

__Request__

```xml
POST / HTTP/1.1
SOAPAction: "http://www.3gpp.org/ftp/Specs/archive/23_series/23.140/schema/REL-6-MM7-1-4"
Content-Type: multipart/related; start="soap-start"; type="text/xml"; 
        boundary="----=_Part_139078_1411587550.1397492135426"
Host: api.skycore.com
Content-Length: 2546
X-Skycore-Carrier-Id: 0001890
Connection: Keep-Alive

------=_Part_139078_1411587550.1397492135426
Content-Type: text/xml
Content-ID: <soap-start>
<?xml version="1.0" encoding="UTF-8" standalone="yes"?>
<soap-env:Envelope xmlns:ns1="http://schemas.xmlsoap.org/soap/envelope/" xmlns=
"http://www.3gpp.org/ftp/Specs/archive/23_series/23.140/schema/REL-6-MM7-1-4">
<soap-env::Header>
   <TransactionID soap-env:mustUnderstand="1">1000001</TransactionID>
</soap-env::Header>
<soap-env::Body>
   <DeliverReq>
      <MM7Version>6.8.0</MM7Version>
      <LinkedID>1000001</LinkedID>
      <Sender>
         <Number>1617423433</Number>
      </Sender>
      <Recipients>
         <To>
         <Number displayOnly="false">111122</Number>
         </To>
      </Recipients>
      <TimeStamp>2014-04-14T16:15:23.414Z</TimeStamp>
      <Priority>Normal</Priority>
      <Content href="cid:default.cid" allowAdaptations="true"/>
   </DeliverReq>
</soap-env:Body>
</soap-env:Envelope>

------=_Part_139078_1411587550.1397492135426
Content-Type: multipart/mixed; 
        boundary="----=_Part_139079_1300104441.1397492135426"
Content-ID: <default.cid>

------=_Part_139079_1300104441.1397492135426
Content-Type: image/jpeg
Content-Transfer-Encoding: binary
Content-ID: image_0.jpg
<Binary contents>

------=_Part_139079_1300104441.1397492135426
Content-Type: text/plain
Content-Transfer-Encoding: binary
Content-ID: text_0.txt
Test MO message!

------=_Part_139079_1300104441.1397492135426--

------=_Part_139078_1411587550.1397492135426--
```

__Response__

```xml
HTTP/1.1 200 OK
Server: Apache
Content-Type: application/xml; charset=utf-8
Content-Length: 715
Date: Mon, 16 Mar 2015 17:46:59 GMT

<?xml version="1.0" encoding="UTF-8" ?>
<soap-env:Envelope xmlns:soap-env="http://schemas.xmlsoap.org/soap/envelope/" xmlns:xsi=
"http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
<soap-env:Header>
   <TransactionID soap-env:mustUnderstand="1">1000001</TransactionID>
</soap-env:Header>
<soap-env:Body>
   <DeliverRsp xmlns="http://www.3gpp.org/ftp/Specs/archive/23_series/23.140/
   schema/REL-6-MM7-1-4">
      <MM7Version>6.8.0</MM7Version>
      <Status>
         <StatusCode>1000</StatusCode>
         <StatusText>Successfully received MMS</StatusText>
      </Status>
   </DeliverRsp>
</soap-env:Body>
</soap-env:Envelope>
```
