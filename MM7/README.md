[Back to Root](../../../)

##Skycore MM7 v1.0

__Overview__

MMS APIs are currently offered via an implementation of the MM7 protocol. MM7 is the standard protocol used by the carriers to send and receive MMS messages. It is a SOAP based protocol sent over HTTP. MM7 supports the following API actions:

| Action | Functionality |
|------------------------|----------------------------------------------------|
| [SubmitReq & SubmitRsp] (/MM7/mm7SubmitMT.md) | Send an MT Message to a device. |
| [DeliverReq & DeliverRsp] (/MM7/mm7DeliverMO.md) | Receive an MO message from the device. |
| [DeliveryReportReq & DeliveryReportRsp] (/MM7/mm7DeliveryReport.md) | Receive a Delivery report for a previously submitted MT MMS Message. |

The use of our MM7 API is only available for accounts with a paid plan. We support submitting MMS messages with MM7 version 5.3.0 to 6.8.0. Your VASPID will be your API Key. We will issue you a VASID to submit with your message. The VASID will be unique on each short code. All traffic is encrypted in transit via SSL/TLS. We authenticate using the VASPID, Shortcode and typically VASID. We support, but do not require basic authentication. For added security we can also authenticate your accounts IP address (IP Whitelisting) along with your other credentials. 

__Finding your VASPID (API Key)__

You must first request access to the API from your account manager. Once the API is turned on, you can find your API Key in the API Settings page under your 'Account' dropdown. Alternatively your account manager will provide you with the Key. You can reset the Key at any time to revoke access. Your username and password for your account are seperate from your API key so you do not have to worry about a account password reset affecting your services. 

__Finding your VASID__

Your account manager will provide you with a VASID for each shortcode. If you use a dedicated shortcode you can pick your own VASID or we can configure it empty.

__Receiving Delivery Reports and MO's__

Your Delivery Report URL and MO URL is configured in your Account's API Settings page. You can update it at any time.  SOAP requests will be forwarded to your server every second and require an HTTP STATUS 200 and a proper MM7 SOAP Response or else we will retry. You can also turn off the SOAP notifications to your server and download a CSV of final message statues from the User Interface.

> We expect your server to accept our postback within 10 seconds by responding with a standard HTTP STATUS 200 header (success) and proper SOAP Response with matching MM7 TransactionID and Status 1000. If establishing a connection to your Postback URL takes longer than 10 seconds, the connection will time out and be dropped.  If the connection times out or the HTTP code is not 200 we will retry the notification again five minutes later for a maximum of 5 retries per notification.

__API Limitations__

You may have a throughput limit on your account. If your API requests exceed the throughput on your account then you may have some latency in the delivery of your messages. There may also be limits on the number of API calls allowed per second/minute/day. These limits will be published in your API Settings page. If you exceed this limit then your messasge will be rejected and you will be required to retry the request. 

__Authentication__

Authenticating your API call can be done via a combination of the IP Whitelist, VASPID and Shortcode. For shared shortcodes, we will also authenticate the VASID.

__Special Considerations__

<i>Always Use International Number Format:</i> You must use international format when submitting an MM7 message to Skycore. International format includes both the country code with the phone number. We use the country code to determine routing of the message. There should be no dialing prefixes (eg 00 or 001) or special characters such as the plus symbol when submitting messages. (example: '642111111' not '+642111111'). If you submit a message without a country code the message will likely get routed to the wrong country and you may end up paying for the delivery there.

> For example the US number (774)-319-9144 in international number format would be 17743199144 because the USA country code is 1.
