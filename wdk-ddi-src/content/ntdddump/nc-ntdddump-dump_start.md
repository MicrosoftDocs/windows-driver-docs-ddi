---
UID: NC:ntdddump.DUMP_START
title: DUMP_START (ntdddump.h)
description: The Dump_Start callback routine is called after initializing the dump driver and just before starting the dump write process.
old-location: storage\dump_start.htm
tech.root: storage
ms.assetid: a315f51f-069a-4c3d-bedc-2378b0996022
ms.date: 03/29/2018
keywords: ["DUMP_START callback function"]
ms.keywords: Dump_Start, Dump_Start routine [Storage Devices], PDUMP_START, filter_rtns_071f1e6c-9471-47ef-bf40-6429a798b792.xml, ntdddump/Dump_Start, storage.dump_start
f1_keywords:
 - "ntdddump/Dump_Start"
 - "Dump_Start"
req.header: ntdddump.h
req.include-header: Ntdddump.h
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows Vista and Windows Server 2008.
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
- UserDefined
api_location:
- ntdddump.h
api_name:
- Dump_Start
targetos: Windows
req.typenames: 
---

# DUMP_START callback function


## -description


The <i>Dump_Start</i> callback routine is called after initializing the dump driver and just before starting the dump write process.


## -parameters




### -param FilterExtension 
[in]
A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntdddump/ns-ntdddump-_filter_extension">FILTER_EXTENSION</a> structure.


## -returns



If the routine succeeds, it must return STATUS_SUCCESS. Otherwise, it must return one of the error status values that are defined in <i>Ntstatus.h</i>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntdddump/ns-ntdddump-_filter_extension">FILTER_EXTENSION</a>
 

 

