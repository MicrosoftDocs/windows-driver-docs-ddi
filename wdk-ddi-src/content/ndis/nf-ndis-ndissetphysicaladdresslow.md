---
UID: NF:ndis.NdisSetPhysicalAddressLow
title: NdisSetPhysicalAddressLow macro
author: windows-driver-content
description: NdisSetPhysicalAddressLow sets the low-order part of a given physical address to a given value.
old-location: netvista\ndissetphysicaladdresslow.htm
tech.root: netvista
ms.assetid: 2454f923-15c5-43c8-8d62-eee000d89a10
ms.author: windowsdriverdev
ms.date: 5/2/2018
ms.keywords: NdisSetPhysicalAddressLow, NdisSetPhysicalAddressLow macro [Network Drivers Starting with Windows Vista], miniport_memory_shared_ref_b21e2206-bd6c-47b6-b518-31bcad459bbb.xml, ndis/NdisSetPhysicalAddressLow, netvista.ndissetphysicaladdresslow
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ndis.h
api_name:
-	NdisSetPhysicalAddressLow
product:
- Windows
targetos: Windows
req.typenames: 
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




<a href="https://msdn.microsoft.com/library/windows/hardware/ff557129">NDIS_PHYSICAL_ADDRESS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562654">NdisGetPhysicalAddressLow</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564551">NdisSetPhysicalAddressHigh</a>
 

 

