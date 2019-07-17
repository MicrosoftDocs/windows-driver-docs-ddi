---
UID: NS:ks.__unnamed_struct_16
title: KSEVENT_TIME_MARK (ks.h)
description: The KSEVENT_TIME_MARK structure is used in various events within the KSEVENTSETID_Clock event set.
old-location: stream\ksevent_time_mark.htm
tech.root: stream
ms.assetid: c1e756a8-4850-4ddc-9bbf-97146a798554
ms.date: 04/23/2018
ms.keywords: "*PKSEVENT_TIME_MARK, KSEVENT_TIME_MARK, KSEVENT_TIME_MARK structure [Streaming Media Devices], PKSEVENT_TIME_MARK, PKSEVENT_TIME_MARK structure pointer [Streaming Media Devices], ks-struct_66e60015-261c-4e6d-a58f-dab8d50cf4d6.xml, ks/KSEVENT_TIME_MARK, ks/PKSEVENT_TIME_MARK, stream.ksevent_time_mark"
ms.topic: struct
f1_keywords:
 - "ks/KSEVENT_TIME_MARK"
req.header: ks.h
req.include-header: Ks.h
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
- ks.h
api_name:
- KSEVENT_TIME_MARK
product:
- Windows
targetos: Windows
req.typenames: KSEVENT_TIME_MARK, *PKSEVENT_TIME_MARK
---

# KSEVENT_TIME_MARK structure


## -description


The KSEVENT_TIME_MARK structure is used in various events within the <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/kseventsetid-clock">KSEVENTSETID_Clock</a> event set. 


## -struct-fields




### -field EventData

A structure of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-kseventdata">KSEVENTDATA</a> that specifies the standard event structure.


### -field MarkTime

Specifies the clock time when the event should be signaled.


## -remarks



The flags indicate the type of units for the interval. The interval can be specified in KSEVENT_DATA_MARKF_FILETIME units for these events, which are 100-nanosecond units.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/kseventsetid-clock">KSEVENTSETID_Clock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-ksevent_time_interval">KSEVENT_TIME_INTERVAL</a>
 

 

