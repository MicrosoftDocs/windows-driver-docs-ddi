---
UID: NF:ndis.NdisSetPhysicalAddressLow
title: NdisSetPhysicalAddressLow macro (ndis.h)
description: NdisSetPhysicalAddressLow sets the low-order part of a given physical address to a given value.
old-location: netvista\ndissetphysicaladdresslow.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["NdisSetPhysicalAddressLow macro"]
ms.keywords: NdisSetPhysicalAddressLow, NdisSetPhysicalAddressLow macro [Network Drivers Starting with Windows Vista], miniport_memory_shared_ref_b21e2206-bd6c-47b6-b518-31bcad459bbb.xml, ndis/NdisSetPhysicalAddressLow, netvista.ndissetphysicaladdresslow
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisSetPhysicalAddressLow (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisSetPhysicalAddressLow (NDIS   5.1)) in Windows XP.
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
 - NdisSetPhysicalAddressLow
 - ndis/NdisSetPhysicalAddressLow
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ndis.h
api_name:
 - NdisSetPhysicalAddressLow
---

# NdisSetPhysicalAddressLow macro


## -description

<b>NdisSetPhysicalAddressLow</b> sets the low-order part of a given physical address to a given
  value.

## -parameters

### -param _PhysicalAddress [in]


Specifies a physical address of an OS-dependent size.

### -param _Value [in]


Specifies the value to be written into the low-order part of the address.

## -see-also

<a href="/previous-versions/windows/hardware/network/ff557129(v=vs.85)">NDIS_PHYSICAL_ADDRESS</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisgetphysicaladdresslow">NdisGetPhysicalAddressLow</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndissetphysicaladdresshigh">NdisSetPhysicalAddressHigh</a>
