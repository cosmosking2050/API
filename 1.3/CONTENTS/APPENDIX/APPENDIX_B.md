<a href="/1.3/README.md">Back to the Table of Contents</a>&nbsp;&nbsp;|&nbsp;&nbsp;<a href="API_APPENDIX.md">Back to Appendix List</a>
<h2>APPENDIX B</h2>
<div class="text-2"><a id="appendix-b"></a><strong>Error/Notification/Protocol Code Reference</strong></div>
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
<td>E641 Invalid MMS Inbox ID</td>
<td>E893 'rellongitude4' value is invalid</td>
</tr>
<tr>
<td>E642 MMS Inbox content is empty.</td>
<td>E894 'rellongitude5' value is invalid</td>
</tr>
<tr>
<td>E643 Could not clean up MMS Inbox content.</td>
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
<p><strong>ii. Postback Notification Codes</strong></p>
<table class="toc" id="toc" style="font-size:11px;">
<tbody>
<tr>
<td>E001 - encoding of mobile video failed</td>
</tr>
<tr>
<td>E002 - encoding of MMS audio failed</td>
</tr>
<tr>
<td>E003 - encoding of MMS video failed</td>
</tr>
<tr>
<td>E012 - encoding of MMS audio failed</td>
</tr>
<tr>
<td>E013 - encoding of MMS video failed</td>
</tr>
<tr>
<td>E101 - Error occured. Impossible to send MMS</td>
</tr>
<tr>
<td>N003 - content was stored / encoded correctly</td>
</tr>
<tr>
<td>N013 - content was stored / encoded correctly and sending was triggered</td>
</tr>
<tr>
<td>N101 - when content sending started</td>
</tr>
<tr>
<td>N102 - when we get the Delivery report with either success or error</td>
</tr>
<tr>
<td>N201 - SMS Message Sent</td>
</tr>
<tr>
<td>N202 - SMS Sent/Delivered (or) SMS Sent/Failed</td>
</tr>
<tr>
<td>N211 - SMS MO received</td>
</tr>
<tr>
<td>N301 - number subscribed</td>
</tr>
<tr>
<td>N302 - number unsubscribed</td>
</tr>
<tr>
<td>N401 - MMS MO received successfuly</td>
</tr>
<tr>
<td>N801 - Pass was generated succesfully.</td>
</tr>
<tr>
<td>N802 - Some error occurred. Pass generation failed.</td>
</tr>
<tr>
<td>N803 - Maximum limit for pass generation reached.</td>
</tr>
<tr>
<td>N811 - User Account do not have enough credits to generate the pass.</td>
</tr>
</tbody>
</table>
<p><strong>iii. SMS Protocol Code Look Up</strong></p>
<table class="SMS-code-look-up" style="font-size:11px;">
<tbody>
<tr>
<th><strong>Protocol</strong></th>
<th><strong>Status</strong></th>
<th><strong>Success</strong></th>
<th class="nobrd"><strong>Notification Information</strong></th>
</tr>
<tr>
<td>1</td>
<td>92100</td>
<td>no</td>
<td>No Route</td>
</tr>
<tr>
<td>1</td>
<td>92101</td>
<td>no</td>
<td>No Credits</td>
</tr>
<tr>
<td>1</td>
<td>92102</td>
<td>no</td>
<td>Overspending</td>
</tr>
<tr>
<td>1</td>
<td>92110</td>
<td>no</td>
<td>No ProgramID</td>
</tr>
<tr>
<td>1</td>
<td>92111</td>
<td>no</td>
<td>TMobile Missing RefID</td>
</tr>
<tr>
<td>2</td>
<td>0</td>
<td>yes</td>
<td>Message sent</td>
</tr>
<tr>
<td>2</td>
<td>1</td>
<td>yes</td>
<td>Processing request</td>
</tr>
<tr>
<td>2</td>
<td>2</td>
<td>yes</td>
<td>Message queued</td>
</tr>
<tr>
<td>2</td>
<td>3</td>
<td>yes</td>
<td>Message buffered with carrier and waiting for delivery response</td>
</tr>
<tr>
<td>2</td>
<td>4</td>
<td>yes</td>
<td>Message delivered</td>
</tr>
<tr>
<td>2</td>
<td>5</td>
<td>yes</td>
<td>Message transferred to carrier and waiting for buffered response</td>
</tr>
<tr>
<td>2</td>
<td>301</td>
<td>no</td>
<td>Only one top level request element is permitted</td>
</tr>
<tr>
<td>2</td>
<td>303</td>
<td>no</td>
<td>The required version attribute of the request element was not found in the request</td>
</tr>
<tr>
<td>2</td>
<td>304</td>
<td>no</td>
<td>The required protocol attribute of the request element was not found in the request</td>
</tr>
<tr>
<td>2</td>
<td>306</td>
<td>no</td>
<td>The XML POST parameter cannot be empty</td>
</tr>
<tr>
<td>2</td>
<td>307</td>
<td>no</td>
<td>The request was an ill-formed XML document</td>
</tr>
<tr>
<td>2</td>
<td>310</td>
<td>no</td>
<td>If the force option is going to be set, it can only be set to one or zero</td>
</tr>
<tr>
<td>2</td>
<td>311</td>
<td>no</td>
<td>Method option is no longer used</td>
</tr>
<tr>
<td>2</td>
<td>321</td>
<td>no</td>
<td>Invalid request version</td>
</tr>
<tr>
<td>2</td>
<td>322</td>
<td>no</td>
<td>Invalid request protocol</td>
</tr>
<tr>
<td>2</td>
<td>323</td>
<td>no</td>
<td>Invalid request type</td>
</tr>
<tr>
<td>2</td>
<td>330</td>
<td>no</td>
<td>Invalid number of page elements</td>
</tr>
<tr>
<td>2</td>
<td>331</td>
<td>no</td>
<td>Client not found</td>
</tr>
<tr>
<td>2</td>
<td>337</td>
<td>no</td>
<td>Invalid carrier ID value</td>
</tr>
<tr>
<td>2</td>
<td>338</td>
<td>no</td>
<td>Message Service Id and destination carrier attributes cannot be used at same time</td>
</tr>
<tr>
<td>2</td>
<td>339</td>
<td>no</td>
<td>Invalid destination carrier ID value</td>
</tr>
<tr>
<td>2</td>
<td>340</td>
<td>no</td>
<td>Invalid source carrier ID value</td>
</tr>
<tr>
<td>2</td>
<td>341</td>
<td>no</td>
<td>Transaction failed; Carrier ID does not exist</td>
</tr>
<tr>
<td>2</td>
<td>342</td>
<td>no</td>
<td>A message service ID is required</td>
</tr>
<tr>
<td>2</td>
<td>343</td>
<td>no</td>
<td>The message service ID is discontinued</td>
</tr>
<tr>
<td>2</td>
<td>344</td>
<td>no</td>
<td>The message service ID is beta</td>
</tr>
<tr>
<td>2</td>
<td>345</td>
<td>no</td>
<td>Unable to determine carrier ID from destination address</td>
</tr>
<tr>
<td>2</td>
<td>349</td>
<td>no</td>
<td>Destination address contains non-numeric characters</td>
</tr>
<tr>
<td>2</td>
<td>350</td>
<td>no</td>
<td>A destination address is required</td>
</tr>
<tr>
<td>2</td>
<td>351</td>
<td>no</td>
<td>Transaction failed: Invalid destination address value</td>
</tr>
<tr>
<td>2</td>
<td>352</td>
<td>no</td>
<td>Invalid destination address country code</td>
</tr>
<tr>
<td>2</td>
<td>353</td>
<td>no</td>
<td>Message text or data is required</td>
</tr>
<tr>
<td>2</td>
<td>354</td>
<td>no</td>
<td>Message text is not long enough</td>
</tr>
<tr>
<td>2</td>
<td>355</td>
<td>no</td>
<td>Message text is too long</td>
</tr>
<tr>
<td>2</td>
<td>356</td>
<td>no</td>
<td>Message from is required</td>
</tr>
<tr>
<td>2</td>
<td>357</td>
<td>no</td>
<td>Message from is not long enough</td>
</tr>
<tr>
<td>2</td>
<td>358</td>
<td>no</td>
<td>Message from is too long</td>
</tr>
<tr>
<td>2</td>
<td>359</td>
<td>no</td>
<td>Message callback is required</td>
</tr>
<tr>
<td>2</td>
<td>360</td>
<td>no</td>
<td>Message callback is not long enough</td>
</tr>
<tr>
<td>2</td>
<td>361</td>
<td>no</td>
<td>Message callback is too long</td>
</tr>
<tr>
<td>2</td>
<td>362</td>
<td>no</td>
<td>Message callback contains non-numeric characters</td>
</tr>
<tr>
<td>2</td>
<td>363</td>
<td>no</td>
<td>Invalid callback number used</td>
</tr>
<tr>
<td>2</td>
<td>364</td>
<td>no</td>
<td>Callback and destination address cannot be identical</td>
</tr>
<tr>
<td>2</td>
<td>365</td>
<td>no</td>
<td>Strict international addressing is enforced, please use a + sign, country code, and national number</td>
</tr>
<tr>
<td>2</td>
<td>366</td>
<td>no</td>
<td>Invalid message length control option</td>
</tr>
<tr>
<td>2</td>
<td>367</td>
<td>no</td>
<td>Invalid source TON value</td>
</tr>
<tr>
<td>2</td>
<td>368</td>
<td>no</td>
<td>Invalid source address value</td>
</tr>
<tr>
<td>2</td>
<td>369</td>
<td>no</td>
<td>Account not permitted to use an alphanumeric source address</td>
</tr>
<tr>
<td>2</td>
<td>370</td>
<td>no</td>
<td>Account not permitted to use a short code source address</td>
</tr>
<tr>
<td>2</td>
<td>371</td>
<td>no</td>
<td>Callback attribute and source element cannot be used at same time</td>
</tr>
<tr>
<td>2</td>
<td>372</td>
<td>no</td>
<td>Pin attribute and destination element cannot be used at same time</td>
</tr>
<tr>
<td>2</td>
<td>373</td>
<td>no</td>
<td>Invalid destination TON value</td>
</tr>
<tr>
<td>2</td>
<td>374</td>
<td>no</td>
<td>Preview lookup request failed</td>
</tr>
<tr>
<td>2</td>
<td>375</td>
<td>no</td>
<td>Source address denied</td>
</tr>
<tr>
<td>2</td>
<td>376</td>
<td>no</td>
<td>Account not permitted to use premium billing options</td>
</tr>
<tr>
<td>2</td>
<td>377</td>
<td>no</td>
<td>Invalid premium billing charge type</td>
</tr>
<tr>
<td>2</td>
<td>378</td>
<td>no</td>
<td>Invalid premium billing charge amount</td>
</tr>
<tr>
<td>2</td>
<td>379</td>
<td>no</td>
<td>Invalid user data header</td>
</tr>
<tr>
<td>2</td>
<td>380</td>
<td>no</td>
<td>Invalid data coding scheme</td>
</tr>
<tr>
<td>2</td>
<td>381</td>
<td>no</td>
<td>Invalid characters used with selected data coding scheme</td>
</tr>
<tr>
<td>2</td>
<td>382</td>
<td>no</td>
<td>Invalid source or destination port</td>
</tr>
<tr>
<td>2</td>
<td>383</td>
<td>no</td>
<td>Message data and text attributes cannot be used at same time</td>
</tr>
<tr>
<td>2</td>
<td>384</td>
<td>no</td>
<td>Invalid message data</td>
</tr>
<tr>
<td>2</td>
<td>385</td>
<td>no</td>
<td>Invalid or unsupported ringtone format</td>
</tr>
<tr>
<td>2</td>
<td>386</td>
<td>no</td>
<td>Invalid or unsupported image format</td>
</tr>
<tr>
<td>2</td>
<td>387</td>
<td>no</td>
<td>Must provide a valid phone type to send images or ringtones</td>
</tr>
<tr>
<td>2</td>
<td>388</td>
<td>no</td>
<td>Binary messaging is not supported for this carrier</td>
</tr>
<tr>
<td>2</td>
<td>389</td>
<td>no</td>
<td>A valid image type must be specified</td>
</tr>
<tr>
<td>2</td>
<td>390</td>
<td>no</td>
<td>Must provide a numeric country and network code</td>
</tr>
<tr>
<td>2</td>
<td>391</td>
<td>no</td>
<td>Must provide ringtone data</td>
</tr>
<tr>
<td>2</td>
<td>392</td>
<td>no</td>
<td>Must provide image data</td>
</tr>
<tr>
<td>2</td>
<td>393</td>
<td>no</td>
<td>Must provide at least a screen saver or a ringtone to send a profile</td>
</tr>
<tr>
<td>2</td>
<td>394</td>
<td>no</td>
<td>Invalid option type for the phone specified</td>
</tr>
<tr>
<td>2</td>
<td>395</td>
<td>no</td>
<td>Must provide a country code and a network code to send a logo</td>
</tr>
<tr>
<td>2</td>
<td>396</td>
<td>no</td>
<td>Smart messages cannot use more than 3 messages to transfer</td>
</tr>
<tr>
<td>2</td>
<td>397</td>
<td>no</td>
<td>WAP Pushes require the optional URL parameter to be included</td>
</tr>
<tr>
<td>2</td>
<td>398</td>
<td>no</td>
<td>WAP Pushes not supported for this type of carrier</td>
</tr>
<tr>
<td>2</td>
<td>399</td>
<td>no</td>
<td>Binary data with a User Data Header is not allowed for your account</td>
</tr>
<tr>
<td>2</td>
<td>400</td>
<td>no</td>
<td>General error occurred while delivering the message to the<br />
carrier</td>
</tr>
<tr>
<td>2</td>
<td>401</td>
<td>no</td>
<td>General error occurred while delivering the message to the<br />
carrier</td>
</tr>
<tr>
<td>2</td>
<td>410</td>
<td>no</td>
<td>Message recipient not found on carrier</td>
</tr>
<tr>
<td>2</td>
<td>411</td>
<td>no</td>
<td>Message recipient not found on carrier</td>
</tr>
<tr>
<td>2</td>
<td>420</td>
<td>no</td>
<td>Invalid subscriber ID or subscriber password</td>
</tr>
<tr>
<td>2</td>
<td>430</td>
<td>no</td>
<td>Demo or commercial access is required</td>
</tr>
<tr>
<td>2</td>
<td>431</td>
<td>no</td>
<td>Invalid Subscriber ID</td>
</tr>
<tr>
<td>2</td>
<td>432</td>
<td>no</td>
<td>Account access permanently blocked</td>
</tr>
<tr>
<td>2</td>
<td>433</td>
<td>no</td>
<td>Account access denied</td>
</tr>
<tr>
<td>2</td>
<td>434</td>
<td>no</td>
<td>Account access has expired</td>
</tr>
<tr>
<td>2</td>
<td>451</td>
<td>no</td>
<td>Account mobile originated deliver profile incorrectly setup</td>
</tr>
<tr>
<td>2</td>
<td>460</td>
<td>no</td>
<td>Account entry not found in billing database</td>
</tr>
<tr>
<td>2</td>
<td>461</td>
<td>no</td>
<td>Must include source address if premium billing requested</td>
</tr>
<tr>
<td>2</td>
<td>507</td>
<td>no</td>
<td>Carrier facility not supported</td>
</tr>
<tr>
<td>2</td>
<td>508</td>
<td>no</td>
<td>Carrier absent subscriber</td>
</tr>
<tr>
<td>2</td>
<td>509</td>
<td>no</td>
<td>Carrier delivery failed</td>
</tr>
<tr>
<td>2</td>
<td>510</td>
<td>no</td>
<td>Carrier protocol error</td>
</tr>
<tr>
<td>2</td>
<td>511</td>
<td>no</td>
<td>Carrier MS not equipped</td>
</tr>
<tr>
<td>2</td>
<td>512</td>
<td>no</td>
<td>Carrier unknown SC</td>
</tr>
<tr>
<td>2</td>
<td>513</td>
<td>no</td>
<td>Carrier illegal MS</td>
</tr>
<tr>
<td>2</td>
<td>514</td>
<td>no</td>
<td>Carrier MS not a subscriber</td>
</tr>
<tr>
<td>2</td>
<td>560</td>
<td>no</td>
<td>Message recipient not authorized by carrier to receive the<br />
message</td>
</tr>
<tr>
<td>2</td>
<td>561</td>
<td>no</td>
<td>Content blocked by carrier</td>
</tr>
<tr>
<td>2</td>
<td>562</td>
<td>no</td>
<td>Short code not active</td>
</tr>
<tr>
<td>2</td>
<td>563</td>
<td>no</td>
<td>Short code expired</td>
</tr>
<tr>
<td>2</td>
<td>564</td>
<td>no</td>
<td>Short code blocked</td>
</tr>
<tr>
<td>2</td>
<td>565</td>
<td>no</td>
<td>Reseller address blocked by carrier</td>
</tr>
<tr>
<td>2</td>
<td>566</td>
<td>no</td>
<td>Destination address blocked by carrier</td>
</tr>
<tr>
<td>2</td>
<td>568</td>
<td>no</td>
<td>Destination address not provisioned for SMS</td>
</tr>
<tr>
<td>2</td>
<td>569</td>
<td>no</td>
<td>Destination address suspended by carrier</td>
</tr>
<tr>
<td>2</td>
<td>570</td>
<td>no</td>
<td>Invalid charge amount: charge amount not allowed for charge type</td>
</tr>
<tr>
<td>2</td>
<td>571</td>
<td>no</td>
<td>Campaign rejected by carrier</td>
</tr>
<tr>
<td>2</td>
<td>572</td>
<td>no</td>
<td>Campaign information is not provisioned for this carrier or is not active</td>
</tr>
<tr>
<td>2</td>
<td>800</td>
<td>no</td>
<td>Invalid number of service elements in request</td>
</tr>
<tr>
<td>2</td>
<td>801</td>
<td>no</td>
<td>General error while retrieving the service list</td>
</tr>
<tr>
<td>2</td>
<td>802</td>
<td>no</td>
<td>Service ID is required</td>
</tr>
<tr>
<td>2</td>
<td>803</td>
<td>no</td>
<td>Invalid service ID since it was null</td>
</tr>
<tr>
<td>2</td>
<td>810</td>
<td>no</td>
<td>Failed message delivery</td>
</tr>
<tr>
<td>2</td>
<td>811</td>
<td>no</td>
<td>Message Delivery Error: Message expired by carrier</td>
</tr>
<tr>
<td>2</td>
<td>815</td>
<td>no</td>
<td>Message Delivery Error - Message submitted to but not acknowledged by carrier</td>
</tr>
<tr>
<td>2</td>
<td>1000</td>
<td>no</td>
<td>System error: General error occured while processing request</td>
</tr>
<tr>
<td>2</td>
<td>1001</td>
<td>no</td>
<td>System error: Duplicate Ticket ID</td>
</tr>
<tr>
<td>2</td>
<td>1010</td>
<td>no</td>
<td>Temporary system error</td>
</tr>
<tr>
<td>2</td>
<td>1020</td>
<td>no</td>
<td>Temporary external system error</td>
</tr>
<tr>
<td>2</td>
<td>1030</td>
<td>no</td>
<td>External system error</td>
</tr>
<tr>
<td>2</td>
<td>2001</td>
<td>no</td>
<td>Invalid subscription authentication</td>
</tr>
<tr>
<td>2</td>
<td>2002</td>
<td>no</td>
<td>Subscriber/account ID has been de-activated</td>
</tr>
<tr>
<td>2</td>
<td>2003</td>
<td>no</td>
<td>Subscriber/account ID has been deleted</td>
</tr>
<tr>
<td>2</td>
<td>2010</td>
<td>no</td>
<td>General billing error</td>
</tr>
<tr>
<td>2</td>
<td>2011</td>
<td>no</td>
<td>Transaction failed: Message delivery expired, no charge was made</td>
</tr>
<tr>
<td>2</td>
<td>2012</td>
<td>no</td>
<td>Transaction failed: Consumer canceled the transaction</td>
</tr>
<tr>
<td>2</td>
<td>2013</td>
<td>no</td>
<td>Message still in process</td>
</tr>
<tr>
<td>2</td>
<td>2014</td>
<td>no</td>
<td>Transaction failed: Wireless subscriber is ineligible for billing on carrier</td>
</tr>
<tr>
<td>2</td>
<td>2015</td>
<td>no</td>
<td>Transaction failed: Wireless subscriber's account is deactivated</td>
</tr>
<tr>
<td>2</td>
<td>2016</td>
<td>no</td>
<td>Unspecified error</td>
</tr>
<tr>
<td>2</td>
<td>2017</td>
<td>no</td>
<td>Message has been deleted by carrier</td>
</tr>
<tr>
<td>2</td>
<td>2018</td>
<td>no</td>
<td>Subscriber payment method is invalid</td>
</tr>
<tr>
<td>2</td>
<td>2019</td>
<td>no</td>
<td>Undeliverable to user</td>
</tr>
<tr>
<td>2</td>
<td>2020</td>
<td>no</td>
<td>Transaction failed: Wireless subscriber over spending limit</td>
</tr>
<tr>
<td>2</td>
<td>2021</td>
<td>no</td>
<td>Service not available for user</td>
</tr>
<tr>
<td>2</td>
<td>2022</td>
<td>no</td>
<td>Transaction failed: Wireless subscriber not eligible for premium billing: Subscriber setting</td>
</tr>
<tr>
<td>2</td>
<td>2023</td>
<td>no</td>
<td>User not found on carrier network</td>
</tr>
<tr>
<td>2</td>
<td>2024</td>
<td>no</td>
<td>Transaction failed: Wireless subscriber's account closed, suspended or locked.</td>
</tr>
<tr>
<td>2</td>
<td>2025</td>
<td>no</td>
<td>Transaction failed: Carrier does not support premium billing with the supplied short code</td>
</tr>
<tr>
<td>2</td>
<td>2026</td>
<td>no</td>
<td>Transaction failed: Ineligible product</td>
</tr>
<tr>
<td>2</td>
<td>2027</td>
<td>no</td>
<td>Transaction failed: Wireless network operator temporary system<br />
error</td>
</tr>
<tr>
<td>2</td>
<td>2028</td>
<td>no</td>
<td>Wireless subscriber has run out of prepaid credits</td>
</tr>
<tr>
<td>2</td>
<td>2029</td>
<td>no</td>
<td>Wireless subscriber not eligible for premium billing: blocked MDN</td>
</tr>
<tr>
<td>2</td>
<td>2030</td>
<td>no</td>
<td>Transaction failed: Wireless subscriber not eligible for premium<br />
billing: Reseller</td>
</tr>
<tr>
<td>2</td>
<td>2031</td>
<td>no</td>
<td>Short code is currently in test mode, only whitelisted handsets are permitted</td>
</tr>
<tr>
<td>2</td>
<td>2032</td>
<td>no</td>
<td>Short code is not certified on carrier</td>
</tr>
<tr>
<td>2</td>
<td>2033</td>
<td>no</td>
<td>Short code not permitted for this carrier</td>
</tr>
<tr>
<td>2</td>
<td>2034</td>
<td>no</td>
<td>Short code and price point combination is not allowed for this carrier</td>
</tr>
<tr>
<td>2</td>
<td>2035</td>
<td>no</td>
<td>Transaction failed: Wireless subscriber not found</td>
</tr>
<tr>
<td>2</td>
<td>2036</td>
<td>no</td>
<td>Tax failed on transaction</td>
</tr>
<tr>
<td>2</td>
<td>2037</td>
<td>no</td>
<td>Transaction failed: Does not meet minimum charge amount</td>
</tr>
<tr>
<td>2</td>
<td>2038</td>
<td>no</td>
<td>Transaction failed: Amount exceeds specified maximum</td>
</tr>
<tr>
<td>2</td>
<td>2039</td>
<td>no</td>
<td>Advice-of-Charge Timed Out</td>
</tr>
<tr>
<td>2</td>
<td>2040</td>
<td>no</td>
<td>Transaction failed: Charge duration exceeded</td>
</tr>
<tr>
<td>2</td>
<td>2041</td>
<td>no</td>
<td>Transaction failed: Unable to process request; previous billing request still being processed; Advice-of-Charge re-sent</td>
</tr>
<tr>
<td>2</td>
<td>2042</td>
<td>no</td>
<td>Refund denied: Transaction already refunded</td>
</tr>
<tr>
<td>2</td>
<td>2043</td>
<td>no</td>
<td>Request Failed: No transaction found matching provided data</td>
</tr>
<tr>
<td>2</td>
<td>2044</td>
<td>no</td>
<td>Invalid URL</td>
</tr>
<tr>
<td>2</td>
<td>2045</td>
<td>no</td>
<td>Carrier not supported</td>
</tr>
<tr>
<td>2</td>
<td>2046</td>
<td>no</td>
<td>Invalid sessionId</td>
</tr>
<tr>
<td>2</td>
<td>2047</td>
<td>no</td>
<td>Invalid ticketid</td>
</tr>
<tr>
<td>2</td>
<td>2048</td>
<td>no</td>
<td>Validation Error</td>
</tr>
<tr>
<td>2</td>
<td>2049</td>
<td>no</td>
<td>Transaction failed: Request with no associated charge; failed by<br />
OpenMarket</td>
</tr>
<tr>
<td>2</td>
<td>2050</td>
<td>no</td>
<td>Transaction failed: The transaction has been denied by the<br />
carrier's billing system</td>
</tr>
<tr>
<td>2</td>
<td>2051</td>
<td>no</td>
<td>Supplied ticketId is either in a processed state or failed state</td>
</tr>
<tr>
<td>2</td>
<td>2052</td>
<td>no</td>
<td>Transaction failed: Campaign information is not provisioned for this carrier or is not active</td>
</tr>
<tr>
<td>2</td>
<td>2053</td>
<td>no</td>
<td>Transaction failed: Advice of charge message exceeded maximum length</td>
</tr>
<tr>
<td>2</td>
<td>2054</td>
<td>no</td>
<td>Transaction failed:  Wireless subscriber?s account closed</td>
</tr>
<tr>
<td>2</td>
<td>2056</td>
<td>no</td>
<td>Transaction failed: Campaign rejected by carrier</td>
</tr>
<tr>
<td>2</td>
<td>2100</td>
<td>no</td>
<td>Invalid request-&lt;request parameter&gt; is missing</td>
</tr>
<tr>
<td>2</td>
<td>2101</td>
<td>no</td>
<td>Account is not authorized</td>
</tr>
<tr>
<td>2</td>
<td>2102</td>
<td>no</td>
<td>Account is not authorized to use short code</td>
</tr>
<tr>
<td>2</td>
<td>2104</td>
<td>no</td>
<td>Transaction failed: Refund cannot be processed against a failed charge</td>
</tr>
<tr>
<td>2</td>
<td>2120</td>
<td>no</td>
<td>Account does not have permission to refund the charge</td>
</tr>
<tr>
<td>2</td>
<td>2121</td>
<td>no</td>
<td>Refund cannot exceed the original transaction amount</td>
</tr>
<tr>
<td>2</td>
<td>2122</td>
<td>no</td>
<td>ProgramId is a required field for this carrier</td>
</tr>
<tr>
<td>2</td>
<td>2123</td>
<td>no</td>
<td>The carrier does not support refunds to be processed</td>
</tr>
<tr>
<td>2</td>
<td>2124</td>
<td>no</td>
<td>The carrier does not support partial refunds</td>
</tr>
<tr>
<td>2</td>
<td>2125</td>
<td>no</td>
<td>Refund cannot be processed as it exceeds the allowable time period since the charge</td>
</tr>
<tr>
<td>2</td>
<td>2126</td>
<td>no</td>
<td>Carrier information cannot be found from the WAP header</td>
</tr>
<tr>
<td>2</td>
<td>3041</td>
<td>no</td>
<td>Standard rate message blocked by the OpenMarket deactivated numbers firewall</td>
</tr>
<tr>
<td>2</td>
<td>3042</td>
<td>no</td>
<td>Premium rate message blocked by the OpenMarket deactivated numbers firewall</td>
</tr>
<tr>
<td>2</td>
<td>4000</td>
<td>no</td>
<td>Transaction failed: Merchant account not permitted to use the<br />
subscription service</td>
</tr>
<tr>
<td>2</td>
<td>4001</td>
<td>no</td>
<td>Short code is not provisioned to use the subscription service<br />
for this carrier</td>
</tr>
<tr>
<td>2</td>
<td>4010</td>
<td>no</td>
<td>Transaction failed: Subscription already exists</td>
</tr>
<tr>
<td>2</td>
<td>4011</td>
<td>no</td>
<td>Transaction failed: Unable to process request; previous billing request still being processed</td>
</tr>
<tr>
<td>2</td>
<td>4012</td>
<td>no</td>
<td>Transaction failed: Subscription already exists on carrier; possible phone number change</td>
</tr>
<tr>
<td>2</td>
<td>4013</td>
<td>no</td>
<td>Transaction failed: Unable to process request; previous billing request is pending consumer response</td>
</tr>
<tr>
<td>2</td>
<td>4020</td>
<td>no</td>
<td>Transaction failed: Subscription not found</td>
</tr>
<tr>
<td>2</td>
<td>4021</td>
<td>no</td>
<td>Transaction failed: Subscription already expired</td>
</tr>
<tr>
<td>2</td>
<td>4030</td>
<td>no</td>
<td>Renewal error: subscription already billed for this period</td>
</tr>
<tr>
<td>2</td>
<td>4031</td>
<td>no</td>
<td>Renewal error: Subscription renewal status cannot be determined</td>
</tr>
<tr>
<td>2</td>
<td>4032</td>
<td>no</td>
<td>Renewal error: Subscription already expired</td>
</tr>
<tr>
<td>2</td>
<td>4033</td>
<td>no</td>
<td>Subscription successfully cancelled, message delivery failed.</td>
</tr>
<tr>
<td>2</td>
<td>4035</td>
<td>no</td>
<td>Renewal Error: Subscription renewal failed by carrier</td>
</tr>
<tr>
<td>2</td>
<td>4050</td>
<td>no</td>
<td>Conclude error: subscription already concluded.</td>
</tr>
<tr>
<td>2</td>
<td>4051</td>
<td>no</td>
<td>Conclude error: Subscription cannot be concluded while in indeterminate state.</td>
</tr>
<tr>
<td>2</td>
<td>4052</td>
<td>no</td>
<td>Transaction failed: Received notification of account deactivation; failed by OpenMarket</td>
</tr>
<tr>
<td>2</td>
<td>4054</td>
<td>no</td>
<td>Renewal error: Subscription already revoked</td>
</tr>
<tr>
<td>2</td>
<td>4055</td>
<td>no</td>
<td>Conclude error: Subscription cannot be concluded while a renewal is pending</td>
</tr>
<tr>
<td>3</td>
<td>1</td>
<td>yes</td>
<td>delivery success</td>
</tr>
<tr>
<td>3</td>
<td>2</td>
<td>no</td>
<td>delivery failure</td>
</tr>
<tr>
<td>3</td>
<td>4</td>
<td>yes</td>
<td>msg buffered</td>
</tr>
<tr>
<td>3</td>
<td>8</td>
<td>yes</td>
<td>smsc submit</td>
</tr>
<tr>
<td>3</td>
<td>16</td>
<td>no</td>
<td>smsc reject (error)</td>
</tr>
<tr>
<td>4</td>
<td>0</td>
<td>yes</td>
<td>Successfully executed</td>
</tr>
<tr>
<td>4</td>
<td>1</td>
<td>no</td>
<td>Invalid login or un-authorized API usage</td>
</tr>
<tr>
<td>4</td>
<td>2</td>
<td>no</td>
<td>Consumer is blocked by IPX</td>
</tr>
<tr>
<td>4</td>
<td>3</td>
<td>no</td>
<td>Operation is not provisioned by IPX</td>
</tr>
<tr>
<td>4</td>
<td>4</td>
<td>no</td>
<td>The consumer is unknown to IPX</td>
</tr>
<tr>
<td>4</td>
<td>5</td>
<td>no</td>
<td>Consumer has blocked this service in IPX</td>
</tr>
<tr>
<td>4</td>
<td>6</td>
<td>no</td>
<td>The originating address is not supported</td>
</tr>
<tr>
<td>4</td>
<td>7</td>
<td>no</td>
<td>Alpha originating address not supported by account</td>
</tr>
<tr>
<td>4</td>
<td>8</td>
<td>no</td>
<td>MSISDN originating address not supported by account</td>
</tr>
<tr>
<td>4</td>
<td>9</td>
<td>no</td>
<td>GSM extended not supported by account</td>
</tr>
<tr>
<td>4</td>
<td>10</td>
<td>no</td>
<td>Unicode not supported by account</td>
</tr>
<tr>
<td>4</td>
<td>11</td>
<td>no</td>
<td>Status report not supported by account</td>
</tr>
<tr>
<td>4</td>
<td>12</td>
<td>no</td>
<td>Required capability not supported</td>
</tr>
<tr>
<td>4</td>
<td>13</td>
<td>no</td>
<td>Could not route message</td>
</tr>
<tr>
<td>4</td>
<td>14</td>
<td>no</td>
<td>The content provider max throttling rate is exceeded</td>
</tr>
<tr>
<td>4</td>
<td>15</td>
<td>no</td>
<td>The account max throttling rate is exceeded</td>
</tr>
<tr>
<td>4</td>
<td>16</td>
<td>no</td>
<td>Protocol ID not supported by account</td>
</tr>
<tr>
<td>4</td>
<td>50</td>
<td>no</td>
<td>Partial success: (&lt;1&gt;;&lt;2&gt;;&lt;n&gt;)</td>
</tr>
<tr>
<td>4</td>
<td>99</td>
<td>no</td>
<td>Internal server error</td>
</tr>
<tr>
<td>4</td>
<td>100</td>
<td>no</td>
<td>Invalid destination address</td>
</tr>
<tr>
<td>4</td>
<td>101</td>
<td>no</td>
<td>Invalid tariff class (price)</td>
</tr>
<tr>
<td>4</td>
<td>102</td>
<td>no</td>
<td>Invalid referenced (linked) ID</td>
</tr>
<tr>
<td>4</td>
<td>103</td>
<td>no</td>
<td>Invalid account name</td>
</tr>
<tr>
<td>4</td>
<td>104</td>
<td>no</td>
<td>Invalid content category</td>
</tr>
<tr>
<td>4</td>
<td>105</td>
<td>no</td>
<td>Invalid content meta data</td>
</tr>
<tr>
<td>4</td>
<td>106</td>
<td>no</td>
<td>Invalid originating address</td>
</tr>
<tr>
<td>4</td>
<td>107</td>
<td>no</td>
<td>Invalid alphanumeric originating address</td>
</tr>
<tr>
<td>4</td>
<td>108</td>
<td>no</td>
<td>Invalid validity time</td>
</tr>
<tr>
<td>4</td>
<td>109</td>
<td>no</td>
<td>Invalid delivery time</td>
</tr>
<tr>
<td>4</td>
<td>110</td>
<td>no</td>
<td>Invalid message content/user data</td>
</tr>
<tr>
<td>4</td>
<td>111</td>
<td>no</td>
<td>Invalid message length</td>
</tr>
<tr>
<td>4</td>
<td>112</td>
<td>no</td>
<td>Invalid user data header</td>
</tr>
<tr>
<td>4</td>
<td>113</td>
<td>no</td>
<td>Invalid data coding scheme</td>
</tr>
<tr>
<td>4</td>
<td>114</td>
<td>no</td>
<td>Invalid protocol ID</td>
</tr>
<tr>
<td>4</td>
<td>115</td>
<td>no</td>
<td>Invalid status report flags</td>
</tr>
<tr>
<td>4</td>
<td>116</td>
<td>no</td>
<td>Invalid TON</td>
</tr>
<tr>
<td>4</td>
<td>117</td>
<td>no</td>
<td>Invalid VAT</td>
</tr>
<tr>
<td>4</td>
<td>200</td>
<td>no</td>
<td>Operator integration error</td>
</tr>
<tr>
<td>4</td>
<td>201</td>
<td>no</td>
<td>Communication problems</td>
</tr>
<tr>
<td>4</td>
<td>202</td>
<td>no</td>
<td>Read timeout</td>
</tr>
<tr>
<td>4</td>
<td>299</td>
<td>no</td>
<td>Integration error</td>
</tr>
</tbody>
</table>
