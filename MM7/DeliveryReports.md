[Back to the Table of Contents](/MM7/)

## Receiving Delivery Reports

Skycore sends delivery reports using the MM7 Delivery Report message type i.e., "DeliveryReportReq". The delivery report indicates the current state of the original submit request message. We will send a delivery report to your platform only when the appropriate information is available. If the delivery report message is accepted or rejected then respond with an "DeliveryReportRsp", including a status that indicates why the delivery report was accepted/rejected.

__Understanding the delivery report status__

For information about the status codes returned for Delivery Reports, please [See Delivery report status] (/MM7/deliveryReportStatuses.md)

__MM7 delivery report request elements__

__Elements in the SOAP header and body__

| Element | Description | Returned |
| ------------ | ------------------ | ------------------ |
| TransactionID | This identifies the DeliveryReportReq/DeliveryReportRsp pair. It is Skycore generated ID. | Always |
| DeliveryReportReq | Identifies the message as an MM7 Delivery Report. | Always |
| MM7Version | Identifies the MM7 Version.<br/>[See all supported MM7 Versions] (/MM7/supportedMM7Versions.md) | Always |
| Recipient | The mobile phone number of the end user. This must be a valid mobile number in international format without a leading + symbol; for example: 12515550123 (US) and 447700900750 (UK). | Always |
| Sender | Your shortcode. This should match the same information that is linked in the MT configuration, and generally to the service you are providing.| Always | 
| MessageID | Skycore generated ID linked to the submitted message. This ID was returned to your system in the initial response (SubmitRsp) to your MT MMS request. | Always |
| Date | The date and time of the submission of the multimedia message (timestamp). Value is in UTC. | Always |
| MMStatus | A code that indicates whether the MT message was delivered successful or failed. For information about the status codes returned for Delivery Reports, please [See Delivery report status] (/MM7/deliveryReportStatuses.md). | Always |
| UACapabilities | Also known as MMS User Agent capabilities. This describes the capabilities of the MMS User agent of the mobile handset. | Only when provided by mobile operator |
