---
UID: NF:ndis.NdisStoreUlong
title: NdisStoreUlong macro (ndis.h)
description: The NdisStoreUlong function stores a ULONG value at a particular address, avoiding alignment faults.
old-location: netvista\ndisstoreulong.htm
tech.root: netvista
ms.assetid: 4fb0b803-1fe2-409b-8543-dddc5df67fe4
ms.date: 05/02/2018
ms.keywords: NdisStoreUlong, NdisStoreUlong macro [Network Drivers Starting with Windows Vista], ndis/NdisStoreUlong, ndis_memory_ref_99349378-c2ab-4f96-82a3-7d76b15aaca3.xml, netvista.ndisstoreulong
ms.topic: macro
f1_keywords:
 - "ndis/NdisStoreUlong"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for existing drivers in  NDIS 6.0 and later, but new drivers should use RtlStoreUlong instead.
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
- NdisStoreUlong
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisStoreUlong macro


## -description


The 
  <b>NdisStoreUlong</b> function stores a ULONG value at a particular address, avoiding alignment
  faults.


## -parameters




### -param Destination

A pointer to a location in which to store a given ULONG value.

### -param Value [in]

The value to be stored.


## -remarks



Callers of 
    <b>NdisStoreUlong</b> can be running at any IRQL if 
    <i>DestinationAddress</i> points to nonpaged pool. Otherwise, the caller must be running at IRQL <
    DISPATCH_LEVEL.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisretrieveulong">NdisRetrieveUlong</a>
 

 

