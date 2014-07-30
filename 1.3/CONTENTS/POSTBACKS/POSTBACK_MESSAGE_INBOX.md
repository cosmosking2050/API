[Back to the Table of Contents](/1.3/README.md)

## SMS/MMS MO Postbacks

The MMS MO / SMS MO Postback API notifies you that a customer has replied to your messsage, or interacted to one of your keywords. To receive SMS MO postback notifications you need to have that option enabled in your account API. You can setup a separate Postback URL specifically for SMS/MMS MO's.

__SMS MO Information:__
 Once enabled you will receive an notification immediately when someone interacts with your shared shortcode campaign or your dedicated shortcode. Each message comes back in its own postback notification. 

__MMS MO Information:__
To receive MMS MO postback you need to configure it within the particular MMS Inbox keyword campaign.  Once the MMS MO postback is enabled in the MMS Inbox campaign you will start receiving postbacks for each MMS MO received on the MMS MO Keyword or replies to an SMS sent. If you have opted to enable the MMS MO moderation panel, then the postback notifictions will only be sent upon approval by the moderator.

### The SMS MO

This postback notifies you when an SMS MO is received.


| Variable | Description |
| -------- | ----------- |
| CODE | N211. | 
| ORIGIN | SMS_MO. | 
| FROM | SMS senders mobile number. | 
| TO | Shortcode or longcode the SMS was sent to. | 
| TEXT | The actual text that was sent by the sender. | 
| RECEIVED | Timestamp of the SMS received by our server. | 
| TRANSACTIONID | TransactionId for the SMS MO transaction that occurred. | 

```xml
<POSTBACK>
    <ORIGIN>SMS_MO</ORIGIN>
    <CODE>N211</CODE>
    <FROM>15552312102</FROM>
    <TO>86717</TO>
    <TEXT>STOP</TEXT>
    <RECEIVED>2011-09-28T17:31:02-04:00</RECEIVED>
    <TRANSACTIONID>511XG-02294-192SA-482H8</TRANSACTIONID>
</POSTBACK>
```

### The MMS MO

This postback notifies you when an MMS MO is received.

| Variable | Description |
| -------- | ----------- |
| CODE | N401. |
| ORIGIN | MMS_MO. |
| FROM | The phone number, including the country code, of the sender. | 
| TO | The recipient shortcode or longcode. | 
| KEYWORD | If a keyword was recognized in the first word of the subject or the first word body of the message and it matched to a MMS Inbox Keyword campaign that keyword will be passed in this node. | 
| TRACKINGID | A tracking ID, skycore has assigned this message. | 
| SPID | The SPID of the sender's carrier. | 
| TIMESTAMP | The timestamp that our system received the MMS MO. | 
| CONTENT | Contains the file nodes sent in the MMS MO. | 
| FILE | A series of sub-nodes that contains a single URL to a picture, video, audio or text file sent in the MMS MO within each node. The URL points to the location of the content on our servers. For those developing the back-end handling of the postback URL, you may choose to download/store these content files for whatever purpose you see fit. You may also choose to store the URLs for download at a future time. The file will be removed based on the terms of your contract. | 

```xml
<POSTBACK>
    <ORIGIN>MMS_MO</ORIGIN>
    <CODE>N401</CODE>
    <FROM>13217949521</FROM>
    <TO>74700</TO>
    <KEYWORD>all</KEYWORD>
    <TRACKINGID>MMS_MO_iLnCRrL6</TRACKINGID>
    <SPID>0001470</SPID>
    <TIMESTAMP>2014-02-03T11:19:49-05:00</TIMESTAMP>
    <CONTENT>
        <FILE>URL of Content Here</FILE>
        <FILE>URL of Content Here</FILE>
        <FILE>URL of Content Here</FILE>
    </CONTENT>
</POSTBACK>
```