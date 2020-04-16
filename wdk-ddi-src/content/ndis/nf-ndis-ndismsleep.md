---
UID: NF:ndis.NdisMSleep
title: NdisMSleep function (ndis.h)
description: The NdisMSleep function delays execution of the caller for a given interval in microseconds.
old-location: netvista\ndismsleep.htm
tech.root: netvista
ms.assetid: 5b6c3fc5-4220-4a4b-9412-8bfc8141ea90
ms.date: 05/02/2018
keywords: ["NdisMSleep function"]
ms.keywords: NdisMSleep, NdisMSleep function [Network Drivers Starting with Windows Vista], ndis/NdisMSleep, ndis_delay_ref_81af917a-626a-493f-97ed-c4ce48999b12.xml, netvista.ndismsleep
f1_keywords:
 - "ndis/NdisMSleep"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisMSleep (NDIS 5.1)) in Windows   Vista. Supported for NDIS 5.1 drivers (see    NdisMSleep (NDIS 5.1)).
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_Miniport_Driver_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: < DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- ndis.lib
- ndis.dll
api_name:
- NdisMSleep
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisMSleep function


## -description


The 
  <b>NdisMSleep</b> function delays execution of the caller for a given interval in microseconds.


## -parameters




### -param MicrosecondsToSleep [in]

The number of microseconds to delay.


## -remarks



For the given time in the 
    <i>MicrosecondsToSleep</i> parameter, the caller's thread of execution is put into a wait state, thereby
    allowing other threads to get work done on the current processor. When the given interval expires, the
    caller of 
    <b>NdisMSleep</b> resumes execution.

An NDIS driver should always call 
    <b>NdisMSleep</b> in preference to the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisstallexecution">NdisStallExecution</a> function unless the
    driver is running at IRQL >= DISPATCH_LEVEL. 
    <b>NdisMSleep</b> can accept a larger delay interval than 
    <b>NdisStallExecution</b>, which should 
    <u>never</u> be called with an interval greater than 50 microseconds. Do not call <b>NdisMSleep</b> with a timeout of more than 30,000,000 microseconds (that is, 30 seconds or half a minute).

Miniport drivers can call 
    <b>NdisMSleep</b> from their 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a> and,
    possibly, 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_halt">MiniportHaltEx</a> functions when either
    function must wait for state changes to occur in the NIC before that function continues its
    operations.

Both 
    <b>NdisMSleep</b> and 
    <b>NdisStallExecution</b> allow a miniport driver to specify a delay consistently and independently of the
    clock speed of the host CPU. Neither function involves a timer object such as those that are used by the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndissettimerobject">NdisSetTimerObject</a> function. The
    resolution of the host system clock varies, so very short delays can take slightly longer than the delay
    time that the caller of 
    <b>NdisMSleep</b> or 
    <b>NdisStallExecution</b> specified.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_halt">MiniportHaltEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndissettimerobject">NdisSetTimerObject</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisstallexecution">NdisStallExecution</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiswaitevent">NdisWaitEvent</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-ndis_timer_function">NetTimerCallback</a>
 

 

