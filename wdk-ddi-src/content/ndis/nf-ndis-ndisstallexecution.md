---
UID: NF:ndis.NdisStallExecution
title: NdisStallExecution macro
author: windows-driver-content
description: The NdisStallExecution function stalls the caller on the current processor for a given interval.
old-location: netvista\ndisstallexecution.htm
tech.root: netvista
ms.assetid: 590f5a1a-fd78-408e-b4f0-555f08694c43
ms.date: 5/2/2018
ms.keywords: NdisStallExecution, NdisStallExecution macro [Network Drivers Starting with Windows Vista], ndis/NdisStallExecution, ndis_delay_ref_de9bdd45-0bed-44cc-bdce-3ecd81842010.xml, netvista.ndisstallexecution
ms.topic: macro
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisStallExecution (NDIS 5.1))   in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisStallExecution (NDIS 5.1))   in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: NdisStallExecution_Delay
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: Any level
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ndis.h
api_name:
-	NdisStallExecution
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisStallExecution macro


## -description


The 
  <b>NdisStallExecution</b> function stalls the caller on the current processor for a given interval.


## -parameters




### -param MicroSecondsToStall

The number of microseconds to delay. A driver should specify no more than 50 microseconds.


## -remarks



<b>NdisStallExecution</b> is a processor-dependent function that busy-waits for at least the specified
    number of microseconds, but not significantly longer.

This function should be called by drivers that must wait for an interval of more than a few
    instructions but less than 50 microseconds. Drivers that call this routine should minimize the number of
    microseconds that they specify.

If a driver must wait for an interval longer than 50 microseconds, it should call the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff563677">NdisMSleep</a> function. Note that callers of 
    <b>NdisMSleep</b> run at IRQL &lt; DISPATCH_LEVEL.




## -see-also




<a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a>



<a href="https://msdn.microsoft.com/15f82163-a1b5-4cef-a53e-8a97adb2cd92">MiniportResetEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563677">NdisMSleep</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564563">NdisSetTimerObject</a>
 

 

