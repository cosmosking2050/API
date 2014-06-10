<h2>Skycore API v1.3</h2>

<h3> Overview</h3>
Developers! Do you want to add Skycore's capabilities into your backend or campaign? Use our APIs below to integrate with us. Make sure to read this document before you get started. <a href="http://www.skycore.com/contact">Contact us</a> if you need assistance. The use of our API is only available for accounts with a Paid Plan. There is a free trial available to test message deliverability, formatting and latency through the user interface at <a href="http://www.skycore.com">Skycore.com</a>.


<h3>Fining your API Key</h3>

You must first request access to the API from your Skycore account manager. Once the API is turned on, you can find your API_KEY in the API Settings page under your 'Account' dropown. 

<h3>Using the API</h3>

<h4>Making API requests:</h4>

<code>GET Request</code>  - with URL encoded key/value pairs.

<code>POST Request</code> - with XML data passed inside an 'xml' variable. 

> Note: You must URL Encode the values in the query string of your GET Requests. Failure to do so may result in the API failing to fully interpret your request. For example this query string <code>&data_full_name=John Smith&data_age=35</code> would need to be encoded <code>&data_full_name=John+Smith&data_age=35</code> (space replaced with plus sign)




<h4>Receiving API callbacks:</h4>

<code>POST XML</code> - to the Postback URL defined in your Account's API Settings page. 

> If establishing a connection to your Postback URL takes longer than 10 seconds, the connection will time out and fail. We expect your server to respond with an successful status header containing HTTP STATUS 200. If no response is given or the HTTP code is not 200 we will consider it a failed request and will retry five minutes later up to 5 times.

<h4>API Limitations</h4>

You may have a throughput limit on your account. If your API requests exceed the throughput on your account then you may have some latency in the delivery of your messages. There may also be limits on the number of API calls allowed per second/minute/day. These limits will be published in your API Settings page. 

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
<h3>Special Considerations</h3>

<b>Always Use International Number Format!</b> You must use international format when sending SMS or MMS. International format includes both the country code with the phone number. We use the country code to determine routing of the message. There should be no dialing prefixes (eg 00 or 001) or special characters such as the plus symbol when submitting messages. (e.g. ’642111111′ not ‘+642111111′)

> For example the US number (774)-319-9144 in international number format would be 17743199144 because the USA country code is 1.


<h2>Table Of Contents</h2>

<h3>API Methods</h3>

<li><b>User</b></li>
    <ul>
    <li><a href="CONTENTS/METHODS/createUser.md">createUser</a></li>
    <li><a href="CONTENTS/METHODS/loginUser.md">loginUser</a></li>
    </ul>
<li><b>SMS/MMS</b></li>
    <ul>
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
   </ul>
<li><b>Email</b></li>
    <ul>
    <li><a href="CONTENTS/METHODS/getEmailIds.md">getEmailIds</a></li>
    <li><a href="CONTENTS/METHODS/getEmailCampaigns.md">getEmailCampaigns</a></li>
    <li><a href="CONTENTS/METHODS/createEmailCampaign.md">createEmailCampaign</a></li>
    <li><a href="CONTENTS/METHODS/sendSavedEmail.md">sendSavedEmail</a></li>
    <li><a href="CONTENTS/METHODS/subscribeEmail+unsubscribeEmail.md">subscribeEmail + unsubscribeEmail</a></li>
    </ul>
<li><b>Passbook</b></li>
    <ul>
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

<h3>Postback Notifications</h3>

<li><b>Postbacks</b></li>
* <a href="CONTENTS/POSTBACKS/POSTBACK_SMS+MMS_MO.md">SMS MO/MMS MO (Mobile Originated) Postbacks</a>
* <a href="CONTENTS/POSTBACKS/POSTBACK_SMS+MMS_MT.md">SMS MT/MMS MT (Mobile Terminated) Postbacks</a> 
* <a href="CONTENTS/POSTBACKS/POSTBACK_PASSES.md">Passbook Postbacks</a> 
* <a href="CONTENTS/POSTBACKS/POSTBACK_SUB+UNSUB.md">Subscribe + Unsubscribe Postbacks</a> 


<h3>Appendix</h3>

      <ul>
      <li><a href="CONTENTS/APPENDIX/APPENDIX_A.md">APPENDIX A [Key Term Definitions]</a></li>
      <li><a href="CONTENTS/APPENDIX/APPENDIX_B.md">APPENDIX B [API Error Codes]</a></li>
      <li><a href="CONTENTS/APPENDIX/APPENDIX_C.md">APPENDIX C [XML Report Export Format]</a></li>
      <li><a href="CONTENTS/APPENDIX/APPENDIX_D.md">APPENDIX D [Postback Notification Codes]</a></li>
      <li><a href="CONTENTS/APPENDIX/APPENDIX_E.md">APPENDIX E [Carrier / SPID Reference Table]</a></li>
      </ul>
  

