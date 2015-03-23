[Back to the Table of Contents](/MM7/UNSUPPORTED-SOAP-ELEMENTS/)

##Unsupported MM7 SOAP Elements

__MM7_DeliveryReport.REQ__

| Element | Description |
| ---------- | -------------------------- |
| ApplicID | This information element indicates the identification of the application that the delivery report is intended for. If a Reply-Applic-ID was indicated in the corresponding original MM, the recipient MMS Relay/Server shall set its value to that Reply-Applic-ID value. Otherwise, the recipient MMS Relay/Server shall set its value to the Applic-ID value that was indicated in the corresponding original MM |
| AuxApplicInfo | If present, this information element indicates additional application/implementation specific control information. The recipient MMS Relay/Server shall insert it if Aux-Applic-Info was indicated in the corresponding original MM, in which case its value shall equal that Aux-Applic-Info value |
| MMSRelayServerID | Identifier of the MMS Relay/Server |
| ReplyApplicID | If present, this information element indicates a "reply path" to this delivery report, i.e. the identification of an application to which reply-MMs are addressed. The recipient MMS Relay/Server shall insert it into the MM1_DeliveryReport.REQ if the values of Applic-ID and Reply-Applic-ID in the corresponding original MM differ, in which case its value shall equal the Applic-ID value that was indicated in the corresponding original MM |
