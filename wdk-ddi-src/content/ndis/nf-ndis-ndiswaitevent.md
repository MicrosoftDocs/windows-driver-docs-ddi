---
UID: NF:ndis.NdisWaitEvent
title: NdisWaitEvent function
author: windows-driver-content
description: The NdisWaitEvent function puts the caller into a wait state until the given event is set to the Signaled state or the wait times out.
old-location: netvista\ndiswaitevent.htm
tech.root: netvista
ms.assetid: fefdb56f-6689-4a4f-a198-6108190624f0
ms.author: windowsdriverdev
ms.date: 5/2/2018
ms.keywords: NdisWaitEvent, NdisWaitEvent function [Network Drivers Starting with Windows Vista], ndis/NdisWaitEvent, ndis_event_ref_d607d02a-0509-4399-90e8-bbfb43d613b3.xml, netvista.ndiswaitevent
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisWaitEvent (NDIS 5.1)) in Windows   Vista. Supported for NDIS 5.1 drivers (see    NdisWaitEvent (NDIS 5.1)) in Windows   XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_Miscellaneous_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ndis.lib
-	ndis.dll
api_name:
-	NdisWaitEvent
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisWaitEvent function


## -description


The
  <b>NdisWaitEvent</b> function puts the caller into a wait state until the given event is set to the Signaled
  state or the wait times out.


## -parameters




### -param Event [in]

A pointer to an initialized event object for which the caller provides the storage.


### -param MsToWait [in]

The number of milliseconds the caller will wait if the event is not set to the 
     <i>signaled</i> state within that interval. A value of zero specifies that the caller will wait for the
     event indefinitely.


## -returns



<b>NdisWaitEvent</b> returns <b>TRUE</b> if the event is in the 
     <i>signaled</i> state when the wait is satisfied.




## -remarks



<b>NdisWaitEvent</b> returns control to its caller when the given event is signaled or the specified 
    <i>MsToWait</i> interval expires, whichever is sooner. If the event is currently in the 
    <i>signaled</i> state when this call occurs, 
    <b>NdisWaitEvent</b> returns control immediately.

A miniport driver typically calls 
    <b>NdisWaitEvent</b> from its 
    <a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a> and 
    <a href="https://msdn.microsoft.com/b8d452b4-bef3-4991-87cf-fac15bedfde4">MiniportHaltEx</a> functions. A protocol
    driver typically calls 
    <b>NdisWaitEvent</b> from its 
    <a href="https://msdn.microsoft.com/1958722e-012e-4110-a82c-751744bcf9b5">ProtocolBindAdapterEx</a> and 
    <a href="https://msdn.microsoft.com/19fa7be2-acb9-42f6-bd9f-5be3e3c8b5fa">
    ProtocolUnbindAdapterEx</a> functions.




## -see-also




<a href="https://msdn.microsoft.com/library/gg156036.aspx">DriverEntry of NDIS Protocol
   Drivers</a>



<a href="https://msdn.microsoft.com/b8d452b4-bef3-4991-87cf-fac15bedfde4">MiniportHaltEx</a>



<a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562732">NdisInitializeEvent</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564526">NdisResetEvent</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564539">NdisSetEvent</a>



<a href="https://msdn.microsoft.com/1958722e-012e-4110-a82c-751744bcf9b5">ProtocolBindAdapterEx</a>



<a href="https://msdn.microsoft.com/19fa7be2-acb9-42f6-bd9f-5be3e3c8b5fa">ProtocolUnbindAdapterEx</a>
 

 

