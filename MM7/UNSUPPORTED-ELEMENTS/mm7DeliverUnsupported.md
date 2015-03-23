[Back to the Table of Contents](/MM7/UNSUPPORTED-ELEMENTS/)

##Unsupported MM7 SOAP Elements

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
