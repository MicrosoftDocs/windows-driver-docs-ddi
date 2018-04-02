---
UID: NF:ndis.NdisResetEvent
title: NdisResetEvent function
author: windows-driver-content
description: The NdisResetEvent function clears the Signaled state of a given event.
old-location: netvista\ndisresetevent.htm
old-project: netvista
ms.assetid: fba29b92-5735-4050-b690-3c25e4f57cd1
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: NdisResetEvent, NdisResetEvent function [Network Drivers Starting with Windows Vista], ndis/NdisResetEvent, ndis_event_ref_2970c5ca-b236-41e4-b156-c283f4f637f9.xml, netvista.ndisresetevent
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisResetEvent (NDIS 5.1)) in   Windows Vista. Supported for NDIS 5.1 drivers (see    NdisResetEvent (NDIS 5.1)) in   Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_Synch_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ndis.lib
-	ndis.dll
api_name:
-	NdisResetEvent
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisResetEvent function


## -description


The
  <b>NdisResetEvent</b> function clears the Signaled state of a given event.


## -parameters




### -param Event [in]

A pointer to an initialized event object for which the caller provided the storage.


## -returns



None




## -remarks



<b>NdisResetEvent</b> explicitly sets the state of the given event to 
    <i>not-signaled</i>.

When an event is set to the 
    <i>signaled</i> state with the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff564539">NdisSetEvent</a> function, it remains in that
    state until an explicit call to 
    <b>NdisResetEvent</b> occurs. While an event remains in the 
    <i>signaled</i> state, callers of the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff564651">NdisWaitEvent</a> function on that event are
    dispatched for execution without waiting.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff562732">NdisInitializeEvent</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564539">NdisSetEvent</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564651">NdisWaitEvent</a>
 

 

