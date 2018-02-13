---
UID: NS:ks.KSEVENT_TIME_INTERVAL
title: KSEVENT_TIME_INTERVAL
author: windows-driver-content
description: The KSEVENT_TIME_INTERVAL structure is used in various events within the KSEVENTSETID_Clock event set.
old-location: stream\ksevent_time_interval.htm
old-project: stream
ms.assetid: 61699da0-2c34-44cb-8e1a-b266acfc7878
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: PKSEVENT_TIME_INTERVAL, KSEVENT_TIME_INTERVAL structure [Streaming Media Devices], ks/KSEVENT_TIME_INTERVAL, ks-struct_690ec7fd-ea7c-4a47-8351-779aa2cf8e2c.xml, ks/PKSEVENT_TIME_INTERVAL, PKSEVENT_TIME_INTERVAL structure pointer [Streaming Media Devices], *PKSEVENT_TIME_INTERVAL, stream.ksevent_time_interval, KSEVENT_TIME_INTERVAL
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ks.h
apiname:
-	KSEVENT_TIME_INTERVAL
product: Windows
targetos: Windows
req.typenames: KSEVENT_TIME_INTERVAL, *PKSEVENT_TIME_INTERVAL
---

# KSEVENT_TIME_INTERVAL structure


## -description


The KSEVENT_TIME_INTERVAL structure is used in various events within the <a href="https://msdn.microsoft.com/library/windows/hardware/ff561764">KSEVENTSETID_Clock</a> event set. 


## -syntax


````
typedef struct {
  KSEVENTDATA EventData;
  LONGLONG    TimeBase;
  LONGLONG    Interval;
} KSEVENT_TIME_INTERVAL, *PKSEVENT_TIME_INTERVAL;
````


## -struct-fields




### -field EventData

A structure of type <a href="..\ks\ns-ks-kseventdata.md">KSEVENTDATA</a> that specifies the standard event structure.


### -field TimeBase

Specifies the initial clock time when the event should be signaled.


### -field Interval

Specifies the subsequent interval when the event should continue to be signaled.


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff561764">KSEVENTSETID_Clock</a>



<a href="..\ks\ns-ks-ksevent_time_mark.md">KSEVENT_TIME_MARK</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSEVENT_TIME_INTERVAL structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

