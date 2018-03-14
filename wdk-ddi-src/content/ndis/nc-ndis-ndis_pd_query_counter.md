---
UID: NC:ndis.NDIS_PD_QUERY_COUNTER
title: NDIS_PD_QUERY_COUNTER
author: windows-driver-content
description: The PacketDirect (PD) platform calls a PD-capable miniport driver's NdisPDQueryCounter function to query the current values stored in a counter object.
old-location: netvista\ndispdquerycounter.htm
old-project: netvista
ms.assetid: C4860A43-2C53-4967-81A8-41FFF5CD2A5E
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: NDIS_PD_QUERY_COUNTER, NdisPDQueryCounter, NdisPDQueryCounter callback function [Network Drivers Starting with Windows Vista], ndis/NdisPDQueryCounter, netvista.ndispdquerycounter
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ndis.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Ndis.h
api_name:
-	NdisPDQueryCounter
product: Windows
targetos: Windows
req.typenames: VIDEO_STREAM_INIT_PARMS, *LPVIDEO_STREAM_INIT_PARMS
---

# NDIS_PD_QUERY_COUNTER callback


## -description


The PacketDirect (PD) platform calls a PD-capable miniport driver's 
   <i>NdisPDQueryCounter</i> function to query the current values stored in a counter object.<div class="alert"><b>Note</b>  You must declare the function by using the <b>NDIS_PD_QUERY_COUNTER</b> type. For more
   information, see the following Examples section.</div>
<div> </div>



## -prototype


````
NDIS_PD_QUERY_COUNTER NdisPDQueryCounter;

void NdisPDQueryCounter(
  _In_  NDIS_PD_COUNTER_HANDLE CounterHandle,
  _Out_ NDIS_PD_COUNTER_VALUE  *CounterValue
)
{ ... }
````


## -parameters




### -param CounterHandle [in]

A counter handle that the miniport driver allocated in its <a href="..\ndis\nc-ndis-ndis_pd_allocate_counter.md">NdisPDAllocateCounter</a> function.


### -param CounterValue [out]

The miniport returns a pointer to a <a href="..\ndis\ns-ndis-_ndis_pd_counter_value.md">NDIS_PD_COUNTER_VALUE</a> structure that contains the values stored in  the counter object.


## -returns



This callback function does not return a value.




## -see-also

<a href="..\ndis\ns-ndis-_ndis_pd_counter_value.md">NDIS_PD_COUNTER_VALUE</a>



 

 


