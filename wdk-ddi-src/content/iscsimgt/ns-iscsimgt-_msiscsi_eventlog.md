---
UID: NS:iscsimgt._MSiSCSI_Eventlog
title: _MSiSCSI_Eventlog (iscsimgt.h)
description: This MSiSCSI_EventLog method is used to log any messages to the event log.
old-location: storage\msiscsi_eventlog.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["MSiSCSI_Eventlog structure"]
ms.keywords: "*PMSiSCSI_Eventlog, MSiSCSI_EventLog, MSiSCSI_EventLog structure [Storage Devices], MSiSCSI_Eventlog, PMSiSCSI_EventLog, PMSiSCSI_EventLog structure pointer [Storage Devices], _MSiSCSI_Eventlog, iscsimgt/MSiSCSI_EventLog, iscsimgt/PMSiSCSI_EventLog, storage.msiscsi_eventlog, structs-iSCSI_d2419ba1-4f36-42c6-8a21-164dadb50263.xml"
req.header: iscsimgt.h
req.include-header: Iscsimgt.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: MSiSCSI_Eventlog, *PMSiSCSI_Eventlog
f1_keywords:
 - _MSiSCSI_Eventlog
 - iscsimgt/_MSiSCSI_Eventlog
 - PMSiSCSI_Eventlog
 - iscsimgt/PMSiSCSI_Eventlog
 - MSiSCSI_Eventlog
 - iscsimgt/MSiSCSI_Eventlog
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Iscsimgt.h
api_name:
 - _MSiSCSI_Eventlog
 - PMSiSCSI_Eventlog
 - MSiSCSI_Eventlog
---

# _MSiSCSI_Eventlog structure


## -description

This MSiSCSI_EventLog method is used to log any messages to the event log.

## -struct-fields

### -field Type

This specifies the EVENTLOG_MESSAGE_QUALIFIERS type of event log message.

### -field LogToEventlog

### -field Size

This specifies the size of the Additional Data field.

### -field AdditionalData

 




#### - AdditionalData[1]

This provides additional information associated with this event.


#### - LogToEventLog

If this value it set to 1, the message will be logged to the system event log.

## -remarks

We recommend that you implement this class.

