---
UID: NF:ndis.NdisAllocateTimerObject
title: NdisAllocateTimerObject function (ndis.h)
description: The NdisAllocateTimerObject function allocates and initializes a timer object for use with subsequent NdisXxx timer functions.
old-location: netvista\ndisallocatetimerobject.htm
tech.root: netvista
ms.assetid: feb5e4cf-7e23-434e-9dc5-bb445a6f5606
ms.date: 05/02/2018
keywords: ["NdisAllocateTimerObject function"]
ms.keywords: NdisAllocateTimerObject, NdisAllocateTimerObject function [Network Drivers Starting with Windows Vista], ndis/NdisAllocateTimerObject, ndis_timer_ref_38e524b5-9210-4c60-b9ea-66fc23593dad.xml, netvista.ndisallocatetimerobject
f1_keywords:
 - "ndis/NdisAllocateTimerObject"
 - "NdisAllocateTimerObject"
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
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- ndis.lib
- ndis.dll
api_name:
- NdisAllocateTimerObject
targetos: Windows
req.typenames: 
---

# NdisAllocateTimerObject function


## -description


The 
  <b>NdisAllocateTimerObject</b> function allocates and initializes a timer object for use with subsequent 
  <b>Ndis<i>Xxx</i></b> timer functions.


## -parameters




### -param NdisHandle 
[in]
An NDIS handle that was obtained during caller initialization. For more information about
     obtaining NDIS handles, see 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/network/obtaining-pool-handles">Obtaining Pool Handles</a>.


### -param TimerCharacteristics 
[in]
A pointer to a caller-supplied 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_timer_characteristics">
     NDIS_TIMER_CHARACTERISTICS</a> structure that specifies the characteristics of the allocated timer
     object.


### -param pTimerObject 
[out]
A pointer to an NDIS timer object handle that NDIS provides to identify the timer object in
     subsequent calls to 
     <b>Ndis<i>Xxx</i></b> timer functions.


## -returns



<b>NdisAllocateTimerObject</b> returns one of the following status values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The timer object was allocated successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The allocation failed because of insufficient resources.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_BAD_CHARACTERISTICS</b></dt>
</dl>
</td>
<td width="60%">
The allocation failed because the information in the NDIS_TIMER_CHARACTERISTICS structure is
       invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_FAILURE</b></dt>
</dl>
</td>
<td width="60%">
None of the preceding status values apply.

</td>
</tr>
</table>
 




## -remarks



To use timer services, an NDIS driver first calls the 
    <b>NdisAllocateTimerObject</b> function to initialize a timer object. Typically, 
    <b>NdisAllocateTimerObject</b> is called during driver initialization.

To start a timer, call the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndissettimerobject">NdisSetTimerObject</a> function. Calls to 
    <b>NdisSetTimerObject</b> insert the timer object in the system timer queue. Only one instance of a
    particular timer object can be queued at any given moment.

To cancel a timer, call the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscanceltimerobject">NdisCancelTimerObject</a> function. 
    <b>NdisCancelTimerObject</b> dequeues the timer object if it is currently queued.

To free a timer object, you must call the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfreetimerobject">NdisFreeTimerObject</a> function.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_timer_characteristics">NDIS_TIMER_CHARACTERISTICS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscanceltimerobject">NdisCancelTimerObject</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfreetimerobject">NdisFreeTimerObject</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndissettimerobject">NdisSetTimerObject</a>
 

 

