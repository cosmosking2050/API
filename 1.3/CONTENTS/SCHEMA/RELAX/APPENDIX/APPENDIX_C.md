[Back to the Table of Contents](/1.3/README.md)

## APPENDIX C

__XML Reports, Campaign Batches, Autoresponders, Subscriptions and Sending Lists__

__Request Limit for getSendingStatistics()__

When getSendingStatistics() API function is called the Platform responds with a URL link that leads to an XML file to be downloaded. You are limited in the number of requests you can make per day to this API and in the period duration for which you want to get the report.

The report is a list of sent SMS/MMS xml reports grouped into sections.

__SMS sending XML__

All data related to sending one SMS are encapsulated inside the *&lt;TEXT&gt;* tag which contains a few attributes:

- *id* - The sending id in our history.
- *to* - Receiver's phone number.
- *carrier* - Receiver's carrier.
- *from* - The shortcode message that was sent fromerro.
- *body* - Text sent to the number.


Inside *&lt;TEXT&gt;* we list all status updates for that message. There are two statuses updates:

- ACK - Message has been processed on our side and left our server (status 10).
- DLR or ERROR - We received delivery report stating the delivery was successfull DLR (status 20) or failed (ERROR).

Here is the example of SMS sending XML:
```xml
<TEXT id="455118" to="11112233444" carrier="Verizon Wireless" from="60856" 
 body="Jack: Hello My friend!">
    <ACK gw="10" net="0" time="2012-04-30T08:30:12.327558Z">
    <DLR gw="20" net="0" time="2012-04-30T08:30:12.327558Z">
</TEXT>
```

```xml
element TEXT {
    attribute id { text } &
    attribute to { text } &
    attribute carrier { text } &
    attribute from { text } &
    attribute body { text } &
    element ACK {
        attribute gw { text } &
        attribute net { text } &
        attribute time { text }
    } &
    element DLR {
        attribute gw { text } &
        attribute net { text } &
        attribute time { text }
    }
}
```

__MMS sending XML__

All data related to sending one MMS are encapsulated inside the _&lt;CONTENT&gt;_ tag which contain few attributes:

- *id* - This sending id in our history.
- *to* - Receiver's phone number.
- *carrier* - Receiver's carrier.
- *contentid* - Id of the content/MMS.
- *contentname* - Name of the content/MMS.
- *from* - The shortcode message that was sent from.
- *delivery* - The delivery type (binary/xhtml).


Inside *&lt;CONTENT&gt;* we have *&lt;MSG_STATUS&gt;* tag which encapsulate all status updates for that message and *&lt;MM7_HANDSETID&gt;/&lt;XHTML_HANDSETID&gt;*

*&lt;MSG_STATUS&gt;* contain all SMS/MMS status updates, we update each SMS/MMS status multiple times during the sending process and tag will indicate which stage of the sending process the SMS/MMS is in.

For BINARY MMS sending, our statuses are in chronological order:

- INQUE - Message inserted into processing que.
- INIT - Processing message has been started (status 0).
- ACK or ERROR - Message has been processed on our side and left our server (ACK - status 9) or some internal ERROR occured.
- DLR or EXPIRED or REJECTED - We received delivery report, meaning phone has received the message (DLR - status 20) or carrier rejected MMS (REJECTED - status 35) or carrier could not deliver MMS to handset (EXPIRED - status 30).


Based on the sendings we do sent binary Device Discovery Message (DDM) that preceed sending real MMS, statuses for DDM are as follows:

- INQUE - Message inserted into processing que.
- ACK - Message has been processed on our side and left our server (ACK - status 80)
- DLR or EXPIRED or REJECTED - We received DDM delivery report, meaning phone has received the message (DLR - status 81) or carrier rejected MMS (REJECTED - status 35) or carrier could not deliver MMS to handset (EXPIRED - status 30). When we receive DLR status for DDM sending of real MMS is triggered instantly.

For XHTML MMS we also have in chronological order:

- INQUE - Message inserted into processing que.
- INIT - Processing message has been started (status 0).
- ACK or ERROR - Message has been processed on our side and link has been sent to the phone (ACK - status 10) or some internal ERROR occured.
- DLR - We received delivery report, meaning phone has received the link (status 20).
- OPENED - Link has been browsed (status 11).

*&lt;MM7_HANDSETID&gt;/&lt;XHTML_HANDSETID&gt;* contain detected handset. For binary delivery we are placing the handsetid inside *&lt;MM7_HANDSTID&gt;*, for xhtml delivery we put the browser UA Profile inside *&lt;XHTML_HANDSETID&gt;*.

Here is the example of MMS sending XML (binary delivery):
```xml
<CONTENT id="455076" carrier="T-Mobile" to="11112233444" delivery="binary" 
 contentid="40301" contentname="Flowers" from="60856">
    <MSG_STATUS>
        <INQUE time="2012-04-24T04:45:15.655766Z"/>
        <INIT gw="0" net="0" time="2012-04-24T04:45:16.831756Z"/>
        <ACK gw="9" net="0" time="2012-04-24T04:45:18.80118Z"/>
        <DLR gw="20" net="1000" time="2012-04-24T04:45:23.953745Z"/>
    </MSG_STATUS>
    <MM7_HANDSETID>motol7c</MM7_HANDSETID>
</CONTENT>
```

```xml
element CONTENT {
    attribute id { text } &
    attribute carrier { text } &
    attribute to { text } &
    attribute delivery { text } &
    attribute contentid { text } &
    attribute contentname { text } &
    attribute from { text } &
    element MSG_STATUS {
        element INQUE {
            attribute time { text }
        } &
        element INIT {
            attribute gw { text } &
            attribute net { text } &
            attribute time { text }
        } &
        element ACK {
            attribute gw { text } &
            attribute net { text } &
            attribute time { text }
        } &
        element DLR {
            attribute gw { text } &
            attribute net { text } &
            attribute time { text }
        }
    } &
    element MM7_HANDSETID { text }
}
```

Here is the example of MMS sending XML (xhtml delivery):
```xml
<CONTENT id="455119" to="48111222333" carrier="All Carriers" delivery="xhtml" 
 contentid="39755" contentname="Flowers" from="+447624805892">
    <MSG_STATUS>
        <INQUE time="2012-04-30T09:06:07.5649Z"/>
        <INIT gw="0" net="0" time="2012-04-30T09:06:08.338719Z"/>
        <ACK gw="10" net="0" time="2012-04-30T09:06:08.918484Z"/>
        <OPENED gw="11" net="0" time="2012-04-30T09:06:39.258603Z"/>
        <DLR gw="20" net="0" time="2012-04-30T09:06:08.783382Z">
    </MSG_STATUS>
    <XHTML_HANDSETID>Mozilla/5.0 (Windows NT 6.1; WOW64) AppleWebKit/535.19 
     (KHTML, like Gecko) Chrome/18.0.1025.162 Safari/535.19</XHTML_HANDSETID>
</CONTENT>
```

```xml
element CONTENT {
    attribute id { text } &
    attribute to { text } &
    attribute carrier { text } &
    attribute delivery { text } &
    attribute contentid { text } &
    attribute contentname { text } &
    attribute from { text } &
    element MSG_STATUS {
        element INQUE {
            attribute time { text }
        } &
        element INIT {
            attribute gw { text } &
            attribute net { text } &
            attribute time { text }
        } &
        element ACK {
            attribute gw { text } &
            attribute net { text } &
            attribute time { text }
        } &
        element OPENED {
            attribute gw { text } &
            attribute net { text } &
            attribute time { text }
        } &
        element DLR {
            attribute gw { text } &
            attribute net { text } &
            attribute time { text }
        }
    } &
    element XHTML_HANDSETID { text }
}
```

### Report

The Report itself contains a list of all messages grouped into sections encapsulated into *&lt;RESPONSE&gt;* tag. Here are more detailed examples of what we have in each section.

__A) Campaign Batches__ are encapsulated inside *&lt;BATCHES&gt;&lt;/BATCHES&gt;*. Each MMS/SMS batch contain a list of SMS/MMS XML that is encalpsulated inside *&lt;BATCH&gt;&lt;/BATCH&gt;* tag. Batches represent campaign scheduled sending of the MMS or SMS. Each *&lt;BATCH&gt;* tag contain attributes:

- *id* - The campaign scheduled sending id.
- *campaignid* - Campaign ID.
- *campaignname* - Campaign name.
- *scheduled_date* - Date the campaign was scheduled to be sent out.
- *contentid* - (only for MMS) Name of the content/MMS sent to the phones.
- *contentname* - (only for MMS) Name of the content/MMS sent to the phones.
- *body* - (only for MMS) Text of the SMS sent to the phones.
- *from* - The shortcode messages that were sent from.


Because some attributes are common across whole campaign scheduled sending we do not place them inside SMS/MMS XML and just have them inside *&lt;BATCH&gt;* tag. Those attributes are: *contentid*, *contentname* (for MMS sent from Campaign), *body* (for SMS sent from Campiagn), *from*.

Here is MMS sending inside Campaign batch:
```xml
<BATCHES>
    <BATCH id="12418" from="60856" campaignid="1136" campaignname="MyCampaign" 
     scheduled_date="2010-10-12 06:32:46.620197-04@server localtime" contentid="35080" 
     contentname="Flowers"/>
        <CONTENT id="150838" carrier="Verizon Wireless" to="11112233444" delivery="binary">
            <MSG_STATUS>
                <INQUE time="2010-10-12T06:32:46.620197Z"/>
                <INIT gw="0" net="0" time="2010-10-12T06:33:12.115367Z"/>
                <ACK gw="9" net="1000" time="2010-10-12T06:33:12.508827Z"/>
                <DLR gw="20" net="1000" time="2010-10-12T06:33:19.579773Z"/>
            </MSG_STATUS>
            <MM7_HANDSETID>VX8000v1</MM7_HANDSETID>
        </CONTENT>
        ....
        ....
    </BATCH>
    ....
    ....
</BATCHES>
```

```xml
element BATCHES {
    element BATCH {
        attribute id { text } &
        attribute from { text } &
        attribute campaignid { text } &
        attribute campaignname { text } &
        attribute scheduled_date { text } &
        attribute contentid { text } &
        attribute contentname { text } &
        element CONTENT {
            attribute id { text } &
            attribute carrier { text } &
            attribute to { text } &
            attribute delivery { text } &
            element MSG_STATUS {
                element INQUE {
                    attribute time { text }
                } &
                element INIT {
                    attribute gw { text } &
                    attribute net { text } &
                    attribute time { text }
                } &
                element ACK {
                    attribute gw { text } &
                    attribute net { text } &
                    attribute time { text }
                } &
                element DLR {
                    attribute gw { text } &
                    attribute net { text } &
                    attribute time { text }
                }
            } &
            element MM7_HANDSETID { text }
        }
    }
}
```

Here is SMS sending inside alert batch:
```xml
<BATCHES>
    <BATCH id="21896" from="60856" scheduled_date="2012-04-27T13:00:00Z@server localtime" 
     campaignid="1442" campaignname="MyCampaign" body="Sample SMS for Campaign"/> 
        <TEXT id="455110" to="11112233444">
            <ACK gw="10" net="0" time="2012-04-27T13:05:05.89278Z">
            <DLR gw="20" net="0" time="2012-04-27T13:05:05.89278Z"> 
        </TEXT>
        <TEXT id="455109" to="11112233444">
            <ACK gw="10" net="0" time="2012-04-27T13:05:05.881257Z">
            <DLR gw="20" net="0" time="2012-04-27T13:05:05.881257Z">
        </TEXT> 
        ....
        ....
    </BATCH>
    ....
    ....
</BATCHES>
```

```xml
element BATCHES {
    element BATCH {
        attribute id { text } &
        attribute from { text } &
        attribute scheduled_date { text } &
        attribute campaignid { text } &
        attribute campaignname { text } &
        attribute body { text } &
        element TEXT {
            attribute id { text } &
            attribute to { text } &
            element ACK {
                attribute gw { text } &
                attribute net { text } &
                attribute time { text }
            } &
            element DLR {
                attribute gw { text } &
                attribute net { text } &
                attribute time { text }
            }
        }
    }
}
```

__B) Campaign autoresponder__ are encapsulated inside *&lt;AUTORESPONDERS&gt;&lt;/AUTORESPONDERS&gt;*. Each MMS/SMS autoresponder contain a list of SMS/MMS XML that is encalpsulated inside *&lt;AUTORESPONDER&gt;&lt;/AUTORESPONDER&gt;* tag. Autoresponders represent all MMS/SMS sendings of one Campaign autoresponder. Each *&lt;AUTORESPONDER&gt;* tag contain attributes:

- *id* - The campaign autoresponder id.
- *campaignid* - Campaign ID.
- *campaignname* - Campaign name.
- *contentid* - (only for MMS) Name of the content/MMS sent to the phones.
- *contentname* - (only for MMS) Name of the content/MMS sent to the phones.
- *body* - (only for MMS) Text of the SMS sent to the phones.
- *from* - The shortcode messages that were sent from.


Because some attributes are common across whole campaign autoresponder sending we do not place them inside SMS/MMS XML and just have them inside *&lt;AUTORESPONDER&gt;* tag. Those attributes are: *contentid*, *contentname* (for MMS Autoresponders), *body* (for SMS Autoresponders), *from*.

Here is MMS Autoresponder example:
```xml
<AUTORESPONDERS>
    <AUTORESPONDER id="351" from="60856" campaignid="1442" campaignname="MyCampaign" 
     contentid="40301" contentname="Flowers"/> 
        <CONTENT id="455076" carrier="T-Mobile" to="11112233444" delivery="binary"> 
            <MSG_STATUS> 
                <INQUE time="2012-04-24T04:45:15.655766Z"/> 
                <INIT gw="0" net="0" time="2012-04-24T04:45:16.831756Z"/> 
                <ACK gw="9" net="0" time="2012-04-24T04:45:18.80118Z"/> 
                <DLR gw="20" net="1000" time="2012-04-24T04:45:23.953745Z"/> 
            </MSG_STATUS> 
            <MM7_HANDSETID>motol7c</MM7_HANDSETID> 
        </CONTENT>
        ....
        ....
    </AUTORESPONDER>
    ....
    ....
</AUTORESPONDERS>
```

```xml
element AUTORESPONDERS
{
    element AUTORESPONDER {
        attribute id { text } &
        attribute from { text } &
        attribute campaignid { text } &
        attribute campaignname { text } &
        attribute contentid { text } &
        attribute contentname { text } &
        element CONTENT {
            attribute id { text } &
            attribute carrier { text } &
            attribute to { text } &
            attribute delivery { text } &
            element MSG_STATUS {
                element INQUE {
                    attribute time { text }
                } &
                element INIT {
                    attribute gw { text } &
                    attribute net { text } &
                    attribute time { text }
                } &
                element ACK {
                    attribute gw { text } &
                    attribute net { text } &
                    attribute time { text }
                } &
                element DLR {
                    attribute gw { text } &
                    attribute net { text } &
                    attribute time { text }
                }
            } &
            element MM7_HANDSETID { text }
        }
    }
}


Here is SMS Autoresponder example:
```xml
<AUTORESPONDERS>
   <AUTORESPONDER id="352" from="60856" campaignid="1442" campaignname="MyCampaign" 
    body="text autoresponder"/>
      <TEXT id="455078" to="11112233444">
         <ACK gw="10" net="0" time="2012-04-24T04:45:48.133354Z">
         <DLR gw="20" net="0" time="2012-04-24T04:45:48.133354Z">
      </TEXT>
      <TEXT id="455077" to="11112233444">
         <ACK gw="10" net="0" time="2012-04-24T04:45:17.278337Z">
         <DLR gw="20" net="0" time="2012-04-24T04:45:17.278337Z">
      </TEXT>
      .... 
      .... 
   </AUTORESPONDER>
   ....
   ....
</AUTORESPONDERS>
```

```xml
element AUTORESPONDERS {
    element AUTORESPONDER {
        attribute id { text } &
        attribute from { text } &
        attribute campaignid { text } &
        attribute campaignname { text } &
        attribute body { text } &
        element TEXT {
            attribute id { text } &
            attribute to { text } &
            element ACK {
                attribute gw { text } &
                attribute net { text } &
                attribute time { text }
            } &
            element DLR {
                attribute gw { text } &
                attribute net { text } &
                attribute time { text }
            }
        }
    }
}
```

__C) Campaign Subscriptions__ are encapsulated inside *&lt;SUBSCRIPTIONS&gt;&lt;/SUBSCRIPTIONS&gt;*. Traffic generated for each subscription contain a list of SMS/MMS XML that is encalpsulated inside *&lt;SUB&gt;&lt;/SUB&gt;* tag. Each *&lt;SUB&gt;* tag contain attributes:

- *to* - Subscriber's phone number.
- *carrier*- Subscriber's carrier.
- *from* - The shortcode messages that were sent from.


All above mentioned attributes are common across whole subscription traffic and we don't put inside SMS/MMS XML and just have them inside *&lt;SUB&gt;* tag.

Here is the example of the traffic for the Single Opt-In subscription with SMS Confirmation:
```xml
<SUBSCRIPTIONS>
    <SUB to="11112233444" carrier="AT&T" from="60856"> 
        <TEXT id="455037" text="MyBrand: Confirmed to MyCampaign, msg/. Msg&Data rates may 
         apply. Reply STOP to cancel, HELP for help. Enterprisem.ms">
            <ACK gw="10" net="0" time="2012-04-10T06:38:56.090705Z">
            <DLR gw="20" net="0" time="2012-04-10T06:38:56.090705Z">
        </TEXT> 
    </SUB>
    ....
    ....
</SUBSCRIPTIONS>
```

```xml
element SUBSCRIPTIONS {
    element SUB {
        attribute to { text } &
        attribute carrier { text } &
        attribute from { text } &
        element TEXT {
            attribute id { text } &
            attribute text { text } &
            element ACK {
                attribute gw { text } &
                attribute net { text } &
                attribute time { text }
            } &
            element DLR {
                attribute gw { text } &
                attribute net { text } &
                attribute time { text }
            }
        }
    }
}
```

Here is the example of the traffic for the Double Opt-In subscription with MMS Confirmation:
```xml
<SUBSCRIPTIONS>
    <SUB to="11112233444" carrier="T-Mobile" from="60856">
        <CONTENT id="455112" contentid="39755" contentname="Flowers" delivery="binary">
            <MSG_STATUS>
                <INQUE time="2012-04-27T13:32:21.798528Z"/>
                <INIT gw="0" net="0" time="2012-04-27T13:32:22.204127Z"/>
                <ACK gw="9" net="0" time="2012-04-27T13:32:24.200166Z"/>      
            </MSG_STATUS>
            <MM7_HANDSETID>Default</MM7_HANDSETID>
        </CONTENT>
        <TEXT id="455111" text="MyBrand: To follow MyCampaign,  msg/, reply YES. 
         Msg&Data rates may apply. Reply HELP for help. Enterprisem.ms.">
            <ACK gw="10" net="0" time="2012-04-27T13:32:12.892155Z">
            <DLR gw="20" net="0" time="2012-04-27T13:32:12.892155Z">
        </TEXT>
    </SUB>
    ....
    ....
</SUBSCRIPTIONS>
```

```xml
element SUBSCRIPTIONS {
    element SUB {
        attribute to { text } &
        attribute carrier { text } &
        attribute from { text } &
        element CONTENT {
            attribute id { text } &
            attribute contentid { text } &
            attribute contentname { text } &
            attribute delivery { text } &
            element MSG_STATUS {
                element INQUE {
                    attribute time { text }
                } &
                element INIT {
                    attribute gw { text } &
                    attribute net { text } &
                    attribute time { text }
                } &
                element ACK {
                    attribute gw { text } &
                    attribute net { text } &
                    attribute time { text }
                }
            } &
            element MM7_HANDSETID { text }
        } &
        element TEXT {
            attribute id { text } &
            attribute text { text } &
            element ACK {
                attribute gw { text } &
                attribute net { text } &
                attribute time { text }
            } &
            element DLR {
                attribute gw { text } &
                attribute net { text } &
                attribute time { text }
            }
        }
    }
}
```

__D) Sending List__ contain all other SMS/MMS sendings encapsulated into *&lt;SENDING_LIST&gt;&lt;/SENDING_LIST&gt;* tag. This contain a list of *&lt;CONTENT&gt;* and *&lt;TEXT&gt;* tags.

Below is example of MMS:
```xml
<SENDING_LIST>
   <CONTENT id="455043" carrier="All Carriers" to="48111222333" delivery="xhtml" 
    contentid="39755" contentname="Flowers" from="+447624805892">
      <MSG_STATUS>
         <INQUE time="2012-04-23T09:04:57.353055Z"/>
         <INIT gw="0" net="0" time="2012-04-23T09:04:58.048795Z"/>
         <ACK gw="10" net="0" time="2012-04-23T09:05:03.516081Z"/>
         <ERROR info="delivery failure" time="2012-04-23T09:05:02.982315Z">       
      </MSG_STATUS>
   </CONTENT>
   ....
   ....
</SENDING_LIST>
```

```xml
element SENDING_LIST {
    element CONTENT {
        attribute id { text } &
        attribute carrier { text } &
        attribute to { text } &
        attribute delivery { text } &
        attribute contentid { text } &
        attribute contentname { text } &
        attribute from { text } &
        element MSG_STATUS {
            element INQUE {
                attribute time { text }
            } &
            element INIT {
                attribute gw { text } &
                attribute net { text } &
                attribute time { text }
            } &
            element ACK {
                attribute info { text } &
                attribute time { text }
            } &
            element ERROR {
                attribute info { text } &
                attribute time { text }
            }
        }
    }
}
```

Below is example of SMS:
```xml
<SENDING_LIST>
   <TEXT id="150283" to="11112233444" text="Hello my friend. Where do you want to go today?">
      <ACK gw="10" net="0" time="2010-10-05T12:21:40.947088Z">
      <DLR gw="20" net="0" time="2010-10-05T12:21:40.947088Z">
   </TEXT>
   ....
   ....
</SENDING_LIST>
```

```xml
element SENDING_LIST {
    element TEXT {
        attribute id { text } &
        attribute to { text } &
        attribute text { text } &
        element ACK {
            attribute gw { text } &
            attribute net { text } &
            attribute time { text }
        } &
        element DLR {
            attribute gw { text } &
            attribute net { text } &
            attribute time { text }
        }
    }
}
