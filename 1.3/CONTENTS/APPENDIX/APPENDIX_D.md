<a href="/1.3/README.md">Back to the Table of Contents</a>&nbsp;&nbsp;|&nbsp;&nbsp;<a href="API_APPENDIX.md">Back to Appendix List</a>
<h2>APPENDIX D</h2>
<strong>Special Considerations Regarding API Usage</strong>

<p><strong>International format numbers: </strong> You must use international format. International format is a number format that includes the countrycode with the phone number. There should be no dialing prefixes (eg 00 or 001) or special characters such as the plus symbol (e.g. &#8217;642111111&#8242; not &#8216;+642111111&#8242;). For example the US number (774)-319-9144 in international number format would be 17743199144 because the USA country code is 1.</p>

<p><strong>Sending limitations:</strong> You may have a throughput limit on your account. If your API requests 
exceed the throughput on your account then you may have some latency in the delivery of your messages.</p>

<p><strong>Postback:</strong>  If establishing a connection to your Postback URL takes longer than 10 seconds, the 
connection will time out and fail. We expect your server to respond with an successful status header containing HTTP STATUS 200. If no response is given or the HTTP code is not 200 we will consider it a failed request and will retry five minutes later up to 5 times.</p>

<p><strong>GET Requests:</strong> You must URL Encode the values in the query string of your HTTP GET 
requests. Failure to do so may result in the API failing to fully interpret your request. For example, your 
unencoded query string may look like this:</p>

<p><u>Before encoding</u>:<br /><pre>&data_full_name=John Smith&data_age=35</pre></p>
<p><u>After encoding</u>: (space replaced with plus sign)<br />
<pre>&data_full_name=John+Smith&data_age=35</pre></p>
