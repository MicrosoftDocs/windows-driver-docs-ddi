---
UID: NC:ndis.NDIS_PD_FREE_COUNTER
title: NDIS_PD_FREE_COUNTER (ndis.h)
description: The PacketDirect (PD) platform calls a PD-capable miniport driver's NdisPDFreeCounter function to free a counter object.
old-location: netvista\ndispdfreecounter.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["NDIS_PD_FREE_COUNTER callback function"]
ms.keywords: NDIS_PD_FREE_COUNTER, NDIS_PD_FREE_COUNTER callback, NdisPDFreeCounter, NdisPDFreeCounter callback function [Network Drivers Starting with Windows Vista], ndis/NdisPDFreeCounter, netvista.ndispdfreecounter
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
targetos: Windows
req.typenames: 
f1_keywords:
 - NDIS_PD_FREE_COUNTER
 - ndis/NDIS_PD_FREE_COUNTER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Ndis.h
api_name:
 - NDIS_PD_FREE_COUNTER
---

# NDIS_PD_FREE_COUNTER callback function


## -description

The PacketDirect (PD) platform calls a PD-capable miniport driver's 
   <i>NdisPDFreeCounter</i> function to free a counter object.<div class="alert"><b>Note</b>  You must declare the function by using the <b>NDIS_PD_FREE_COUNTER</b> type. For more
   information, see the following Examples section.</div>
<div> </div>

## -parameters

### -param CounterHandle [in]


A counter handle that the miniport driver allocated in its <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-ndis_pd_allocate_counter">NdisPDAllocateCounter</a> function.

## -returns

This callback function does not return a value.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-ndis_pd_allocate_counter">NdisPDAllocateCounter</a>

