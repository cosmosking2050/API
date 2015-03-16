##MMS Status Codes

| StatusCode | StatusText | Details |
| --------- | ------------- | ---------------------- |
|1000|Success|Successfully parsed and validated request.|
|2000|Client error|Invalid IP Address or Protocol|
|2002|Address Error|Invalid Address|
|2004|Multimedia refused|Carrier refuses content|
|2007|Unable to parse request|Message format corrupt|
|2300|Account disabled|Your account is no longer provisioned for MMS|
|2301|Account not Provisioned for MM7|Your account is not provisioned for MM7 API|
|2400|Content length exceeded maximum supported request size|Reduce the size of the content you are sending.|
|2401|Invalid sender identification|Sender identification invalid or missing.|
|2402|Invalid VASID|The VASID is your ServiceID|
|2403|Invalid source address|The Shortcode may be incorrect or not provisioned|
|2404|Invalid VASPID|The VASPID is your API Key|
|2405|Message rejected, reply charging not supported|Message rejected, reply charging not supported|
|2406|Invalid carrier|Invalid carrier ID.|
|2407|Missing carrier ID|Carrier ID is required to be passed|
|2408|Unable to authenticate|Ensure the HTTP username and password you have specified are correct and formatted properly within the Authorization header.|
|2500|Missing or Invalid HTTP header Content-Length or Content-Type|Ensure the HTTP Content-Length and Content Type header are included and valid.|
|2502|Missing destination address|Ensure the recipient is specified correctly for the MM7 version that is used.|
|2503|Multiple destination addresses not supported|Multiple recipients not supported. Instead, create multiple messages|
|2504|Missing source address|Ensure source address is specified correctly for the MM7 version that is used|
|2505|Missing or unsupported MM7 Version|Ensure specified MM7 version is on the list of supported versions, and is in the format x.y.z|
|2506|Missing XML element - Content|Ensure the Content element is included in the SubmitRequest.|
|2507|Unsupported namespace|Ensure that all the namespaces specified are on the list of supported namespaces.|
|2510|Missing or Invalid SOAP header|Ensure the SOAP envelope contains a SOAP header with only the TransactionID element|
|2511|Missing or Invalid SOAP body|Ensure the SOAP envelope contains a SOAP body with the SubmitReq|
|2512|Unsupported operation|SubmitReq is the only supported operation|
|2513|Unable to parse attachment|Ensure your attachment is specified, and encoded properly|
|2514|Invalid SOAP attachment header Content-Type|Ensure the Content-Type headers of all the attachments are formatted properly|
|2515|Invalid SOAP body part Content-Type|Ensure the Content-Type header of the SOAP body part, aka the SOAP envelope part, is formatted properly|
|3000|System error|Internal system/service error.|
|3001|Number blacklisted|Phone number is blacklisted for receiving messages do not retry|
|3002|Charged party not supported|Charged Party not supported|
|3003|Multimedia download failed|Using URLs in the MM7 the fetch of content failed or took too long|
|3100|Throughput exceeded|Throughput exceeded please retry later|
|3200|Provisioning issue|Provisioning problem, please contact your account manager|
|3500|Timeout|Carrier gateway timeout|
|4000|General service error|Carrier rejects the message due to a general service error|
|4002|Unsuported MM7 version|The carrier does not support this MM7 version|
|4003|Unsupported operation|Carrier rejects the message due to unsupported operation or format|
|4004|Validation error|Validation error|
|4006|Service unavailable|Carrier capacity reached. Retry later|
|4007|Service denied|Carrier denies service for the recipient address|
