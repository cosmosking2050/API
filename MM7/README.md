<h1>Coming soon!... </h1>

<h2>Skycore MM7 v1.0</h2>

<h3> Overview</h3>

MMS APIs are currently offered via an implementation of the MM7 protocol. MM7 is the standard protocol used by the carriers to send and receive MMS messages. It is a SOAP based protocol sent over HTTP. MM7 supports the following API actions:
<ul>
  <li>SubmitReq - used to send an MT Message to a device </li>
  <li>DeliverReq - used to receive an MO message from the device <li>
</ul>

The use of our MM7 API is only available for accounts with a paid plan. We support submitting MMS messages with MM7 version 5.3.0 to 6.8.0. Your VASPID will be your API Key. We will issue you a VASID to submit with your message. We do not require basic authentication but we do support IP Whitelisting your IP address to your account credentials. 

<h3>Finding your API Key (VASPID)</h3>

You must first request access to the API from your Skycore account manager. Once the API is turned on, you can find your API Key in the API Settings page under your 'Account' dropdown. 

<h3>Finding your VASID</h3>

Your account manager will provide you with a VASID for each shortcode. If you use a dedicated shortcode you can pick your own VASID or we can configure it empty.

<h4>Receiving Delivery Reports and MO's:</h4>

The Delivery Report URL and MO URL is configured in your Account's API Settings page. You can update it at any time.  SOAP requests will be forwarded to your server every second and require an HTTP STATUS 200 response. You can also turn off the SOAP notifications to your server and download a CSV of final message statues from the User Interface.

> We expect your server to accept our postback within 10 seconds by responding with a stanard HTTP STATUS 200 header (success). If establishing a connection to your Postback URL takes longer than 10 seconds, the connection will time out and be dropped.  If the connection times out or the HTTP code is not 200 we will retry the notification again five minutes later for a maximum of 5 retries per notification.

<h4>API Limitations</h4>

You may have a throughput limit on your account. If your API requests exceed the throughput on your account then you may have some latency in the delivery of your messages. There may also be limits on the number of API calls allowed per second/minute/day. These limits will be published in your API Settings page. If you exceed this limit then your messasge will be rejected and you will be required to retry the request. 

<h3>Authentication</h3>

Authenticating your API call can be done via a combination of the IPWhielist, VASPID and Shortcode. For shared shortcodes we will also authenticate the VASID. 

<h3>Special Considerations</h3>

<b>Always Use International Number Format!</b> You must use international format when submitting an MM7 message to Skycore. International format includes both the country code with the phone number. We use the country code to determine routing of the message. There should be no dialing prefixes (eg 00 or 001) or special characters such as the plus symbol when submitting messages. (e.g. ’642111111′ not ‘+642111111′). If you submit a message without a country code the message will likely get routed to the wrong country and you may end up paying for the delivery there. 

> For example the US number (774)-319-9144 in international number format would be 17743199144 because the USA country code is 1.
