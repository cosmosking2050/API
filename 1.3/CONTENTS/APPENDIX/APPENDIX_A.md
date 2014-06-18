[Back to the Table of Contents](/1.3/README.md)&nbsp;&nbsp;|&nbsp;&nbsp;[Back to Appendix List](API_APPENDIX.md)</a>
## APPENDIX A

__KEY TERM DEFINITIONS__

| Variable | Description |
| -------- | ----------- |
| ACTION | This is the name of the function you want to execute with the API. |
| API_KEY | Random key that is assigned to an account that can be used for authorization instead of USER/PASS. You can find and regenerate this key on the 'API Settings' page. |
| BARCODEID | The alphanumeric value that is encoded inside a barcode that was sent using the 'sendMMSBarcode' function. |
| BARCODEVALUE | The barcode value or Id that will be encoded into the barcode image on the pass. |
| BARCODETEXT | Added text that will be shown below the barcode image on the pass. |
| BRANDNAME | The company, brand, or individual that will appear as the sender’s name for the campaign. |
| CAMPAIGNID | The ID(integer) of the campaign to which the user will be subscribed. |
| CAMPAIGNNAME | The name for a new campaign created with either the createMMSCampaign or createEmailCampaign function |
| CAMPAIGNREF | Depending on your API settings, you may be required to subscribe a user first before sending them messages. If you are required to subscribe a user first, then a valid Campaign Reference is required. This would be the campaign ID(integer) to which the user is subscribed. |
| CTA | This will prompt a mobile owner with a subscribe/unsubscribe confirmation via SMS Opt-in request (yes/no). |
| CUSTOMTEXT | This is custom text that will overwrite a given slide text used in a sendSavedMMS function call. |
| CUSTOMTITLE | This is a custom title that will overwrite the MMS Subject used in a sendSavedMMS function call. |
| DURATION | The duration of a slide displayed in seconds (integer). |
| DATABASEID | The identification code for a Barcode Database(integer). |
| DDMTITLE | Title for a DDM message (Device Discovery Message) used in the sendSavedMMS function. |
| DDMTEXT | Text/Body for DDM message (Device Discovery Message) used in the sendSavedMMS function. |
| DDMTIMEOUT |  The time(in minutes) for a DDM message (Device Discovery Message) used in the 'sendSavedMMS' function. After this time expires, we send an MMS even if there is not a DDM result received. |
| EMAIL | A valid email address. |
| EMAILID | The ID(integer) for an email template. |
| END_DATE | The end date of the sending statistics used in the 'getSendingStatistics' function. The format should be "YYYY-MM-DD hh:mm:ss" (ignoring quotations). |
| FROM | A valid shortcode or longcode for the sender address(string). When sending to a list of many numbers using the 'sendSavedContent' function and if the 'FROM' value cannot be used for a certain country, then the system will re-write the sender address to use a valid shortcode for those numbers. |
| HISTORYID | This is a permanent reference number used to indentify the SMS/MMS message sending in our History. The 'HISTORYID' is used in the API reports. |
| MAILINGADDRESS | This is the physical address that will appear in your email footers. You are required to provide your physical address in accordance with the "CAN-SPAM Act of 2003". Please make sure to include your company name and country in the address when you create a campaign. This field is used when creating an Email campaign. |
| MMSID | The ID(integer) of a saved MMS. |
| MMSINBOXID | The ID(integer) of a saved MMS to be removed inside the 'removeMMSInboxContent' function. |
| MOBILE | A Phone Number used inside the 'subscribe'/'unsubscribe' function. |
| NEWPASS | A Password for a new account created with the 'createUser' function. |
| NEWUSER | A Username for a new account created with the 'createUser' function. |
| NOTIFY | A mobile owner will be notified about being subscribed/unsubscribed via a confirmation SMS (yes/no). |
| ORIGIN | This identifies the Postback. It can be SMS_MT, MMS_MT or SUB. |
| PASS | A valid, md5() encoded account password. |
| PASSDATA |  All the data that goes on the pass(Array). |
| PASSDATAID | A valid Pass Data Row ID(integer). |
| PASSTEMPLATEID | Valid Pass Template ID(integer). |
| SCHEDULEDID | This is a reference ID(integer) for a sending campaign. It is used for every number belonging to that campaign. When campaign sending is processed, the system will generate postback notifications linking SCHEDULEDID with TRACKINGID and HISTORYID. |
| SEQUENCE | This encloses all MMS slide presentation data from one or multiple slides (up to a maximum of 8). |
| SLIDE | This represents a single slide within the MMS sequence the could include IMAGE/URL/TEXT/PIC etc. (There are special rules for slides within the 'saveMMS' special consideration section). |
| SPID | The carrier ID(integer). See <a href="/1.3/CONTENTS/APPENDIX/APPENDIX_E.md">Appendix E</a>. |
| START_DATE | The start date for sending statistics used in the 'getSendingStatistics' function. The format should be "YYYY-MM-DD hh:mm:ss" (ignoring quotations). |
| TEXT | The SMS message limit is 160 characters(string). |
| TO | This is the message recipient's phone number in an international format. |
| TOCAMPAIGN | The ID(integer) of a campaign for which you want to schedule an MMS using the 'sendSavedMMSCampaign' function. |
| TRACKINGID | On success, the API returns with the tracking ID(integer) to identify sent messages.  On failure, no tracking ID is returned. This is the internal reference number for SMS/MMS sending, it is a temporary ID and (where possible) HISTORYID should be used. Once the message sending is processed you shall receive a postback containing both TRACKINGID and HISTORYID. |
| TRANSACTIONID | The ID(integer) that will be encoded into a delivered barcode(string). |
| TIMEZONE | A time zone abbreviation associated with the phone number used inside the 'subscribe' function. |
| USER | A valid account username. |
