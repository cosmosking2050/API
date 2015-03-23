[Back to the Table of Contents](/MM7/)

##Unsupported MM7 SOAP Elements

The following MM7 request elements are not supported. These elements are ignored and never validated. Future version releases may respond with an error if unsupported element are used in SubmitReq.

__MM7_Submit.REQ__

| Element | Description |
| ----------- | -------------------------------- |
|ApplicID| This information element contains the identification of the destination application. Upon reception, the recipient MMS VAS Application shall provide this MM7_retrieve.REQ to the specified destination application |
|AuxApplicInfo| If present, this information element indicates additional application/implementation specific control information |
|ChargedParty| An indication which party is expected to be charged for an MM submitted by the VASP, e.g. the sending, receiving, both parties third party or neither. Possible values are "Sender", "Recipient", "Both", "Neither" |
|ChargedPartyID| The address/id of the third party which is expected to pay for the MM |
|ContentClass| Classifies the content of the MM to the smallest content class to which the MM belongs. Possible values are "text", "image-basic", "image-rich", "video-basic", "video-rich", "megapixel", "content-basic", "content-rich" |
|DeliveryCondition| If the condition is met the MM shall be delivered to the recipient MMS User Agent, otherwise the MM shall be discarded. The initial values are: MMS capable only; HPLMN only; any other values can be added based on bilateral agreements between the MMS Relay/Server operator and the VASP. |
|DeliveryReport| A request for delivery report. Boolean value true/false. |
|DistributionIndicator| If set to 'false' the VASP has indicated that content of the MM is not intended for redistribution. If set to 'true' the VASP has indicated that content of the MM can be redistributed. Boolean value true/false |
|DRMContent| Indicates if the MM contains DRM-protected content. Boolean value true/false |
|EarliestDeliveryTime| The earliest desired time of delivery of the MM to the recipient (time stamp). Date format is absolute or relative |
|ExpiryDate| The desired time of expiry for the MM (time stamp). Date format is absolute or relative |
|LinkedID| This identifies a correspondence to a previous valid message delivered to the VASP.  |
|MessageClass| Class of the MM (e.g. "Informational", "Advertisement", "Auto") |
|Priority| The priority (importance) of the message. Possible values are "High", "Normal", "Low" |
|ReadReply| A request for confirmation via a read report to be delivered. Boolean true/false value. Set it 'true' to receive MM7 Read Replies. |
|ReplyApplicID| If present, this information element indicates a "reply path". It contains the application identifier which shall be used by the recipient MMS VAS Application when a reply-MM or a read-reply report is created |
|ReplyCharging| A request for reply-charging. No value. Presence implies true |
|<i>replyChargingSize</i>| In case of reply-charging the maximum size for reply-MM(s) granted to the recipient(s). Optional attribute of ReplyCharging element. Positive integer value |
|<i>replyDeadline</i>| In case of reply-charging the latest time of submission of replies granted to the recipient(s) (time stamp). Optional attribute of ReplyCharging element. Date format is absolute or relative | 
|ServiceCode| Information supplied by the VASP which may be included in charging/billing information. The syntax and semantics of the content of this information are out of the scope of this specification. |
|TimeStamp|The time and date of the submission of the MM (time stamp) |


__MM7_Deliver.REQ__

| Element | Description |
| ---------- | -------------------------- |
|ApplicID| The presence of this information element indicates that this abstract message shall be provided to an application residing on an MMS User Agent. It contains the identification of the destination application|
|AuxApplicInfo| If present, this information element indicates additional application/implementation specific control information |
|MMSRelayServerID|Identifier of the MMS Relay/Server|
|RecipientSPI| The SPI of the intended MM recipient, in case the MM was delivered to VASP based on the recipient address |
|ReplyApplicID| If present, this information element indicates a “reply path”, i.e. the identifier of the application to which delivery reports, read-reply reports and reply-MMs are addressed if any |
|ReplyChargingID| In case of reply-charging when the reply-MM is submitted within the MM7_deliver.REQ this is the identification of the original MM that is replied to. |
|SenderSPI| The SPI of the MM originator |

__MM7_DeliveryReport.REQ__

| Element | Description |
| ---------- | -------------------------- |
|ApplicID| This information element indicates the identification of the application that the delivery report is intended
for. If a Reply-Applic-ID was indicated in the corresponding original MM, the recipient MMS Relay/Server shall set its
value to that Reply-Applic-ID value. Otherwise, the recipient MMS Relay/Server shall set its value to the Applic-ID
value that was indicated in the corresponding original MM |
|AuxApplicInfo| If present, this information element indicates additional application/implementation specific control
information. The recipient MMS Relay/Server shall insert it if Aux-Applic-Info was indicated in the
corresponding original MM, in which case its value shall equal that Aux-Applic-Info value |
|MMSRelayServerID|Identifier of the MMS Relay/Server|
|ReplyApplicID|  If present, this information element indicates a "reply path" to this delivery report, i.e. the
identification of an application to which reply-MMs are addressed. The recipient MMS Relay/Server shall insert it into
the MM1_DeliveryReport.REQ if the values of Applic-ID and Reply-Applic-ID in the corresponding original MM
differ, in which case its value shall equal the Applic-ID value that was indicated in the corresponding original MM |


