<a href="/1.3/README.md">Back to the Table of Contents</a>&nbsp;&nbsp;|&nbsp;&nbsp;<a href="API_APPENDIX.md">Back to Appendix List</a>
<h2>APPENDIX B</h2>
<div class="text-2"><a id="appendix-b"></a><strong>Error Code Reference</strong></div>
<br/>
<p><strong>i. Error Codes </strong></p>
<table class="toc" style="font-size:11px;">
<tbody>
<tr>
<td>E100 Invalid request. Make request via GET method or send valid XML inside 'xml' field via POST.</td>
<td>E821 Pass was not deleted. Internal error occured.</td>
</tr>
<tr>
<td>E101 'action' required/Invalid Action</td>
<td>E822 There is no pass found in this MMS Template to send.</td>
</tr>
<tr>
<td>E102 'user' or 'api_key' required</td>
<td>E823 There is no pass found in this email template to send.</td>
</tr>
<tr>
<td>E103 'pass' md5(password) required</td>
<td>E824 Invalid call to the API. There is no pass data supplied.</td>
</tr>
<tr>
<td>E104 User Authentication FAILED</td>
<td>E827 Invalid request. 'mmsid' or 'emailtemplateid' or 'passtemplateid' is required</td>
</tr>
<tr>
<td>E105 This account has no API rights</td>
<td>E828 Invalid request. You can request only by 'mmsid' or 'emailtemplateid' or 'passtemplateid' and not more than one</td>
</tr>
<tr>
<td>E106 You can call API every X seconds</td>
<td>E829 'custom identifier value' is invalid. Only Alphabet, Numbers or a Space is allowed</td>
</tr>
<tr>
<td>E107 This account has no rights to use this action</td>
<td>E830 Pass was not generated. Internal error occured</td>
</tr>
<tr>
<td>E108 XML Parse error: $error</td>
<td>E831 Pass was not generated. It reached its download limit</td>
</tr>
<tr>
<td>E109 API not activated</td>
<td>E833 This Pass Template is set to send Personalized Passes. Atleast 'email' or 'phone' or 'custom identifier' is required with the Pass Data</td>
</tr>
<tr>
<td>E110 Invalid receiver number</td>
<td>E840 'headerlabel1' is not accepted. It has to be set as Dynamic in the Pass Template</td>
</tr>
<tr>
<td>E111 Invalid shortcode</td>
<td>E841 'headervalue1' is not accepted. It has to be set as Dynamic in the Pass Template</td>
</tr>
<tr>
<td>E120 Account has reached the API request limit.</td>
<td>E842 'primarylabel1' is not accepted. It has to be set as Dynamic in the Pass Template</td>
</tr>
<tr>
<td>E150 The 'newuser' is required</td>
<td>E843 'primaryvalue1' is not accepted. It has to be set as Dynamic in the Pass Template</td>
</tr>
<tr>
<td>E151 'newuser' already exists</td>
<td>E844 'primarylabel2' is not accepted. It has to be set as Dynamic in the Pass Template</td>
</tr>
<tr>
<td>E152 The 'newpass' is required</td>
<td>E845 'primaryvalue2' is not accepted. It has to be set as Dynamic in the Pass Template</td>
</tr>
<tr>
<td>E153 User was not created. Internal error occurred</td>
<td>E846'seclabel1' is not accepted. It has to be set as Dynamic in the Pass Template</td>
</tr>
<tr>
<td>E154 User was not created. Internal error occurred.</td>
<td>E847'secvalue1' is not accepted. It has to be set as Dynamic in the Pass Template</td>
</tr>
<tr>
<td>E170 'campaignname' is required</td>
<td>E848'seclabel2' is not accepted. It has to be set as Dynamic in the Pass Template</td>
</tr>
<tr>
<td>E171 'brandname' is required</td>
<td>E849'secvalue2' is not accepted. It has to be set as Dynamic in the Pass Template</td>
</tr>
<tr>
<td>E172 Campaign was not created. Internal error occured. Please try again later.</td>
<td>E850'seclabel3' is not accepted. It has to be set as Dynamic in the Pass Template</td>
</tr>
<tr>
<td>E173 'mailingaddress' is required</td>
<td>E851'secvalue3' is not accepted. It has to be set as Dynamic in the Pass Template</td>
</tr>
<tr>
<td>E201 The receiver number is required</td>
<td>E852'seclabel4' is not accepted. It has to be set as Dynamic in the Pass Template</td>
</tr>
<tr>
<td>E225 Too many Slides</td>
<td>E853'secvalue4' is not accepted. It has to be set as Dynamic in the Pass Template</td>
</tr>
<tr>
<td>E226 Audio and Video not allowed in same slide</td>
<td>E854 'auxlabel1' is not accepted. It has to be set as Dynamic in the Pass Template</td>
</tr>
<tr>
<td>E227 Video and Image not allowed in same slide</td>
<td>E855 'auxvalue1' is not accepted. It has to be set as Dynamic in the Pass Template</td>
</tr>
<tr>
<td>E228 Text more than X characters</td>
<td>E856 'auxlabel2' is not accepted. It has to be set as Dynamic in the Pass Template</td>
</tr>
<tr>
<td>E229 Content not allowed</td>
<td>E857 'auxvalue2' is not accepted. It has to be set as Dynamic in the Pass Template</td>
</tr>
<tr>
<td>E230 Bad X slide duration</td>
<td>E858 'auxlabel3' is not accepted. It has to be set as Dynamic in the Pass Template</td>
</tr>
<tr>
<td>E241 This content does not exist</td>
<td>E859 'auxvalue3' is not accepted. It has to be set as Dynamic in the Pass Template</td>
</tr>
<tr>
<td>E301 The 'name' is required</td>
<td>E860 'auxlabel4' is not accepted. It has to be set as Dynamic in the Pass Template</td>
</tr>
<tr>
<td>E302 No slides</td>
<td>E861 'auxvalue4' is not accepted. It has to be set as Dynamic in the Pass Template</td> 
<tr>
<td>E303 Slide X is empty</td>
<td>E862 'backlabel1' is not accepted. It has to be set as Dynamic in the Pass Template</td>
</tr>
<tr>
<td>E331 Image in slide X is too big</td>
<td>E863 'backvalue1' is not accepted. It has to be set as Dynamic in the Pass Template</td>
</tr>
<tr>
<td>E332 Audio in slide X is too big</td>
<td>E864 'backlabel2' is not accepted. It has to be set as Dynamic in the Pass Template</td>
</tr>
<tr>
<td>E333 Video in slide X is too big</td>
<td>E865 'backvalue2' is not accepted. It has to be set as Dynamic in the Pass Template</td>
</tr>
<tr>
<td>E334 Text in slide X is too long</td>
<td>E866 'backlabel3' is not accepted. It has to be set as Dynamic in the Pass Template</td>
</tr>
<tr>
<td>E341 Image file in slide X is corrupted</td>
<td>E867 'backvalue3' is not accepted. It has to be set as Dynamic in the Pass Template</td>
</tr>
<tr>
<td>E351 Could not copy Image in slide X</td>
<td>E868 'backlabel4' is not accepted. It has to be set as Dynamic in the Pass Template</td>
</tr>
<tr>
<td>E400 No Email Templates were created in this account</td>
<td>E869 'backvalue4' is not accepted. It has to be set as Dynamic in the Pass Template</td>
</tr>
<tr>
<td>E401 Invalid email</td>
<td>E870 'rellatitude1', 'relongitude1' and 'reltext1' are not accepted. Relevance Location1 has to be set as Dynamic in the Pass Template</td>
</tr>
<tr>
<td>E402 Invalid 'emailid' (or) 'emailtemplateid'</td>
<td>E871 'rellatitude2', 'relongitude2' and 'reltext2' are not accepted. Relevance Location2 has to be set as Dynamic in the Pass Template</td>
</tr>
<tr>
<td>E403 Could not send email due to missing dataset entry</td>
<td>E872 'rellatitude3', 'relongitude3' and 'reltext3' are not accepted. Relevance Location3 has to be set as Dynamic in the Pass Template</td>
</tr>
<tr>
<td>E404 No Email Campaigns were created in this account</td>
<td>E873 'rellatitude4', 'relongitude4' and 'reltext4' are not accepted. Relevance Location4 has to be set as Dynamic in the Pass Template</td>
</tr>
<tr>
<td>E405 No MMS Campaigns were created in this account</td>
<td>E874 'rellatitude5', 'relongitude5' and 'reltext5' are not accepted. Relevance Location5 has to be set as Dynamic in the Pass Template</td>
</tr>
<tr>
<td>E503 Internal error</td>
<td>E875 'rellatitude6', 'relongitude6' and 'reltext6' are not accepted. Relevance Location6 has to be set as Dynamic in the Pass Template</td>
</tr>
<tr>
<td>E506 'start_date'/'end_date' is required</td>
<td>E876 'rellatitude7', 'relongitude7' and 'reltext7' are not accepted. Relevance Location7 has to be set as Dynamic in the Pass Template</td>
</tr>
<tr>
<td>E507 Invalid 'start_date'/'end_date' format</td>
<td>E877 'rellatitude8', 'relongitude8' and 'reltext8' are not accepted. Relevance Location8 has to be set as Dynamic in the Pass Template</td>
</tr>
<tr>
<td>E508 Invalid 'start_date'/'end_date' format</td>
<td>E878 'rellatitude9', 'relongitude9' and 'reltext9' are not accepted. Relevance Location9 has to be set as Dynamic in the Pass Template</td>
</tr>
<tr>
<td>E509 Lookup period is too long</td>
<td>E879 'rellatitude10', 'relongitude10' and 'reltext10' are not accepted. Relevance Location10 has to be set as Dynamic in the Pass Template</td>
</tr>
<tr>
<td>E510 Lookup too frequent (you need to set time between the lookups)</td>
<td>E880 'rellatitude1' value is invalid</td>
</tr>
<tr>
<td>E620 The 'mmsid' is required</td>
<td>E881 'rellatitude2' value is invalid</td>
</tr>
<tr>
<td>E621 The 'to' is required</td>
<td>E882 'rellatitude3' value is invalid</td>
</tr>
<tr>
<td>E623 The 'to' field can contain up to 100 numbers</td>
<td>E883 'rellatitude4' value is invalid</td>
</tr>
<tr>
<td>E624 The 'tocampaign' is required</td>
<td>E884 'rellatitude5' value is invalid</td>
</tr>
<tr>
<td>E626 Content unavailable. Encoding in progress, try again later.</td>
<td>E885 'rellatitude6' value is invalid</td>
</tr>
<tr>
<td>E628 Operator Not supported</td>
<td>E886 'rellatitude7' value is invalid</td>
</tr>
<tr>
<td>E629 Unrecognized content type</td>
<td>E887 'rellatitude8' value is invalid</td>
</tr>
<tr>
<td>E630 The 'databaseid' is required</td>
<td>E888 'rellatitude9' value is invalid</td>
</tr>
<tr>
<td>E631 The 'barcodeid' is required</td>
<td>E889 'rellatitude10' value is invalid</td>
</tr>
<tr>
<td>E632 Invalid 'databaseid'</td>
<td>E890 'rellongitude1' value is invalid</td>
</tr>
<tr>
<td>E633 This MMS does not contain barcode object</td>
<td>E891 'rellongitude2' value is invalid</td>
</tr>
<tr>
<td>E640 The 'mmsinboxid' is required</td>
<td>E892 'rellongitude3' value is invalid</td>
</tr>
<tr>
<td>E641 Invalid MMS Inbox Message ID</td>
<td>E893 'rellongitude4' value is invalid</td>
</tr>
<tr>
<td>E642 MMS Inbox message has no content.</td>
<td>E894 'rellongitude5' value is invalid</td>
</tr>
<tr>
<td>E643 Could not clean up MMS Inbox message content.</td>
<td>E895 'rellongitude6' value is invalid</td>
</tr>
<tr>
<td>E712 The 'text' is required</td>
<td>E896 'rellongitude7' value is invalid</td>
</tr>
<tr>
<td>E713 There is billing problem on your account</td>
<td>E897 'rellongitude8' value is invalid</td>
</tr>
<tr>
<td>E714 Missing/Invalid 'campaignid'</td>
<td>E898 'rellongitude9' value is invalid</td>
</tr>
<tr>
<td>E715 Number is not subscribed to this campaign</td>
<td>E899 'rellongitude10' value is invalid</td>
</tr>
<tr>
<td>E801 'passtemplateid' is required.</td>
<td>E901 The 'mobile' is required</td>
</tr>
<tr>
<td>E802 Invalid 'passtemplateid'. Pass template is either deleted or do not belong to this user.</td>
<td>E902 The 'campaignid' is required</td>
</tr>
<tr>
<td>E803 'barcodevalue' is required.</td>
<td>E903 Invalid 'campaignid'</td>
</tr>
<tr>
<td>E804 'email' is invalid.</td>
<td>E904 Could not subscribe this number</td>
</tr>
<tr>
<td>E805 'Phone' is invalid.</td>
<td>E905 Could not unsubscribe this number</td></tr>
<tr>
<td>E806 'passdataid' was not created. Internal error occurred.</td>
<td>E911 The 'email' is required</td>
</tr>
<tr>
<td>E807 'passdataid' is required.</td>
<td>E912 Invalid 'campaignid'</td>
</tr>
<tr>
<td>E808 Invalid 'passdataid'. Pass is either deleted or does not belong to this user.</td>
<td>E913 Could not subscribe this 'email'</td>
</tr>
<tr>
<td>E809 Pass was not updated. Internal error occured.</td>
<td>E914 Could not unsubscribe this 'email'</td>
</tr>
<tr>
<td>E915 This 'email' previously opted out of this or other email campaigns owned by this account/user.</td>
<td>E916 Sending to this 'email' was previously a bounce-back.</td>
</tr>
<tr>
<td>E917 This 'email' has filed a SPAM complaint on one or more email campaigns owned by this account/user.</td>
<td>E918 This 'email' was previously opted out by this account/user.</td>
</tr>
</tbody>
</table>
