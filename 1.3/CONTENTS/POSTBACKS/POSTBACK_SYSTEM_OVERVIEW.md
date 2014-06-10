<a href="/1.3/README.md">Back to the Table of Contents</a>
<h2>Overview: Postback Notification System</h2>

<strong>What is a postback?</strong>
<ul>
<li>A postback is a notification sent via a single HTTP POST request in XML format from Skycore's servers to a user-specified URL containing information relative to the user's account regarding the following events:</li>
<ul>
<li>Subscribes/Unsubscribes</li>
<li>SMS/MMS MO(Mobile Originated)</li>
<li>SMS/MMS MT(Mobile Terminated)</li>
<li>Pass Generation</li>
<li>A saved MMS (via API or MMS composer)</li>
</ul>
</ul>

<strong>How do postbacks work?</strong>
<ul>
<li>Specific events trigger their respective postbacks, these postbacks are then placed in a queue.</li>
<li>Postbacks in the queue are then processed and sent out every second to the user-specified URL.</li>
<li>Upon a server's reception of the postback, we expect the server to respond with a properly formatted HTTP header containing an HTTP 200 code.</li>
</ul>

<strong>Important Notes</strong>
<ul>
<li>If establishing a connection to the user-specified Postback URL takes longer than 10 seconds, the connection will time out and fail.  After that, we will attempt to resend the postback every 5 minutes up to a total of 5 times.</li>
<li>If the HTTP response from the user's server is not provided or the HTTP code is not 200, we consider the postback a failed request and we will attempt to resend the postback every 5 minutes up to a total of 5 times.</li>
<li> The following tags are always a part of our postbacks:
  <ul>
  <li>ORIGIN &#8211; identifies origin type of the postback</li>
  <li>CODE &#8211; identifies situation for which the postback was generated. See <a href="/1.3/CONTENTS/APPENDIX/APPENDIX_D.md">APPENDIX D</a> for all notification code definitions.</li>
  </ul>
</ul>


