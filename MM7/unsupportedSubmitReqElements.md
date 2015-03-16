
<h3>Unsupported elements for SubmitReq</h3>

The following MM7 request elements are not supported by Skycore. Skycore does not validate these elements. In a future release, transactions that include such elements may be rejected with an error.

The elements are:
<ul>
    <li>ApplicID</li>
    <li>AuxApplicInfo</li>
    <li>ChargedPartyId</li>
    <li>ContentClass</li>
    <li>DeliveryCondition</li>
    <li>DeliveryReport</li>
    <li>DistributionIndicator</li>
    <li>DRMContent</li>
    <li>EarliestDeliveryTime</li>
    <li>ExpiryDate</li>
    <li>LinkedID (for MT message delivery and delivery reports; MO MMS deliveries will contain this element)</li>
    <li>MessageClass</li>
    <li>Priority</li>
    <li>ReadCharging</li>
    <li>ReadReply</li>
    <li>ReplyApplicID</li>
    <li>replyChargingSize (attribute of ReplyCharging element)</li>
    <li>replyDeadline</li>
    <li>ServiceCode</li>
    <li>TimeStamp</li>
</ul>
