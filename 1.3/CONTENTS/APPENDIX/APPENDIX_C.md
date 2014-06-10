<a href="/1.3/README.md">Back to the Table of Contents</a>&nbsp;&nbsp;|&nbsp;&nbsp;<a href="API_APPENDIX.md">Back to Appendix List</a>
<h2>APPENDIX C</h2>
<div class="text-2"><a id="appendix-b"></a><strong>XML Reports,Campaign Batches,Autoresponders, Subscriptions and Sending Lists</strong></div><br/>
<div class="text-2"><a id="appendix-b"></a><strong>Request Limit for getSendingStatistics()</strong></div>
<p>When getSendingStatistics() API function is called the Platform responds with a URL link that leads to an XML file to be downloaded. You are limited in the number of requests you can make per day to this API and in the period duration for which you want to get the report.</p>
<p>The report is a list of sent SMS/MMS xml reports grouped into sections.</p>
<p><strong>SMS sending XML</strong></p>
<p>All data related to sending one SMS are encapsulated inside <em>&lt;TEXT&gt;</em> tag which contains a few attributes:</p>
<p>- <em>id</em> &#8211; this sending id in our history</p>
<p>- <em>to</em> -receiver&#8217;s phone number</p>
<p>- <em>carrier</em> -receiver&#8217;s carrier</p>
<p>- <em>from</em> &#8211; the shortcode message was sent from</p>
<p>- <em>body</em> &#8211; text sent to the number</p>
<p>Inside &lt;TEXT&gt; we list all status updates for that message. There are two statuses updates:</p>
<p>- ACK &#8211; Message has been processed on our side and left our server (status 10)</p>
<p>- DLR or ERROR &#8211; We received delivery report stating the delivery was successfull DLR (status 20) or failed (ERROR).</p>
<p>Here is the example of SMS sending XML:</p>
<pre>&lt;TEXT id="455118" to="11112233444" carrier="Verizon Wireless" from="60856" 
 body="Jack: Hello My friend!"&gt;
   &lt;ACK gw="10" net="0" time="2012-04-30T08:30:12.327558Z"&gt;
   &lt;DLR gw="20" net="0" time="2012-04-30T08:30:12.327558Z"&gt;
&lt;/TEXT&gt;</pre>
<p><strong>MMS sending XML</strong></p>
<p>All data related to sending one MMS are encapsulated inside <em>&lt;CONTENT&gt;</em> tag which contain few attributes:</p>
<p>- <em>id</em> &#8211; this sending id in our history</p>
<p>- <em>to</em> -receiver&#8217;s phone number</p>
<p>- <em>carrier</em> -receiver&#8217;s carrier</p>
<p>- <em>contentid</em> -id of the content/MMS</p>
<p>- <em>contentname</em> -name of the content/MMS</p>
<p>- <em>from</em> &#8211; the shortcode message was sent from</p>
<p>- <em>delivery</em> &#8211; the delivery type binary/xhtml</p>
<p>Inside &lt;<em>CONTENT</em>&gt; we have &lt;<em>MSG_STATUS</em>&gt; tag which encapsulate all status updates for that message and &lt;<em>MM7_HANDSETID</em>&gt;/&lt;<em>XHTML_HANDSETID</em>&gt;</p>
<p>&lt;<em>MSG_STATUS</em>&gt; contain all SMS/MMS status updates, we update each SMS/MMS status multiple times during the sending process and tag will indicate which stage of the sending process the SMS/MMS is in.</p>
<p>For BINARY MMS sending, our statuses are in chronological order:</p>
<ul>
<li>INQUE &#8211; Message inserted into processing que.</li>
<li>INIT &#8211; Processing message has been started (status 0)</li>
<li>ACK or ERROR &#8211; Message has been processed on our side and left our server (ACK &#8211; status 9) or some internal ERROR occured.</li>
<li>DLR or EXPIRED or REJECTED &#8211; We received delivery report, meaning phone has received the message (DLR &#8211; status 20) or carrier rejected MMS (REJECTED &#8211; status 35) or carrier could not deliver MMS to handset (EXPIRED &#8211; status 30).</li>
</ul>
<p>Based on the sendings we do sent binary Device Discovery Message (DDM) that preceed sending real MMS, statuses for DDM are as follows:</p>
<ul>
<li>INQUE &#8211; Message inserted into processing que.</li>
<li>ACK &#8211; Message has been processed on our side and left our server (ACK &#8211; status 80)</li>
<li>DLR or EXPIRED or REJECTED &#8211; We received DDM delivery report, meaning phone has received the message (DLR &#8211; status 81) or carrier rejected MMS (REJECTED &#8211; status 35) or carrier could not deliver MMS to handset (EXPIRED &#8211; status 30). When we receive DLR status for DDM sending of real MMS is triggered instantly.</li>
</ul>
<p>For XHTML MMS we also have in chronological order:</p>
<ul>
<li>INQUE &#8211; Message inserted into processing que.</li>
<li>INIT &#8211; Processing message has been started (status 0)</li>
<li>ACK or ERROR &#8211; Message has been processed on our side and link has been sent to the phone (ACK &#8211; status 10) or some internal ERROR occured.</li>
<li>DLR &#8211; We received delivery report, meaning phone has received the link (status 20)</li>
<li>OPENED &#8211; Link has been browsed (status 11).</li>
</ul>
<p>&lt;<em>MM7_HANDSETID</em>&gt;/&lt;<em>XHTML_HANDSETID</em>&gt; contain detected handset. For binary delivery we are placing the handsetid inside &lt;<em>MM7_HANDSTID</em>&gt;, for xhtml delivery we put the browser UA Profile inside &lt;<em>XHTML_HANDSETID</em>&gt;</p>
<p>Here is the example of MMS sending XML (binary delivery):</p>
<pre>&lt;CONTENT id="455076" carrier="T-Mobile" to="11112233444" delivery="binary" 
 contentid="40301" contentname="Flowers" from="60856"&gt; 
   &lt;MSG_STATUS&gt; 
      &lt;INQUE time="2012-04-24T04:45:15.655766Z" /&gt; 
      &lt;INIT gw="0" net="0" time="2012-04-24T04:45:16.831756Z"/&gt; 
      &lt;ACK gw="9" net="0" time="2012-04-24T04:45:18.80118Z"/&gt; 
      &lt;DLR gw="20" net="1000" time="2012-04-24T04:45:23.953745Z"/&gt; 
   &lt;/MSG_STATUS&gt; 
   &lt;MM7_HANDSETID&gt;motol7c&lt;/MM7_HANDSETID&gt; 
&lt;/CONTENT&gt;</pre>
<p>Here is the example of MMS sending XML (xhtml delivery):</p>
<pre>&lt;CONTENT id="455119" to="48111222333" carrier="All Carriers" delivery="xhtml" 
 contentid="39755" contentname="Flowers" from="+447624805892" &gt;
   &lt;MSG_STATUS&gt;
      &lt;INQUE time="2012-04-30T09:06:07.5649Z" /&gt;
      &lt;INIT gw="0" net="0" time="2012-04-30T09:06:08.338719Z"/&gt;
      &lt;ACK gw="10" net="0" time="2012-04-30T09:06:08.918484Z"/&gt;
      &lt;OPENED gw="11" net="0" time="2012-04-30T09:06:39.258603Z"/&gt;
      &lt;DLR gw="20" net="0" time="2012-04-30T09:06:08.783382Z"&gt;
   &lt;/MSG_STATUS&gt;
   &lt;XHTML_HANDSETID&gt;Mozilla/5.0 (Windows NT 6.1; WOW64) AppleWebKit/535.19 
    (KHTML, like Gecko) Chrome/18.0.1025.162 Safari/535.19&lt;/XHTML_HANDSETID&gt;
&lt;/CONTENT&gt;</pre>
<h3>Report</h3>
<p>The Report itself contains a list of all messages grouped into sections encapsulated into &lt;RESPONSE&gt; tag. Here are more detailed examples of what we have in each section.</p>
<p><strong>A) Campaign Batches</strong> are encapsulated inside <em>&lt;BATCHES&gt;&lt;/BATCHES&gt;.</em> Each MMS/SMS batch contain a list of SMS/MMS XML that is encalpsulated inside &lt;<em>BATCH</em>&gt;&lt;/<em>BATCH</em>&gt; tag.Batches represent Campaign scheduled sending of the MMS or SMS. Each<em> &lt;BATCH&gt; </em>tag contain attributes:</p>
<p>- <em>id</em> &#8211; this is campaign scheduled sending id</p>
<p>- <em>campaignid</em> &#8211; campaign ID</p>
<p>- <em>campaignname</em> -Campaign name</p>
<p>- <em>scheduled_date</em> &#8211; Date the Campaign was scheduled to be sent out</p>
<p>- <em>contentid</em> &#8211; (only for MMS) name of the content/MMS sent to the phones</p>
<p>- <em>contentname</em> &#8211; (only for MMS) name of the content/MMS sent to the phones</p>
<p>- <em>body</em> &#8211; (only for MMS) text of the SMS sent to the phones</p>
<p>- <em>from</em> &#8211; the shortcode messages were sent from</p>
<p>Because some attributes are common across whole campaign scheduled sending we do not place them inside SMS/MMS XML and just have them inside &lt;<em>BATCH</em>&gt; tag. Those attributes are: <em>contentid</em>, <em>contentname</em> (for MMS sent from Campaign)<em>, body</em> (for SMS sent from Campiagn)<em>, from.<br />
</em></p>
<p>Here is MMS sending inside Campaign batch</p>
<pre>&lt;BATCHES&gt;
   &lt;BATCH id="12418" from="60856" campaignid="1136" campaignname="MyCampaign" 
    scheduled_date="2010-10-12 06:32:46.620197-04@server localtime" contentid="35080" 
    contentname="Flowers" /&gt;
      &lt;CONTENT id="150838" carrier="Verizon Wireless" to="11112233444" delivery="binary"&gt;
         &lt;MSG_STATUS&gt;
            &lt;INQUE time="2010-10-12T06:32:46.620197Z" /&gt;
            &lt;INIT gw="0" net="0" time="2010-10-12T06:33:12.115367Z"/&gt;
            &lt;ACK gw="9" net="1000" time="2010-10-12T06:33:12.508827Z"/&gt;
            &lt;DLR gw="20" net="1000" time="2010-10-12T06:33:19.579773Z"/&gt;
         &lt;/MSG_STATUS&gt;
         &lt;MM7_HANDSETID&gt;VX8000v1&lt;/MM7_HANDSETID&gt;
      &lt;/CONTENT&gt;
      ....
      ....
   &lt;/BATCH&gt;
   ....
   ....
&lt;/BATCHES&gt;</pre>
<p>Here is SMS sending inside alert batch</p>
<pre>&lt;BATCHES&gt;
   &lt;BATCH id="21896" from="60856" scheduled_date="2012-04-27T13:00:00Z@server localtime" 
    campaignid="1442" campaignname="MyCampaign" body="Sample SMS for Campaign" /&gt; 
      &lt;TEXT id="455110" to="11112233444"&gt;
         &lt;ACK gw="10" net="0" time="2012-04-27T13:05:05.89278Z"&gt;
         &lt;DLR gw="20" net="0" time="2012-04-27T13:05:05.89278Z"&gt; 
      &lt;/TEXT&gt;
      &lt;TEXT id="455109" to="11112233444"&gt;
         &lt;ACK gw="10" net="0" time="2012-04-27T13:05:05.881257Z"&gt;
         &lt;DLR gw="20" net="0" time="2012-04-27T13:05:05.881257Z"&gt;
      &lt;/TEXT&gt; 
      ....
      ....
   &lt;/BATCH&gt;
   ....
   ....
&lt;/BATCHES&gt;</pre>
<p><strong>B) Campaign autoresponder</strong> are encapsulated inside <em>&lt;AUTORESPONDERS&gt;&lt;/<em>AUTORESPONDERS</em>&gt;.</em> Each MMS/SMS autoresponder contain a list of SMS/MMS XML that is encalpsulated inside &lt;<em><em>AUTORESPONDER</em></em>&gt;&lt;/<em><em>AUTORESPONDER</em></em>&gt; tag. Autoresponders represent all MMS/SMS sendings of one Campaign autoresponder. Each<em> &lt;<em>AUTORESPONDER</em>&gt; </em>tag contain attributes:</p>
<p>- <em>id</em> &#8211; this is campaign autoresponder id</p>
<p>- <em>campaignid</em> &#8211; campaign ID</p>
<p>- <em>campaignname</em> -Campaign name</p>
<p>- <em>contentid</em> &#8211; (only for MMS) name of the content/MMS sent to the phones</p>
<p>- <em>contentname</em> &#8211; (only for MMS) name of the content/MMS sent to the phones</p>
<p>- <em>body</em> &#8211; (only for MMS) text of the SMS sent to the phones</p>
<p>- <em>from</em> &#8211; the shortcode messages were sent from</p>
<p>Because some attributes are common across whole campaign autoresponder sending we do not place them inside SMS/MMS XML and just have them inside &lt;<em>AUTORESPONDER</em>&gt; tag. Those attributes are: <em>contentid</em>, <em>contentname</em> (for MMS Autoresponders)<em>, body</em> (for SMS Autoresponders)<em>, from.</em></p>
<p>Here is MMS Autoresponder example:</p>
<pre>&lt;AUTORESPONDERS&gt;
   &lt;AUTORESPONDER id="351" from="60856" campaignid="1442" campaignname="MyCampaign" 
    contentid="40301" contentname="Flowers" /&gt; 
      &lt;CONTENT id="455076" carrier="T-Mobile" to="11112233444" delivery="binary"&gt; 
         &lt;MSG_STATUS&gt; 
            &lt;INQUE time="2012-04-24T04:45:15.655766Z" /&gt; 
            &lt;INIT gw="0" net="0" time="2012-04-24T04:45:16.831756Z"/&gt; 
            &lt;ACK gw="9" net="0" time="2012-04-24T04:45:18.80118Z"/&gt; 
            &lt;DLR gw="20" net="1000" time="2012-04-24T04:45:23.953745Z"/&gt; 
         &lt;/MSG_STATUS&gt; 
         &lt;MM7_HANDSETID&gt;motol7c&lt;/MM7_HANDSETID&gt; 
      &lt;/CONTENT&gt;
      ....
      ....
   &lt;/AUTORESPONDER&gt;
   ....
   ....
&lt;/AUTORESPONDERS&gt;</pre>
<p>Here is SMS Autoresponder example:</p>
<pre>&lt;AUTORESPONDERS&gt;
   &lt;AUTORESPONDER id="352" from="60856" campaignid="1442" campaignname="MyCampaign" 
    body="text autoresponder" /&gt;
      &lt;TEXT id="455078" to="11112233444"&gt;
         &lt;ACK gw="10" net="0" time="2012-04-24T04:45:48.133354Z"&gt;
         &lt;DLR gw="20" net="0" time="2012-04-24T04:45:48.133354Z"&gt;
      &lt;/TEXT&gt;
      &lt;TEXT id="455077" to="11112233444"&gt;
         &lt;ACK gw="10" net="0" time="2012-04-24T04:45:17.278337Z"&gt;
         &lt;DLR gw="20" net="0" time="2012-04-24T04:45:17.278337Z"&gt;
      &lt;/TEXT&gt;
      .... 
      .... 
   &lt;/AUTORESPONDER&gt;
   ....
   ....
&lt;/AUTORESPONDERS&gt;</pre>
<p><strong>C) Campaign Subscriptions</strong> are encapsulated inside <em>&lt;SUBSCRIPTIONS&gt;&lt;/<em>SUBSCRIPTIONS</em>&gt;.</em> Traffic generated for each subscription contain a list of SMS/MMS XML that is encalpsulated inside &lt;SUB&gt;&lt;/<em><em>SUB</em></em>&gt; tag. Each<em> &lt;<em>SUB</em>&gt; </em>tag contain attributes:</p>
<p>- <em>to</em> &#8211; subscriber&#8217;s phone number</p>
<p>- <em>carrier</em>- Subscriber&#8217;s carrier</p>
<p>- <em>from</em> &#8211; the shortcode messages were sent from</p>
<p>All above mentioned attributes are common across whole subscription traffic and we don&#8217;t put inside SMS/MMS XML and just have them inside &lt;<em>SUB</em>&gt; tag.</p>
<p>Here is the example of the traffic for the Single Opt-In subscription with SMS Confirmation:</p>
<pre>&lt;SUBSCRIPTIONS&gt;
   &lt;SUB to="11112233444" carrier="AT&amp;T" from="60856"&gt; 
      &lt;TEXT id="455037" text="MyBrand: Confirmed to MyCampaign, msg/. Msg&amp;Data rates may 
       apply. Reply STOP to cancel, HELP for help. Enterprisem.ms" &gt;
         &lt;ACK gw="10" net="0" time="2012-04-10T06:38:56.090705Z"&gt;
         &lt;DLR gw="20" net="0" time="2012-04-10T06:38:56.090705Z"&gt;
      &lt;/TEXT&gt; 
   &lt;/SUB&gt;
   ....
   ....
&lt;/SUBSCRIPTIONS&gt;</pre>
<p>Here is the example of the traffic for the Double Opt-In subscription with MMS Confirmation:</p>
<pre>&lt;SUBSCRIPTIONS&gt;
   &lt;SUB to="11112233444" carrier="T-Mobile" from="60856"&gt;
      &lt;CONTENT id="455112" contentid="39755" contentname="Flowers" delivery="binary"&gt;
         &lt;MSG_STATUS&gt;
            &lt;INQUE time="2012-04-27T13:32:21.798528Z" /&gt;
      &lt;INIT gw="0" net="0" time="2012-04-27T13:32:22.204127Z"/&gt;
	    &lt;ACK gw="9" net="0" time="2012-04-27T13:32:24.200166Z"/&gt;	    
         &lt;/MSG_STATUS&gt;
         &lt;MM7_HANDSETID&gt;Default&lt;/MM7_HANDSETID&gt;
      &lt;/CONTENT&gt;
      &lt;TEXT id="455111" text="MyBrand: To follow MyCampaign,  msg/, reply YES. 
       Msg&amp;Data rates may apply. Reply HELP for help. Enterprisem.ms." &gt;
         &lt;ACK gw="10" net="0" time="2012-04-27T13:32:12.892155Z"&gt;
         &lt;DLR gw="20" net="0" time="2012-04-27T13:32:12.892155Z"&gt;
      &lt;/TEXT&gt;
   &lt;/SUB&gt;
   ....
   ....
&lt;/SUBSCRIPTIONS&gt;</pre>
<p><strong>D) Sending List</strong> contain all other SMS/MMS senidngs encapsulated into &lt;<em>SENDING_LIST</em>&gt;&lt;/<em>SENDING_LIS</em>T&gt; tag. This contain a list of &lt;<em>CONTENT</em>&gt; and &lt;<em>TEXT</em>&gt; tags<br />
Below is example of MMS:</p>
<pre>&lt;SENDING_LIST&gt;
   &lt;CONTENT id="455043" carrier="All Carriers" to="48111222333" delivery="xhtml" 
    contentid="39755" contentname="Flowers" from="+447624805892" &gt;
      &lt;MSG_STATUS&gt;
         &lt;INQUE time="2012-04-23T09:04:57.353055Z" /&gt;
         &lt;INIT gw="0" net="0" time="2012-04-23T09:04:58.048795Z"/&gt;
         &lt;ACK gw="10" net="0" time="2012-04-23T09:05:03.516081Z"/&gt;
         &lt;ERROR info="delivery failure" time="2012-04-23T09:05:02.982315Z"&gt;	    
      &lt;/MSG_STATUS&gt;
   &lt;/CONTENT&gt;
   ....
   ....
&lt;SENDING_LIST&gt;</pre>
<p>Below is example of SMS:</p>
<pre>&lt;SENDING_LIST&gt;
   &lt;TEXT id="150283" to="11112233444" text="Hello my friend. Where do you want to go today?"&gt;
      &lt;ACK gw="10" net="0" time="2010-10-05T12:21:40.947088Z"&gt;
      &lt;DLR gw="20" net="0" time="2010-10-05T12:21:40.947088Z"&gt;
   &lt;/TEXT&gt;
   ....
   ....
&tt;SENDING_LIST&gt;</pre>
