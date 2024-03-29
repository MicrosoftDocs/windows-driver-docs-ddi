---
UID: NF:ndis.NdisGetPhysicalAddressHigh
title: NdisGetPhysicalAddressHigh macro (ndis.h)
description: NdisGetPhysicalAddressHigh returns the high-order part of a given physical address.
old-location: netvista\ndisgetphysicaladdresshigh.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["NdisGetPhysicalAddressHigh macro"]
ms.keywords: NdisGetPhysicalAddressHigh, NdisGetPhysicalAddressHigh macro [Network Drivers Starting with Windows Vista], miniport_memory_shared_ref_911e11c6-b90a-4805-83b9-0d75225917e0.xml, ndis/NdisGetPhysicalAddressHigh, netvista.ndisgetphysicaladdresshigh
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisGetPhysicalAddressHigh   (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisGetPhysicalAddressHigh   (NDIS 5.1)) in Windows XP.
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
targetos: Windows
req.typenames: 
f1_keywords:
 - NdisGetPhysicalAddressHigh
 - ndis/NdisGetPhysicalAddressHigh
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ndis.h
api_name:
 - NdisGetPhysicalAddressHigh
---

# NdisGetPhysicalAddressHigh macro


## -description

<b>NdisGetPhysicalAddressHigh</b> returns the high-order part of a given physical address.

## -parameters

### -param _PhysicalAddress [in]


Specifies a physical address of an OS-dependent size.

## -see-also

<a href="/previous-versions/windows/hardware/network/ff557129(v=vs.85)">NDIS_PHYSICAL_ADDRESS</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisgetphysicaladdresslow">NdisGetPhysicalAddressLow</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndissetphysicaladdresshigh">NdisSetPhysicalAddressHigh</a>
