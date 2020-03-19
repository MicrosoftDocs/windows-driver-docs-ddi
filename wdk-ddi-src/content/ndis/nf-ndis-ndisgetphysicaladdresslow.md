---
UID: NF:ndis.NdisGetPhysicalAddressLow
title: NdisGetPhysicalAddressLow macro (ndis.h)
description: NdisGetPhysicalAddressLow returns the low-order part of a given physical address.
old-location: netvista\ndisgetphysicaladdresslow.htm
tech.root: netvista
ms.assetid: a2e9e398-7b47-49eb-b587-7c42a0162f90
ms.date: 05/02/2018
keywords: ["NdisGetPhysicalAddressLow macro"]
ms.keywords: NdisGetPhysicalAddressLow, NdisGetPhysicalAddressLow macro [Network Drivers Starting with Windows Vista], miniport_memory_shared_ref_20e686ee-bdd4-484d-b3c5-af6bbb764059.xml, ndis/NdisGetPhysicalAddressLow, netvista.ndisgetphysicaladdresslow
f1_keywords:
 - "ndis/NdisGetPhysicalAddressLow"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisGetPhysicalAddressLow (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisGetPhysicalAddressLow (NDIS   5.1)) in Windows XP.
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
req.irql: Any level
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ndis.h
api_name:
- NdisGetPhysicalAddressLow
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisGetPhysicalAddressLow macro


## -description


<b>NdisGetPhysicalAddressLow</b> returns the low-order part of a given physical address.


## -parameters




### -param _PhysicalAddress [in]

Specifies a physical address of an OS-dependent size.


## -see-also




<a href="https://docs.microsoft.com/previous-versions/windows/hardware/network/ff557129(v=vs.85)">NDIS_PHYSICAL_ADDRESS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisgetphysicaladdresshigh">NdisGetPhysicalAddressHigh</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndissetphysicaladdresslow">NdisSetPhysicalAddressLow</a>
 

 

