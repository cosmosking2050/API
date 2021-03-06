[Back to the Table of Contents](/MM7/UNSUPPORTED-ELEMENTS/)

##Unsupported MM7 SOAP Elements

__MM7_Submit.REQ__

| Element | Behavior | Description |
| ------- | ---- | ----------------|
| ApplicID | Stripped | This information element contains the identification of the destination application. Upon reception, the recipient MMS VAS Application shall provide this MM7_retrieve.REQ to the specified destination application |
| AuxApplicInfo | Stripped | If present, this information element indicates additional application/implementation specific control information |
| ChargedParty | Error | An indication which party is expected to be charged for an MM submitted by the VASP, e.g. the sending, receiving, both parties third party or neither. Possible values are "Sender", "Recipient", "Both", "Neither" |
| ChargedPartyID | Error | The address/id of the third party which is expected to pay for the MM |
| ContentClass | Stripped | Classifies the content of the MM to the smallest content class to which the MM belongs. Possible values are "text", "image-basic", "image-rich", "video-basic", "video-rich", "megapixel", "content-basic", "content-rich" |
| DeliveryCondition | Stripped | If the condition is met the MM shall be delivered to the recipient MMS User Agent, otherwise the MM shall be discarded. The initial values are: MMS capable only; HPLMN only; any other values can be added based on bilateral agreements between the MMS Relay/Server operator and the VASP. |
| DeliveryReport | Default to true | A request for delivery report. Boolean value true/false. Ask your account manager to turn off delivery reports. |
| DistributionIndicator | Stripped | If set to 'false' the VASP has indicated that content of the MM is not intended for redistribution. If set to 'true' the VASP has indicated that content of the MM can be redistributed. Boolean value true/false |
| DRMContent | Stripped | Indicates if the MM contains DRM-protected content. Boolean value true/false |
| EarliestDeliveryTime | Stripped | The earliest desired time of delivery of the MM to the recipient (time stamp). Date format is absolute or relative |
| ExpiryDate | Default to 3 days | The desired time of expiry for the MM (time stamp). Date format is absolute. |
| LinkedID | Stripped | This identifies a correspondence to a previous valid message delivered to the VASP.  |
| MessageClass | Pass Through | Class of the MM (e.g. "Informational", "Advertisement", "Auto") |
| Priority | Pass Through | The priority (importance) of the message. Possible values are "High", "Normal", "Low" |
| ReadReply | Stripped | A request for confirmation via a read report to be delivered. Boolean true/false value. Set it 'true' to receive MM7 Read Replies. |
| ReplyApplicID | Stripped |  If present, this information element indicates a "reply path". It contains the application identifier which shall be used by the recipient MMS VAS Application when a reply-MM or a read-reply report is created |
| ReplyCharging | Error | A request for reply-charging. No value. Presence implies true |
| <i>replyChargingSize</i> | Error | In case of reply-charging the maximum size for reply-MM(s) granted to the recipient(s). Optional attribute of ReplyCharging element. Positive integer value |
| <i>replyDeadline</i> | Error | In case of reply-charging the latest time of submission of replies granted to the recipient(s) (time stamp). Optional attribute of ReplyCharging element. Date format is absolute or relative | 
| ServiceCode | Pass Through | Information supplied by the VASP which may be included in charging/billing information. The syntax and semantics of the content of this information are out of the scope of this specification. |
| TimeStamp | Default to Submit time | The time and date of the submission of the MM (time stamp) | 
