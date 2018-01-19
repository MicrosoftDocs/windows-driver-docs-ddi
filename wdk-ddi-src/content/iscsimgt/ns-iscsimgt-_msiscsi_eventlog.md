---
UID: NS:iscsimgt._MSiSCSI_Eventlog
title: _MSiSCSI_Eventlog
author: windows-driver-content
description: This MSiSCSI_EventLog method is used to log any messages to the event log.
old-location: storage\msiscsi_eventlog.htm
old-project: storage
ms.assetid: a31a8688-6002-4ad7-b135-0a8111e2c849
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _MSiSCSI_Eventlog, MSiSCSI_Eventlog, *PMSiSCSI_Eventlog
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: iscsimgt.h
req.include-header: Iscsimgt.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: MSiSCSI_EventLog
req.alt-loc: Iscsimgt.h
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
req.typenames: MSiSCSI_Eventlog, *PMSiSCSI_Eventlog
---

# _MSiSCSI_Eventlog structure



## -description
This MSiSCSI_EventLog method is used to log any messages to the event log.



## -syntax

````
typedef struct _MSiSCSI_EventLog {
  ULONG Type;
  ULONG LogToEventLog;
  ULONG Size;
  UCHAR AdditionalData[1];
} MSiSCSI_EventLog, *PMSiSCSI_EventLog;
````


## -struct-fields

### -field Type

This specifies the EVENTLOG_MESSAGE_QUALIFIERS type of event log message.


### -field LogToEventLog

If this value it set to 1, the message will be logged to the system event log.


### -field Size

This specifies the size of the Additional Data field.


### -field AdditionalData[1]

This provides additional information associated with this event.


## -remarks
We recommend that you implement this class.</p>