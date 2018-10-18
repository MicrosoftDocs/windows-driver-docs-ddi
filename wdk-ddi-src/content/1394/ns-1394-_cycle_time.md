---
UID: NS:1394._CYCLE_TIME
title: "_CYCLE_TIME"
author: windows-driver-content
description: The CYCLE_TIME structure contains the IEEE 1394 isochronous cycle time.
old-location: ieee\cycle_time.htm
tech.root: IEEE
ms.assetid: dcb19338-3848-4f90-876c-357f92fb2637
ms.date: 2/15/2018
ms.keywords: "*PCYCLE_TIME, 1394/CYCLE_TIME, 1394/PCYCLE_TIME, 1394stct_c6b1a6fa-b259-488d-a4a9-e4dace0fcf3d.xml, CYCLE_TIME, CYCLE_TIME structure [Buses], IEEE.cycle_time, PCYCLE_TIME, PCYCLE_TIME structure pointer [Buses], _CYCLE_TIME"
ms.topic: struct
req.header: 1394.h
req.include-header: 1394.h
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
-	1394.h
api_name:
-	CYCLE_TIME
product:
- Windows
targetos: Windows
req.typenames: CYCLE_TIME, *PCYCLE_TIME
---

# _CYCLE_TIME structure


## -description


The CYCLE_TIME structure contains the IEEE 1394 isochronous cycle time.


## -struct-fields




### -field CL_CycleOffset

Specifies the number of clock ticks (based on a 24.576 MHz clock) since the current isochronous cycle began.


### -field CL_CycleCount

Specifies the number of isochronous cycles in the current second.


### -field CL_SecondCount

Specifies the number of seconds. This count wraps to zero every 128 seconds.


## -remarks



The layout of this structure matches that of the CYCLE_TIME register in the <i>IEEE 1394-1995 specification</i>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff537401">ISOCH_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537649">REQUEST_ISOCH_ALLOCATE_RESOURCES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537655">REQUEST_ISOCH_LISTEN</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537656">REQUEST_ISOCH_QUERY_CYCLE_TIME</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537660">REQUEST_ISOCH_TALK</a>
 

 

