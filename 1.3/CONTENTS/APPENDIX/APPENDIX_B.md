[Back to the Table of Contents](/1.3/README.md)

## APPENDIX B

__Error Code Reference__

| Code | Description |
| -------- | ----------- |
| E100 | Invalid request. Make a valid request via GET/POST/XML with all the required variables. |
| E104 | User Authentication Failed. |
| E105 | This account has no API rights. |
| E106 | You can call API every X seconds. |
| E107 | This account has no rights to use this action. |
| E108 | XML Parse error: $error. |
| E109 | API not activated. |
| E110 | Invalid receiver number. |
| E111 | Invalid shortcode. |
| E112 | IP was not whitelisted. API call rejected. |
| E113 | Set throughput exceeded for this API action. API call rejected. |
| E114 | Phone number is blacklisted. API call rejected. |
| E120 | Account has reached the API request limit. |
| E150 | The 'newuser' is required. |
| E151 | 'newuser' already exists. |
| E152 | The 'newpass' is required. |
| E153 | User was not created. Internal error occurred. |
| E154 | User was not created. Internal error occurred. |
| E170 | 'campaignname' is required. |
| E171 | 'brandname' is required. |
| E172 | Campaign was not created. Internal error occured. Please try again later. |
| E173 | 'mailingaddress' is required. |
| E212 | pagenumber is invalid. (RESERVED)|
| E213 | itemsperpage is invalid. (RESERVED) |
| E214 | startdate is invalid. (RESERVED) |
| E223 | More than one object is not allowed in the same slide. |
| E224 | MMS audio/video/image are not allowed with object in the same slide. |
| E225 | Too many Slides. |
| E226 | Audio and Video not allowed in same slide. |
| E227 | Video and Image not allowed in same slide. |
| E228 | Text more than X characters. |
| E229 | Content not allowed. |
| E230 | Bad X slide duration. |
| E241 | This content does not exist. |
| E311 | The 'name' is required. |
| E312 | No slides. |
| E313 | Slide X is empty. |
| E314 | The 'subject' is required. |
| E331 | Image in slide X is too big. |
| E332 | Audio in slide X is too big. |
| E333 | Video in slide X is too big. |
| E334 | Text in slide X is too long. |
| E335 | vCard in slide X is too big. |
| E336 | iCal in slide X is too big. |
| E337 | PDF in slide X is too big. |
| E338 | Passbook file in slide X is too big. |
| E341 | Image file in slide X is corrupted. |
| E343 | Video in slide X has missing codecs
| E351 | Could not copy Image in slide X. |
| E352 | Could not copy Audio in slide X. |
| E353 | Could not copy Video in slide X. |
| E355 | Could not copy vCard in slide X. |
| E356 | Could not copy iCal in slide X. |
| E357 | Could not copy PDF in slide X. |
| E358 | Could not copy Passbook file in slide X. |
| E400 | No Email Templates were created in this account. |
| E402 | Invalid 'emailid' (or) 'emailtemplateid'. |
| E403 | Could not send email due to missing dataset entry. |
| E404 | No Email Campaigns were created in this account. |
| E405 | No MMS Campaigns were created in this account. |
| E406 | Invalid email. |
| E503 | Internal error. |
| E506 | 'start_date'/'end_date' is required. |
| E507 | Invalid 'start_date'/'end_date' format. |
| E508 | Invalid 'start_date'/'end_date' format. |
| E509 | Lookup period is too long. |
| E510 | Lookup too frequent (you need to set time between the lookups). |
| E620 | The 'mmsid' is required. |
| E621 | The 'to' is required. |
| E622 | The 'fallback_sms_text' is required. |
| E623 | The 'to' field can contain up to 100 numbers. |
| E624 | The 'tocampaign' is required. |
| E625 | The 'mmsid' provided was invalid. |
| E626 | Content unavailable. Encoding in progress, try again later. |
| E627 | Invalid serviceid / serviceid is required |
| E628 | Operator Not supported. |
| E629 | Unrecognized content type. |
| E630 | The 'databaseid' is required. |
| E631 | The 'barcodeid' is required. |
| E632 | Invalid 'databaseid'. |
| E633 | This MMS does not contain barcode object. |
| E640 | The 'mmsinboxid' is required. |
| E641 | Invalid MMS Inbox Message ID. |
| E642 | MMS Inbox message has no content. |
| E643 | Could not clean up MMS Inbox message content. |
| E650 | The 'operator id' is required. |
| E651 | The 'operator id' passed was not found on our system. |
| E712 | The 'text' is required. |
| E713 | There is billing problem on your account. |
| E714 | Missing/Invalid 'campaignid'. |
| E715 | Number is not subscribed to this campaign. |
| E801 | 'passtemplateid' is required. |
| E802 | Invalid 'passtemplateid'. Pass template is either deleted or do not belong to this user. |
| E803 | 'barcodevalue' is required. |
| E804 | 'email' is invalid. |
| E805 | 'Phone' is invalid. |
| E806 | 'passdataid' was not created. Internal error occurred. |
| E807 | 'passdataid' is required. |
| E808 | Invalid 'passdataid'. Pass is either deleted or does not belong to this user. |
| E809 | Pass was not updated. Internal error occured. |
| E821 | Pass was not deleted. Internal error occured. |
| E822 | There is no pass found in this MMS Template to send. |
| E823 | There is no pass found in this email template to send. |
| E824 | Invalid call to the API. There is no pass data supplied. |
| E827 | Invalid request. 'mmsid' or 'emailtemplateid' or 'passtemplateid' is required. |
| E828 | Invalid request. You can request only by 'mmsid' or 'emailtemplateid' or 'passtemplateid' and not more than one. |
| E829 | 'custom identifier value' is invalid. Only Alphabet, Numbers or a Space is allowed. |
| E830 | Pass was not generated. Internal error occured. |
| E831 | Pass was not generated. It reached its download limit. |
| E833 | This Pass Template is set to send Personalized Passes. At least 'email' or 'phone' or 'custom identifier' is required with the Pass Data. |
| E840 | 'headerlabel1' is not accepted. It has to be set as Dynamic in the Pass Template. |
| E841 | 'headervalue1' is not accepted. It has to be set as Dynamic in the Pass Template. |
| E842 | 'primarylabel1' is not accepted. It has to be set as Dynamic in the Pass Template. |
| E843 | 'primaryvalue1' is not accepted. It has to be set as Dynamic in the Pass Template. |
| E844 | 'primarylabel2' is not accepted. It has to be set as Dynamic in the Pass Template. |
| E845 | 'primaryvalue2' is not accepted. It has to be set as Dynamic in the Pass Template. |
| E846 | 'seclabel1' is not accepted. It has to be set as Dynamic in the Pass Template. |
| E847 | 'secvalue1' is not accepted. It has to be set as Dynamic in the Pass Template. |
| E848 | 'seclabel2' is not accepted. It has to be set as Dynamic in the Pass Template. |
| E849 | 'secvalue2' is not accepted. It has to be set as Dynamic in the Pass Template. |
| E850 | 'seclabel3' is not accepted. It has to be set as Dynamic in the Pass Template. |
| E851 | 'secvalue3' is not accepted. It has to be set as Dynamic in the Pass Template. |
| E852 | 'seclabel4' is not accepted. It has to be set as Dynamic in the Pass Template. |
| E853 | 'secvalue4' is not accepted. It has to be set as Dynamic in the Pass Template. |
| E854 | 'auxlabel1' is not accepted. It has to be set as Dynamic in the Pass Template. |
| E855 | 'auxvalue1' is not accepted. It has to be set as Dynamic in the Pass Template. |
| E856 | 'auxlabel2' is not accepted. It has to be set as Dynamic in the Pass Template. |
| E857 | 'auxvalue2' is not accepted. It has to be set as Dynamic in the Pass Template. |
| E858 | 'auxlabel3' is not accepted. It has to be set as Dynamic in the Pass Template. |
| E859 | 'auxvalue3' is not accepted. It has to be set as Dynamic in the Pass Template. |
| E860 | 'auxlabel4' is not accepted. It has to be set as Dynamic in the Pass Template. |
| E861 | 'auxvalue4' is not accepted. It has to be set as Dynamic in the Pass Template. |
| E862 | 'backlabel1' is not accepted. It has to be set as Dynamic in the Pass Template. |
| E863 | 'backvalue1' is not accepted. It has to be set as Dynamic in the Pass Template. |
| E864 | 'backlabel2' is not accepted. It has to be set as Dynamic in the Pass Template. |
| E865 | 'backvalue2' is not accepted. It has to be set as Dynamic in the Pass Template. |
| E866 | 'backlabel3' is not accepted. It has to be set as Dynamic in the Pass Template. |
| E867 | 'backvalue3' is not accepted. It has to be set as Dynamic in the Pass Template. |
| E868 | 'backlabel4' is not accepted. It has to be set as Dynamic in the Pass Template. |
| E869 | 'backvalue4' is not accepted. It has to be set as Dynamic in the Pass Template. |
| E870 | 'rellatitude1', 'relongitude1' and 'reltext1' are not accepted. Relevance Location1 has to be set as Dynamic in the Pass Template. |
| E871 | 'rellatitude2', 'relongitude2' and 'reltext2' are not accepted. Relevance Location2 has to be set as Dynamic in the Pass Template. |
| E872 | 'rellatitude3', 'relongitude3' and 'reltext3' are not accepted. Relevance Location3 has to be set as Dynamic in the Pass Template. |
| E873 | 'rellatitude4', 'relongitude4' and 'reltext4' are not accepted. Relevance Location4 has to be set as Dynamic in the Pass Template. |
| E874 | 'rellatitude5', 'relongitude5' and 'reltext5' are not accepted. Relevance Location5 has to be set as Dynamic in the Pass Template. |
| E875 | 'rellatitude6', 'relongitude6' and 'reltext6' are not accepted. Relevance Location6 has to be set as Dynamic in the Pass Template. |
| E876 | 'rellatitude7', 'relongitude7' and 'reltext7' are not accepted. Relevance Location7 has to be set as Dynamic in the Pass Template. |
| E877 | 'rellatitude8', 'relongitude8' and 'reltext8' are not accepted. Relevance Location8 has to be set as Dynamic in the Pass Template. |
| E878 | 'rellatitude9', 'relongitude9' and 'reltext9' are not accepted. Relevance Location9 has to be set as Dynamic in the Pass Template. |
| E879 | 'rellatitude10', 'relongitude10' and 'reltext10' are not accepted. Relevance Location10 has to be set as Dynamic in the Pass Template. |
| E880 | 'rellatitude1' value is invalid. |
| E881 | 'rellatitude2' value is invalid. |
| E882 | 'rellatitude3' value is invalid. |
| E883 | 'rellatitude4' value is invalid. |
| E884 | 'rellatitude5' value is invalid. |
| E885 | 'rellatitude6' value is invalid. |
| E886 | 'rellatitude7' value is invalid. |
| E887 | 'rellatitude8' value is invalid. |
| E888 | 'rellatitude9' value is invalid. |
| E889 | 'rellatitude10' value is invalid. |
| E890 | 'rellongitude1' value is invalid. |
| E891 | 'rellongitude2' value is invalid. |
| E892 | 'rellongitude3' value is invalid. |
| E893 | 'rellongitude4' value is invalid. |
| E894 | 'rellongitude5' value is invalid. |
| E895 | 'rellongitude6' value is invalid. |
| E896 | 'rellongitude7' value is invalid. |
| E897 | 'rellongitude8' value is invalid. |
| E898 | 'rellongitude9' value is invalid. |
| E899 | 'rellongitude10' value is invalid. |
| E901 | The 'mobile' is required. |
| E902 | The 'campaignid' is required. |
| E903 | Invalid 'campaignid'. |
| E904 | Could not subscribe this number. |
| E905 | Could not unsubscribe this number. |
| E911 | The 'email' is required. |
| E912 | Invalid 'campaignid'. |
| E913 | Could not subscribe this 'email'. |
| E914 | Could not unsubscribe this 'email'. |
| E915 | This 'email' previously opted out of this or other email campaigns owned by this account/user. |
| E916 | Sending to this 'email' was previously a bounce-back. |
| E917 | This 'email' has filed a SPAM complaint on one or more email campaigns owned by this account/user. |
| E918 | This 'email' was previously opted out by this account/user. |
| E950 | 'ibeaconuuid1', 'ibeaconmajor1', 'ibeaconminor1' and 'ibeacontext1' values are not accepted. iBeacon1 field has to be set as dynamic in the Pass Template. |
| E951 | 'ibeaconuuid2', 'ibeaconmajor2', 'ibeaconminor2' and 'ibeacontext2' values are not accepted. iBeacon2 field has to be set as dynamic in the Pass Template. |
| E952 | 'ibeaconuuid3', 'ibeaconmajor3', 'ibeaconminor3' and 'ibeacontext3' values are not accepted. iBeacon3 field has to be set as dynamic in the Pass Template. |
| E953 | 'ibeaconuuid4', 'ibeaconmajor4', 'ibeaconminor4' and 'ibeacontext4' values are not accepted. iBeacon4 field has to be set as dynamic in the Pass Template. |
| E954 | 'ibeaconuuid5', 'ibeaconmajor5', 'ibeaconminor5' and 'ibeacontext5' values are not accepted. iBeacon5 field has to be set as dynamic in the Pass Template. |
| E955 | 'ibeaconuuid6', 'ibeaconmajor6', 'ibeaconminor6' and 'ibeacontext6' values are not accepted. iBeacon6 field has to be set as dynamic in the Pass Template. |
| E956 | 'ibeaconuuid7', 'ibeaconmajor7', 'ibeaconminor7' and 'ibeacontext7' values are not accepted. iBeacon7 field has to be set as dynamic in the Pass Template. |
| E957 | 'ibeaconuuid8', 'ibeaconmajor8', 'ibeaconminor8' and 'ibeacontext8' values are not accepted. iBeacon8 field has to be set as dynamic in the Pass Template. |
| E958 | 'ibeaconuuid9', 'ibeaconmajor9', 'ibeaconminor9' and 'ibeacontext9' values are not accepted. iBeacon9 field has to be set as dynamic in the Pass Template. |
| E959 | 'ibeaconuuid10', 'ibeaconmajor10', 'ibeaconminor10' and 'ibeacontext10' values are not accepted. iBeacon10 field has to be set as dynamic in the Pass Template. |
| E960 | 'ibeaconuuid1' value is invalid. | 
| E961 | 'ibeaconuuid2' value is invalid. |
| E962 | 'ibeaconuuid3' value is invalid. |
| E963 | 'ibeaconuuid4' value is invalid. |
| E964 | 'ibeaconuuid5' value is invalid. |
| E965 | 'ibeaconuuid6' value is invalid. |
| E966 | 'ibeaconuuid7' value is invalid. |
| E967 | 'ibeaconuuid8' value is invalid. |
| E968 | 'ibeaconuuid9' value is invalid. |
| E969 |'ibeaconuuid10' value is invalid. |
| E970 | 'ibeaconmajor1' value is invalid. | 
| E971 | 'ibeaconmajor2' value is invalid. |
| E972 | 'ibeaconmajor3' value is invalid. |
| E973 | 'ibeaconmajor4' value is invalid. |
| E974 | 'ibeaconmajor5' value is invalid. |
| E975 | 'ibeaconmajor6' value is invalid. |
| E976 | 'ibeaconmajor7' value is invalid. |
| E977 | 'ibeaconmajor8' value is invalid. |
| E978 | 'ibeaconmajor9' value is invalid. |
| E979 |'ibeaconmajor10' value is invalid. |
| E980 | 'ibeaconminor1' value is invalid. | 
| E981 | 'ibeaconminor2' value is invalid. |
| E982 | 'ibeaconminor3' value is invalid. |
| E983 | 'ibeaconminor4' value is invalid. |
| E984 | 'ibeaconminor5' value is invalid. |
| E985 | 'ibeaconminor6' value is invalid. |
| E986 | 'ibeaconminor7' value is invalid. |
| E987 | 'ibeaconminor8' value is invalid. |
| E988 | 'ibeaconminor9' value is invalid. |
| E989 |'ibeaconminor10' value is invalid. |
| E990 | 'ibeaconuuid1' value is required. | 
| E991 | 'ibeaconuuid2' value is required. |
| E992 | 'ibeaconuuid3' value is required. |
| E993 | 'ibeaconuuid4' value is required. |
| E994 | 'ibeaconuuid5' value is required. |
| E995 | 'ibeaconuuid6' value is required. |
| E996 | 'ibeaconuuid7' value is required. |
| E997 | 'ibeaconuuid8' value is required. |
| E998 | 'ibeaconuuid9' value is required. |
| E999 |'ibeaconuuid10' value is required. |
