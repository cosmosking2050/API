<a href="/1.3/README.md">Back to the Table of Contents</a>&nbsp;&nbsp;|&nbsp;&nbsp;<a href="API_METHODS.md">Back to API Methods</a>
<h2>getSendingStatistics</h2>
<p><strong>Synopsis:</strong><br />
This API requests a report of all messaging transactions between two dates. The Dates should be given in UTC. The server returns the path to an XML file containing the report. All results are saved to file which must be 
downloaded by the requestor. Detailed Information about the report will be 
in <a href="/1.3/CONTENTS/APPENDIX/APPENDIX_C.md">Appendix C</a>.  
<div><strong>Request:</strong></div>
<pre>&lt;REQUEST&gt;
    &lt;ACTION&gt;getSendingStatus &lt;/ACTION&gt;
    &lt;API_KEY&gt;API KEY&lt;/API_KEY&gt;
    &lt;START_DATE&gt;UTC StartDate&lt;/START_DATE&gt;
    &lt;END_DATE&gt;UTC EndDate&lt;/ END_DATE&gt;
&lt;/REQUEST&gt;</pre>
<div><strong>Request Parameters:</strong></div>
<pre><strong>Mandatory:</strong> Action, API_KEY, End_Date, Start_Date
<strong>Optional:</strong> N/A</pre>
<strong>Response Parameters:</strong><br />
Errorcode, Errorinfo, MMSID, Status<br>
<strong>Related Errorcodes: </strong><br />
E506, E507, E508, E509, E510
<div><strong>Request Examples</strong></div>
XML:
<pre>&lt;REQUEST&gt;
  &lt;ACTION&gt;getSendingStatus&lt;/ACTION&gt;
	&lt;API_KEY&gt;qTFkykO9JTfahCOqJ0V2Wf5Cg1t8iWlZ&lt;/API_KEY&gt;
	&lt;START_DATE&gt;2010-10-01 12:00:00&lt;/START_DATE&gt;
	&lt;END_DATE&gt;2010-10-02 12:00:00&lt;/END_DATE&gt;
&lt;/REQUEST&gt;</pre>
GET:
<pre>https://secure.skycore.com/API/wxml/1.3/index.php?action=getsendingstatus&api_key=qTFkykO9JTfahCOqJ0V2Wf5Cg1t8iWlZ
&start_date=2010-10-01+12:00:00&end_date=2010-10-02+12:00:00</pre>
<p><strong>Response Example:</strong><br />
Responses will be a link to a XML file containing the report. All results are saved to file which must be downloaded by the requestor. Detailed Information about the report will be in <a href="/1.3/CONTENTS/APPENDICES/APPENDIX_C.md">Appendix C</a>.</p>
