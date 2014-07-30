REQUEST
```xml
element REQUEST {
    element ACTION { "generatePass" } &
    element API_KEY { text } &
    element PASSTEMPLATEID { text } &
    element PASSDATA {
        element CUSTOMPASSID { text }? &
        element THUMBNAILURL { text }? &
        element BARCODEVALUE { text } &    # if "Barcode = Allowed" && "Barcode Type = Dynamic" && "Barcode Value Source = Dynamic Value" for Pass Template otherwise IGNORED
        element BARCODETEXT { text }? &    # if "Barcode = Allowed" && "Barcode Alternate Text = Dynamic Text" for Pass Template otherwise IGNORED
        element HEADERLABEL1 { text }? &
        element HEADERVALUE1 { text }? &
        element PRIMARYLABEL1 { text }? &
        element PRIMARYVALUE1  { text }? &
        element PRIMARYLABEL2 { text }? &    # if "Pass Template Type = Boarding Pass" otherwise IGNORED
        element PRIMARYVALUE2  { text }? &    # if "Pass Template Type = Boarding Pass" otherwise IGNORED
        element SECLABEL1 { text }? &
        element SECVALUE1 { text }? &
        element SECLABEL2 { text }? &
        element SECVALUE2 { text }? &
        element SECLABEL3 { text }? &
        element SECVALUE3 { text }? &
        element SECLABEL4 { text }? &
        element SECVALUE4 { text }? &
        element AUXLABEL1 { text }? &
        element AUXVALUE1 { text }? &
        element AUXLABEL2 { text }? &
        element AUXVALUE2 { text }? &
        element AUXLABEL3 { text }? &
        element AUXVALUE3 { text }? &
        element AUXLABEL4 { text }? &
        element AUXVALUE4 { text }? &
        element BACKLABEL1 { text }? &
        element BACKVALUE1 { text }? &
        element BACKLABEL2 { text }? &
        element BACKVALUE2 { text }? &
        element BACKLABEL3 { text }? &
        element BACKVALUE3 { text }? &
        element BACKLABEL4 { text }? &
        element BACKVALUE4 { text }? &
        element RELLATITUDE1 { text }? &
        element RELLONGITUDE1 { text }? &
        element RELTEXT1 { text }? &
        element RELLATITUDE2 { text }? &
        element RELLONGITUDE2 { text }? &
        element RELTEXT2 { text }? &
        element RELLATITUDE3 { text }? &
        element RELLONGITUDE3 { text }? &
        element RELTEXT3 { text }? &
        element RELLATITUDE4 { text }? &
        element RELLONGITUDE4 { text }? &
        element RELTEXT4 { text }? &
        element RELLATITUDE5 { text }? &
        element RELLONGITUDE5 { text }? &
        element RELTEXT5 { text }? &
        element RELLATITUDE6 { text }? &
        element RELLONGITUDE6 { text }? &
        element RELTEXT6 { text }? &
        element RELLATITUDE7 { text }? &
        element RELLONGITUDE7 { text }? &
        element RELTEXT7 { text }? &
        element RELLATITUDE8 { text }? &
        element RELLONGITUDE8 { text }? &
        element RELTEXT8 { text }? &
        element RELLATITUDE9 { text }? &
        element RELLONGITUDE9 { text }? &
        element RELTEXT9 { text }? &
        element RELLATITUDE10 { text }? &
        element RELLONGITUDE10 { text }? &
        element RELTEXT10 { text }?
    }
}
```

RESPONSE
```xml
element RESPONSE {
    element STATUS { text } &
    element PASSDATAID { text }? &
    element SERIALNUMBER { text }? &
    element CUSTOMPASSID { text }? &
    element PASSLINK { text }? &
    element DOWNLOADURL { text }? &
    element ERRORCODE { text }? &
    element ERRORINFO { text }?
}
```