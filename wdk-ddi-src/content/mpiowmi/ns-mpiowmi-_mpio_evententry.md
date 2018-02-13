---
UID: NS:mpiowmi._MPIO_EventEntry
title: "_MPIO_EventEntry"
author: windows-driver-content
description: The MPIO_EventEntry structure is used to return events that MPIO has logged.
old-location: storage\mpio_evententry.htm
old-project: storage
ms.assetid: de7fd19e-e18d-4e78-963a-3abdd7921d69
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: MPIO_EventEntry structure [Storage Devices], storage.mpio_evententry, MPIO_EventEntry, structs-scsibus_93008bb2-e885-4f2f-b46a-7393794a9e6e.xml, *PMPIO_EventEntry, _MPIO_EventEntry, PMPIO_EventEntry structure pointer [Storage Devices], mpiowmi/PMPIO_EventEntry, PMPIO_EventEntry, mpiowmi/MPIO_EventEntry
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: mpiowmi.h
req.include-header: Mpiowmi.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	mpiowmi.h
apiname:
-	MPIO_EventEntry
product: Windows
targetos: Windows
req.typenames: MPIO_EventEntry, *PMPIO_EventEntry
---

# _MPIO_EventEntry structure


## -description


The MPIO_EventEntry structure is used to return events that MPIO has logged.


## -syntax


````
typedef struct _MPIO_EventEntry {
  ULONGLONG TimeStamp;
  ULONG     Severity;
  WCHAR     Component[63 + 1];
  WCHAR     EventDescription[63 + 1];
} MPIO_EventEntry, *PMPIO_EventEntry;
````


## -struct-fields




### -field TimeStamp

A 64-bitfield that specifies the timestamp for the event entry.


### -field Severity

A 32-bitfield that indicates the severity of the reported event.


### -field Component

A string that indicates the component to which this event belongs.


### -field EventDescription

A string that indicates the event description.

