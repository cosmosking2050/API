
<h3>Unsupported elements for SubmitReq</h3>

The following MM7 request elements are not supported by Skycore. Skycore does not validate these elements. In a future release, transactions that include such elements may be rejected with an error.

The elements are:
ApplicID
AuxApplicInfo
ChargedPartyId
ContentClass
DeliveryCondition
DeliveryReport
DistributionIndicator
DRMContent
EarliestDeliveryTime
ExpiryDate
LinkedID (for MT message delivery and delivery reports; MO MMS deliveries will contain this element)
MessageClass
Priority
ReadCharging
ReadReply
ReplyApplicID
replyChargingSize (attribute of ReplyCharging element)
replyDeadline
ServiceCode
TimeStamp
