SMS sending XML
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

MMS sending XML (binary delivery)
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

MMS sending XML (xhtml delivery)
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

MMS sending inside campaign batch
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
        }+
    }+
}
```

SMS sending inside alert batch
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
        }+
    }+
}
```

MMS Autoresponder
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
        }+
    }+
}
```

SMS Autoresponder
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
        }+
    }+
}
```

Traffic for the Single Opt-In subscription with SMS Confirmation
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
    }+
}
```

Traffic for the Double Opt-In subscription with MMS Confirmation
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
    }+
}
```

MMS Sending List
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
    }+
}
```

SMS Sending List
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
    }+
}