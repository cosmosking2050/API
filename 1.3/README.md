<h2>Skycore API</h2>

<h3> Overview</h3>
Developers! Do you want to add Skycore's capabilities into your backend or campaign? Use our APIs below to integrate with us. Make sure to read this document before you get started. <a href="http://www.skycore.com/contact">Contact us</a> if you need assistance. The use of our API is only available for accounts with a Paid Plan. There is a free trial available to test message deliverability, formatting and latency through the user interface at <a href="http://www.skycore.com">Skycore.com</a>.


<h3>Fining your API Key</h3>

You must first request access to the API from your Skycore account manager. Once the API is turned on, you can find your API_KEY in the API Settings page under your 'Account' dropown. 

<h3>Using the API</h3>

There are two ways of making API requests:

<code>GET Request</code>  - with URL encoded key/value pairs.

<code>POST Request</code> - with XML data passed inside an 'xml' variable. 

There is one way of receiving API callbacks:

<code>POST XML</code> - to the Postback URL defined in your Account's API Settings page. 

<h3>Authentication</h3>

Authenticating your API call can be done in two ways:

<code>apikey</code> – Each API request must contain the accounts APIKEY. Some API requests may also require an MD5 encrypted password. 


<b>Authentication Error codes:</b>
E100, E101, E102, E103, E104, E105, E106, E107, E108, E109

*Error Example:*
```xml
<RESPONSE>
  <STATUS>Failure</STATUS>
  <ERRORCODE>E101</ERRORCODE>
  <ERRORINFO> 'action' required</ERRORINFO>
</RESPONSE>
```


<h2>Table of Contents</h2>
<ul>
  <li> <a href="CONTENTS/METHODS/API_METHODS.md">API Methods</a></li>
    <ul>
    <li><a href="CONTENTS/METHODS/createUser.md">createUser</a></li>
    <li><a href="CONTENTS/METHODS/loginUser.md">loginUser</a></li>
    <li><a href="CONTENTS/METHODS/sendSMS.md">sendSMS</a></li>
    <li><a href="CONTENTS/METHODS/getMmsIds.md">getMmsIds</a></li>
    <li><a href="CONTENTS/METHODS/getMmsCampaigns.md">getMmsCampaigns</a></li>
    <li><a href="CONTENTS/METHODS/saveMMS.md">saveMMS</a></li>
    <li><a href="CONTENTS/METHODS/sendSavedMMS.md">sendSavedMMS</a></li>
    <li><a href="CONTENTS/METHODS/sendMMSBarcode.md">sendMMSBarcode</a></li>
    <li><a href="CONTENTS/METHODS/sendSavedMMSCampaign.md">sendSavedMMSCampaign</a></li>
    <li><a href="CONTENTS/METHODS/subscribe+unsubscribe.md">subscribe + unsubscribe</a></li>
    <li><a href="CONTENTS/METHODS/createMMSCampaign.md">createMMSCampaign</a></li>
    <li><a href="CONTENTS/METHODS/getSendingStatistics.md">getSendingStatistics</a></li>
    <li><a href="CONTENTS/METHODS/removeMMSInboxMessage.md">removeMMSInboxMessage</a></li>
    <li><a href="CONTENTS/METHODS/getEmailIds.md">getEmailIds</a></li>
    <li><a href="CONTENTS/METHODS/getEmailCampaigns.md">getEmailCampaigns</a></li>
    <li><a href="CONTENTS/METHODS/createEmailCampaign.md">createEmailCampaign</a></li>
    <li><a href="CONTENTS/METHODS/sendSavedEmail.md">sendSavedEmail</a></li>
    <li><a href="CONTENTS/METHODS/subscribeEmail+unsubscribeEmail.md">subscribeEmail + unsubscribeEmail</a></li>
    <li><a href="CONTENTS/METHODS/getPassTemplate.md">getPassTemplate</a></li>
    <li><a href="CONTENTS/METHODS/getPassTemplateIds.md">getPassTemplateIds</a></li>
    <li><a href="CONTENTS/METHODS/addPassData.md">addPassData</a></li>
    <li><a href="CONTENTS/METHODS/updatePass.md">updatePass</a></li>
    <li><a href="CONTENTS/METHODS/deletePassData.md">deletePassData</a></li>
    <li><a href="CONTENTS/METHODS/sendPassInEmail.md">sendPassInEmail</a></li>
    <li><a href="CONTENTS/METHODS/sendPassInMMS.md">sendPassInMMS</a></li>
    <li><a href="CONTENTS/METHODS/generatePassById.md">generatePassById</a></li>
    <li><a href="CONTENTS/METHODS/generatePass.md">generatePass</a></li>
    <li><a href="CONTENTS/METHODS/getPassEmailTemplate.md">getPassEmailTemplate</a></li>
    </ul>
   <br/>
  <li><a href="CONTENTS/POSTBACKS/POSTBACK_SYSTEM_OVERVIEW.md">Postback Notifications</a></li>
    <ul>
    <li><a href="CONTENTS/POSTBACKS/POSTBACK_SMS+MMS_MO.md">SMS MO/MMS MO (Mobile Originated) Postbacks</a></li>
    <li><a href="CONTENTS/POSTBACKS/POSTBACK_SMS+MMS_MT.md">SMS MT/MMS MT (Mobile Terminated) Postbacks</a> </li>
    <li><a href="CONTENTS/POSTBACKS/POSTBACK_PASSES.md">Passbook Postbacks</a> </li>
    <li><a href="CONTENTS/POSTBACKS/POSTBACK_SUB+UNSUB.md">Subscribe + Unsubscribe Postbacks</a> </li>
    </ul>
    <br/>
  <li> <a href="CONTENTS/APPENDIX/API_APPENDIX.md">APPENDIX</a> </li>
    <ul>
      <li><a href="CONTENTS/APPENDIX/APPENDIX_A.md">APPENDIX A [Key Term Definitions]</a></li>
      <li><a href="CONTENTS/APPENDIX/APPENDIX_B.md">APPENDIX B [Error/Notification/Protocol Code References]</a></li>
      <li><a href="CONTENTS/APPENDIX/APPENDIX_C.md">APPENDIX C [XML Report Export Format]</a></li>
      <li><a href="CONTENTS/APPENDIX/APPENDIX_D.md">APPENDIX D [Special API Considerations]</a></li>
      <li><a href="CONTENTS/APPENDIX/APPENDIX_E.md">APPENDIX E [Carrier / SPID Reference Table]</a></li>
   </ul>
</ul>

