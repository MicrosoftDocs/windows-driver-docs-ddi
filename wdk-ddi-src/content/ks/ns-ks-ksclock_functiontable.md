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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ks.h
api_name:
-	KSCLOCK_FUNCTIONTABLE
product:
- Windows
targetos: Windows
req.typenames: KSCLOCK_FUNCTIONTABLE, *PKSCLOCK_FUNCTIONTABLE
---

# KSCLOCK_FUNCTIONTABLE structure


## -description


The KSCLOCK_FUNCTIONTABLE structure describes a function table for the master clock.


## -struct-fields




### -field GetTime

Pointer to a driver-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/ff567161">KStrClockGetTime</a> routine.


### -field GetPhysicalTime

Pointer to a driver-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/ff567160">KStrClockGetPhysicalTime</a> routine.


### -field GetCorrelatedTime

Pointer to a driver-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/ff567159">KStrClockGetCorrelatedTime</a> routine.


### -field GetCorrelatedPhysicalTime

Pointer to a driver-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/ff567157">KStrClockGetCorrelatedPhysicalTime</a> routine. 


## -remarks



Supply this structure in a <a href="https://msdn.microsoft.com/library/windows/hardware/ff564466">KSPROPERTY_CLOCK_FUNCTIONTABLE</a> request. The property request then returns pointers to the requested routines.

The function pointers returned in this structure are valid until the clock's file object is released.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff564466">KSPROPERTY_CLOCK_FUNCTIONTABLE</a>
 

 

