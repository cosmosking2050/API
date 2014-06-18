[Back to the Table of Contents](/1.3/README.md)&nbsp;&nbsp;|&nbsp;&nbsp;[Back to API Methods](API_METHODS.md)
## getSendingStatistics

__Synopsis:__  
This API requests a report of all messaging transactions between two dates. The server returns the path to an XML file containing the report. All results are saved to file which must be downloaded by the requestor. Detailed Information about the report will be in [Appendix C](/1.3/CONTENTS/APPENDIX/APPENDIX_C.md).

__Request:__
```xml
<REQUEST>
    <ACTION>getSendingStatus</ACTION>
    <API_KEY>API KEY</API_KEY>
    <START_DATE>UTC StartDate</START_DATE>
    <END_DATE>UTC EndDate</ END_DATE>
</REQUEST>
```

__Request Parameters:__

    Mandatory: Action, API_KEY, End_Date, Start_Date
    Optional: N/A

__Response Parameters:__

    Errorcode, Errorinfo, MMSID, Status

__Related Errorcodes:__

    E506, E507, E508, E509, E510

__Request Example:__  
XML:
```xml
<REQUEST>
  <ACTION>getSendingStatus</ACTION>
    <API_KEY>qTFkykO9JTfahCOqJ0V2Wf5Cg1t8iWlZ</API_KEY>
    <START_DATE>2010-10-01 12:00:00</START_DATE>
    <END_DATE>2010-10-02 12:00:00</END_DATE>
</REQUEST>
```

GET:

    https://secure.skycore.com/API/wxml/1.3/index.php?action=getsendingstatus&api_key=qTFkykO9JTfahCOqJ0V2Wf5Cg1t8iWlZ
    &start_date=2010-10-01+12:00:00&end_date=2010-10-02+12:00:00

__Response Example__  
Responses will be a link to a XML file containing the report. All results are saved to file which must be downloaded by the requestor. Detailed Information about the report will be in [Appendix C](/1.3/CONTENTS/APPENDIX/APPENDIX_C.md).
