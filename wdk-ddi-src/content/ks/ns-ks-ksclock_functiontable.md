---
UID: NS:ks.KSCLOCK_FUNCTIONTABLE
title: KSCLOCK_FUNCTIONTABLE
author: windows-driver-content
description: The KSCLOCK_FUNCTIONTABLE structure describes a function table for the master clock.
old-location: stream\ksclock_functiontable.htm
old-project: stream
ms.assetid: ed16588e-1c63-411d-b5c8-a8151a218328
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PKSCLOCK_FUNCTIONTABLE, KSCLOCK_FUNCTIONTABLE, KSCLOCK_FUNCTIONTABLE structure [Streaming Media Devices], PKSCLOCK_FUNCTIONTABLE, PKSCLOCK_FUNCTIONTABLE structure pointer [Streaming Media Devices], ks-struct_b86dda38-016f-4116-9770-5b447c664b2e.xml, ks/KSCLOCK_FUNCTIONTABLE, ks/PKSCLOCK_FUNCTIONTABLE, stream.ksclock_functiontable"
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
-	KSCLOCK_FUNCTIONTABLE
product: Windows
targetos: Windows
req.typenames: KSCLOCK_FUNCTIONTABLE, *PKSCLOCK_FUNCTIONTABLE
---

# KSCLOCK_FUNCTIONTABLE structure


## -description


The KSCLOCK_FUNCTIONTABLE structure describes a function table for the master clock.


## -syntax


````
typedef struct {
  PFNKSCLOCK_GETTIME        GetTime;
  PFNKSCLOCK_GETTIME        GetPhysicalTime;
  PFNKSCLOCK_CORRELATEDTIME GetCorrelatedTime;
  PFNKSCLOCK_CORRELATEDTIME GetCorrelatedPhysicalTime;
} KSCLOCK_FUNCTIONTABLE, *PKSCLOCK_FUNCTIONTABLE;
````


## -struct-fields




### -field GetTime

Pointer to a driver-allocated <a href="..\ks\nc-ks-pfnksclock_gettime.md">KStrClockGetTime</a> routine.


### -field GetPhysicalTime

Pointer to a driver-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/ff567160">KStrClockGetPhysicalTime</a> routine.


### -field GetCorrelatedTime

Pointer to a driver-allocated <a href="..\ks\nc-ks-pfnksclock_correlatedtime.md">KStrClockGetCorrelatedTime</a> routine.


### -field GetCorrelatedPhysicalTime

Pointer to a driver-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/ff567157">KStrClockGetCorrelatedPhysicalTime</a> routine. 


## -remarks



Supply this structure in a <a href="https://msdn.microsoft.com/library/windows/hardware/ff564466">KSPROPERTY_CLOCK_FUNCTIONTABLE</a> request. The property request then returns pointers to the requested routines.

The function pointers returned in this structure are valid until the clock's file object is released.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff564466">KSPROPERTY_CLOCK_FUNCTIONTABLE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSCLOCK_FUNCTIONTABLE structure%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

