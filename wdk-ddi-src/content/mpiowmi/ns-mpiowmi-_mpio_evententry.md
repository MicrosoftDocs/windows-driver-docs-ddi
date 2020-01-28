---
UID: NS:mpiowmi._MPIO_EventEntry
title: _MPIO_EventEntry (mpiowmi.h)
description: The MPIO_EventEntry structure is used to return events that MPIO has logged.
old-location: storage\mpio_evententry.htm
tech.root: storage
ms.assetid: de7fd19e-e18d-4e78-963a-3abdd7921d69
ms.date: 03/29/2018
ms.keywords: "*PMPIO_EventEntry, MPIO_EventEntry, MPIO_EventEntry structure [Storage Devices], PMPIO_EventEntry, PMPIO_EventEntry structure pointer [Storage Devices], _MPIO_EventEntry, mpiowmi/MPIO_EventEntry, mpiowmi/PMPIO_EventEntry, storage.mpio_evententry, structs-scsibus_93008bb2-e885-4f2f-b46a-7393794a9e6e.xml"
f1_keywords:
 - "mpiowmi/MPIO_EventEntry"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- mpiowmi.h
api_name:
- MPIO_EventEntry
product:
- Windows
targetos: Windows
req.typenames: MPIO_EventEntry, *PMPIO_EventEntry
---

# _MPIO_EventEntry structure


## -description


The MPIO_EventEntry structure is used to return events that MPIO has logged.


## -struct-fields




### -field TimeStamp

A 64-bitfield that specifies the timestamp for the event entry.


### -field Severity

A 32-bitfield that indicates the severity of the reported event.


### -field Component

A string that indicates the component to which this event belongs.


### -field EventDescription

A string that indicates the event description.

