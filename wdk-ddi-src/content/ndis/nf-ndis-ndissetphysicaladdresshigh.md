---
UID: NF:ndis.NdisSetPhysicalAddressHigh
title: NdisSetPhysicalAddressHigh macro
description: NdisSetPhysicalAddressHigh sets the high-order part of a given physical address to a given value.
old-location: netvista\ndissetphysicaladdresshigh.htm
tech.root: netvista
ms.assetid: bbe58583-ea65-4920-9056-ab46bd881618
ms.date: 05/02/2018
ms.keywords: NdisSetPhysicalAddressHigh, NdisSetPhysicalAddressHigh macro [Network Drivers Starting with Windows Vista], miniport_memory_shared_ref_4644a620-5ec7-449e-9886-ddee46d9ff2a.xml, ndis/NdisSetPhysicalAddressHigh, netvista.ndissetphysicaladdresshigh
ms.topic: macro
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisSetPhysicalAddressHigh   (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisSetPhysicalAddressHigh   (NDIS 5.1)) in Windows XP.
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ndis.h
api_name:
-	NdisSetPhysicalAddressHigh
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisSetPhysicalAddressHigh macro


## -description


<b>NdisSetPhysicalAddressHigh</b> sets the high-order part of a given physical address to a given
  value.


## -parameters




### -param _PhysicalAddress [in]

Specifies a physical address of an OS-dependent size.


### -param _Value [in]

Specifies the value to be written into the high-order part of the address.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff557129">NDIS_PHYSICAL_ADDRESS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562650">NdisGetPhysicalAddressHigh</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564556">NdisSetPhysicalAddressLow</a>
 

 

