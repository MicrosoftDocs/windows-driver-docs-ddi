---
UID: NS:ks.KSEVENT_TIME_INTERVAL
title: KSEVENT_TIME_INTERVAL
author: windows-driver-content
description: The KSEVENT_TIME_INTERVAL structure is used in various events within the KSEVENTSETID_Clock event set.
old-location: stream\ksevent_time_interval.htm
old-project: stream
ms.assetid: 61699da0-2c34-44cb-8e1a-b266acfc7878
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PKSEVENT_TIME_INTERVAL, KSEVENT_TIME_INTERVAL, KSEVENT_TIME_INTERVAL structure [Streaming Media Devices], PKSEVENT_TIME_INTERVAL, PKSEVENT_TIME_INTERVAL structure pointer [Streaming Media Devices], ks-struct_690ec7fd-ea7c-4a47-8351-779aa2cf8e2c.xml, ks/KSEVENT_TIME_INTERVAL, ks/PKSEVENT_TIME_INTERVAL, stream.ksevent_time_interval"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ks.h
api_name:
-	KSEVENT_TIME_INTERVAL
product: Windows
targetos: Windows
req.typenames: KSEVENT_TIME_INTERVAL, *PKSEVENT_TIME_INTERVAL
---

# KSEVENT_TIME_INTERVAL structure


## -description


The KSEVENT_TIME_INTERVAL structure is used in various events within the <a href="https://msdn.microsoft.com/library/windows/hardware/ff561764">KSEVENTSETID_Clock</a> event set. 


## -struct-fields




### -field EventData

A structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff561750">KSEVENTDATA</a> that specifies the standard event structure.


### -field TimeBase

Specifies the initial clock time when the event should be signaled.


### -field Interval

Specifies the subsequent interval when the event should continue to be signaled.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561764">KSEVENTSETID_Clock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561891">KSEVENT_TIME_MARK</a>
 

 

