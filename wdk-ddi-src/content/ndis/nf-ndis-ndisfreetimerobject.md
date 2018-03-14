---
UID: NF:ndis.NdisFreeTimerObject
title: NdisFreeTimerObject function
author: windows-driver-content
description: The NdisFreeTimerObject function frees a timer object that was allocated with the NdisAllocateTimerObject function.
old-location: netvista\ndisfreetimerobject.htm
old-project: netvista
ms.assetid: b3edeebb-7a8f-4cd2-bd52-1b8ce044caa2
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: NdisFreeTimerObject, NdisFreeTimerObject function [Network Drivers Starting with Windows Vista], ndis/NdisFreeTimerObject, ndis_timer_ref_0f4b2edb-47fb-481c-a1e9-6940d15cb354.xml, netvista.ndisfreetimerobject
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_Timer_Function
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
-	NdisFreeTimerObject
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisFreeTimerObject function


## -description


The 
  <b>NdisFreeTimerObject</b> function frees a timer object that was allocated with the 
  <a href="..\ndis\nf-ndis-ndisallocatetimerobject.md">
  NdisAllocateTimerObject</a> function.


## -syntax


````
VOID NdisFreeTimerObject(
  _In_ NDIS_HANDLE TimerObject
);
````


## -parameters




### -param TimerObject [in]

A handle to a timer object that NDIS provides when a driver calls the 
     <a href="..\ndis\nf-ndis-ndisallocatetimerobject.md">
     NdisAllocateTimerObject</a> function.


## -returns



None




## -remarks



To use timer services, an NDIS driver first calls the 
    <a href="..\ndis\nf-ndis-ndisallocatetimerobject.md">NdisAllocateTimerObject</a> function
    to initialize a timer object. Typically, 
    <b>NdisAllocateTimerObject</b> is called when a driver initializes. The driver must call 
    <b>NdisFreeTimerObject</b> to free the timer object when the timer is no longer required.

To cancel a timer, call the 
    <a href="..\ndis\nf-ndis-ndiscanceltimerobject.md">NdisCancelTimerObject</a> function. 
    <b>NdisCancelTimerObject</b> dequeues the timer object if it is currently queued.




## -see-also

<a href="..\ndis\nf-ndis-ndisallocatetimerobject.md">NdisAllocateTimerObject</a>



<a href="..\ndis\nf-ndis-ndiscanceltimerobject.md">NdisCancelTimerObject</a>



<a href="..\ndis\ns-ndis-_ndis_timer_characteristics.md">NDIS_TIMER_CHARACTERISTICS</a>



 

 


