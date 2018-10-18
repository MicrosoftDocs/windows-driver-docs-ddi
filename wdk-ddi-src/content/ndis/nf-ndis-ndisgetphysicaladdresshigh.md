---
UID: NF:ndis.NdisGetPhysicalAddressHigh
title: NdisGetPhysicalAddressHigh macro
author: windows-driver-content
description: NdisGetPhysicalAddressHigh returns the high-order part of a given physical address.
old-location: netvista\ndisgetphysicaladdresshigh.htm
tech.root: netvista
ms.assetid: 17f8c6dd-7235-4ad0-bc3a-e801b53956ce
ms.date: 5/2/2018
ms.keywords: NdisGetPhysicalAddressHigh, NdisGetPhysicalAddressHigh macro [Network Drivers Starting with Windows Vista], miniport_memory_shared_ref_911e11c6-b90a-4805-83b9-0d75225917e0.xml, ndis/NdisGetPhysicalAddressHigh, netvista.ndisgetphysicaladdresshigh
ms.topic: macro
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ndis.h
api_name:
-	NdisGetPhysicalAddressHigh
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisGetPhysicalAddressHigh macro


## -description


<b>NdisGetPhysicalAddressHigh</b> returns the high-order part of a given physical address.


## -parameters




### -param _PhysicalAddress [in]

Specifies a physical address of an OS-dependent size.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff557129">NDIS_PHYSICAL_ADDRESS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562654">NdisGetPhysicalAddressLow</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564551">NdisSetPhysicalAddressHigh</a>
 

 

