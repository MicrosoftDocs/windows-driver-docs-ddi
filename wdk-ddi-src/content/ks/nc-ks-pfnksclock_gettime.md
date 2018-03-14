---
UID: NC:ks.PFNKSCLOCK_GETTIME
title: PFNKSCLOCK_GETTIME
author: windows-driver-content
description: The routine gets system time.KStrClockGetTime is a system-supplied routine that retrieves the current system time.KStrClockGetPhysicalTime is a system-supplied routine that retrieves the current system time minus any suspended delta.
old-location: stream\kstrclockgettime.htm
old-project: stream
ms.assetid: 4b1028a1-8c86-4958-a19f-32c490dda790
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KStrClockGetPhysicalTime, KStrClockGetTime, PFNKSCLOCK_GETTIME, SystemClockGetTime, SystemClockGetTime routine [Streaming Media Devices], ks/SystemClockGetTime, ksfunc_a60a332c-ffc8-4969-9e81-cccaac9b5c0a.xml, stream.kstrclockgettime
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ks.h
req.include-header: Ks.h
req.target-type: Desktop
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
-	UserDefined
api_location:
-	ks.h
api_name:
-	SystemClockGetTime
product: Windows
targetos: Windows
req.typenames: SOUNDDETECTOR_PATTERNHEADER
---

# PFNKSCLOCK_GETTIME callback


## -description


The routine gets system time.

<i>KStrClockGetTime</i> is a system-supplied routine that retrieves the current system time.

<i>KStrClockGetPhysicalTime</i> is a system-supplied routine that retrieves the current system time minus any suspended delta.


## -prototype


````
PFNKSCLOCK_GETTIME SystemClockGetTime;

LONGLONG FASTCALL SystemClockGetTime(
  _In_ PFILE_OBJECT FileObject
)
{ ... }
````


## -parameters




### -param FileObject [in]

A pointer to the <a href="..\wdm\ns-wdm-_file_object.md">FILE_OBJECT</a> structure to which a handle was returned when the clock instance was created.


## -returns



This routine returns the requested time value as a value of type LONGLONG. This value is specified in 100 nanosecond units.




## -remarks



You can obtain an entry point for this routine by supplying a driver-allocated <a href="..\ks\ns-ks-ksclock_functiontable.md">KSCLOCK_FUNCTIONTABLE</a> structure in a <a href="https://msdn.microsoft.com/library/windows/hardware/ff564466">KSPROPERTY_CLOCK_FUNCTIONTABLE</a> request.




## -see-also

<a href="..\ks\ns-ks-ksclock_functiontable.md">KSCLOCK_FUNCTIONTABLE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564466">KSPROPERTY_CLOCK_FUNCTIONTABLE</a>



 

 


