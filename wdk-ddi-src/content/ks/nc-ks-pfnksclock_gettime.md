---
UID: NC:ks.PFNKSCLOCK_GETTIME
title: PFNKSCLOCK_GETTIME
author: windows-driver-content
description: KStrClockGetTime is a system-supplied routine that retrieves the current system time.
old-location: stream\kstrclockgettime.htm
old-project: stream
ms.assetid: 4b1028a1-8c86-4958-a19f-32c490dda790
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: stream.kstrclockgettime, KStrClockGetTime, KStrClockGetTime routine [Streaming Media Devices], KStrClockGetTime, PFNKSCLOCK_GETTIME, PFNKSCLOCK_GETTIME, ks/KStrClockGetTime, ksfunc_a60a332c-ffc8-4969-9e81-cccaac9b5c0a.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	ks.h
apiname:
-	KStrClockGetTime
product: Windows
targetos: Windows
req.typenames: KEYWORDSELECTOR
---

# PFNKSCLOCK_GETTIME callback


## -description


<i>KStrClockGetTime</i> is a system-supplied routine that retrieves the current system time.


## -prototype


````
PFNKSCLOCK_GETTIME KStrClockGetTime;

LONGLONG FASTCALL KStrClockGetTime(
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

<a href="https://msdn.microsoft.com/library/windows/hardware/ff564466">KSPROPERTY_CLOCK_FUNCTIONTABLE</a>



<a href="..\ks\ns-ks-ksclock_functiontable.md">KSCLOCK_FUNCTIONTABLE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20PFNKSCLOCK_GETTIME routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

