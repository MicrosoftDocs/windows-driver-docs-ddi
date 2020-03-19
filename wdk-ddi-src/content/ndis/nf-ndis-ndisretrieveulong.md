---
UID: NF:ndis.NdisRetrieveUlong
title: NdisRetrieveUlong macro (ndis.h)
description: The NdisRetrieveUlong function retrieves a ULONG value from the source address, avoiding alignment faults.
old-location: netvista\ndisretrieveulong.htm
tech.root: netvista
ms.assetid: 41788885-d8a1-4459-82a0-261b39862530
ms.date: 05/02/2018
keywords: ["NdisRetrieveUlong macro"]
ms.keywords: NdisRetrieveUlong, NdisRetrieveUlong macro [Network Drivers Starting with Windows Vista], ndis/NdisRetrieveUlong, ndis_memory_ref_929d856f-6798-499a-aa9a-0f5e7181b972.xml, netvista.ndisretrieveulong
f1_keywords:
 - "ndis/NdisRetrieveUlong"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for existing drivers in  NDIS 6.0 and later, but new drivers should use RtlRetrieveUlong instead.
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
req.irql: See Remarks section
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ndis.h
api_name:
- NdisRetrieveUlong
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisRetrieveUlong macro


## -description


The 
  <b>NdisRetrieveUlong</b> function retrieves a ULONG value from the source address, avoiding alignment
  faults.


## -parameters




### -param Destination

A pointer to a ULONG-aligned memory location in which to store the value.



### -param Source

A pointer to a memory location from which to retrieve the ULONG value.

## -remarks



The given 
    <i>DestinationAddress</i> is assumed to be aligned on a ULONG boundary.

Callers of 
    <b>NdisRetrieveUlong</b> can be running at any IRQL if the given addresses are in nonpaged pool.
    Otherwise, callers must be running at IRQL < DISPATCH_LEVEL.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisstoreulong">NdisStoreUlong</a>
 

 

