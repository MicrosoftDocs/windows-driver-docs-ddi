---
UID: NS:ndis._NDIS_TIMER_CHARACTERISTICS
title: _NDIS_TIMER_CHARACTERISTICS (ndis.h)
description: The NDIS_TIMER_CHARACTERISTICS structure defines characteristics of a one-shot or periodic timer.
old-location: netvista\ndis_timer_characteristics.htm
tech.root: netvista
ms.assetid: 9a62e94c-f635-4ab7-b439-b98c60ba2854
ms.date: 05/02/2018
keywords: ["_NDIS_TIMER_CHARACTERISTICS structure"]
ms.keywords: "*PNDIS_TIMER_CHARACTERISTICS, NDIS_TIMER_CHARACTERISTICS, NDIS_TIMER_CHARACTERISTICS structure [Network Drivers Starting with Windows Vista], PNDIS_TIMER_CHARACTERISTICS, PNDIS_TIMER_CHARACTERISTICS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_TIMER_CHARACTERISTICS, ndis/NDIS_TIMER_CHARACTERISTICS, ndis/PNDIS_TIMER_CHARACTERISTICS, ndis_timer_ref_af673f64-aa72-4767-81a0-5df465a52c81.xml, netvista.ndis_timer_characteristics"
f1_keywords:
 - "ndis/NDIS_TIMER_CHARACTERISTICS"
 - "NDIS_TIMER_CHARACTERISTICS"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ndis.h
api_name:
- NDIS_TIMER_CHARACTERISTICS
targetos: Windows
req.typenames: NDIS_TIMER_CHARACTERISTICS, *PNDIS_TIMER_CHARACTERISTICS
---

# _NDIS_TIMER_CHARACTERISTICS structure


## -description


The NDIS_TIMER_CHARACTERISTICS structure defines characteristics of a one-shot or periodic
  timer.


## -struct-fields




### -field Header

The 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure for the
     NDIS_TIMER_CHARACTERISTICS structure. Set the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_TIMER_CHARACTERISTICS, the 
     <b>Revision</b> member to NDIS_TIMER_CHARACTERISTICS_REVISION_1, and the 
     <b>Size</b> member to NDIS_SIZEOF_TIMER_CHARACTERISTICS_REVISION_1.


### -field AllocationTag

A string that is delimited by single quotation marks and contains up to four characters, usually
     specified in reversed order. You must provide this tag. NDIS uses this tag when it allocates memory for
     the timer.


### -field TimerFunction

A pointer to an entry point for a 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-ndis_timer_function">NetTimerCallback</a> function. NDIS calls
     this function when a timer fires.


### -field FunctionContext

A pointer to a driver-allocated context area. NDIS passes this pointer to the 
     <i>NetTimerCallback</i> function when a timer fires.


## -remarks



To allocate and initialize a timer object, NDIS drivers call the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatetimerobject">NdisAllocateTimerObject</a> function
    and provide an NDIS_TIMER_CHARACTERISTICS structure. The timer does not start until the driver calls the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndissettimerobject">NdisSetTimerObject</a> function.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatetimerobject">NdisAllocateTimerObject</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndissettimerobject">NdisSetTimerObject</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-ndis_timer_function">NetTimerCallback</a>
 

 

