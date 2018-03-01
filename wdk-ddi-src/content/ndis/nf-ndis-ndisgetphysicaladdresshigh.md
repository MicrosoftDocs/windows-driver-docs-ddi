---
UID: NF:ndis.NdisGetPhysicalAddressHigh
title: NdisGetPhysicalAddressHigh macro
author: windows-driver-content
description: NdisGetPhysicalAddressHigh returns the high-order part of a given physical address.
old-location: netvista\ndisgetphysicaladdresshigh.htm
old-project: netvista
ms.assetid: 17f8c6dd-7235-4ad0-bc3a-e801b53956ce
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: NdisGetPhysicalAddressHigh, NdisGetPhysicalAddressHigh macro [Network Drivers Starting with Windows Vista], miniport_memory_shared_ref_911e11c6-b90a-4805-83b9-0d75225917e0.xml, ndis/NdisGetPhysicalAddressHigh, netvista.ndisgetphysicaladdresshigh
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.lib: ndis.h
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
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisGetPhysicalAddressHigh macro


## -description


<b>NdisGetPhysicalAddressHigh</b> returns the high-order part of a given physical address.


## -syntax


````
ULONG NdisGetPhysicalAddressHigh(
  [in] NDIS_PHYSICAL_ADDRESS PhysicalAddress
);
````


## -parameters




### -param _PhysicalAddress [in]

Specifies a physical address of an OS-dependent size.


## -see-also

<a href="..\ndis\nf-ndis-ndisgetphysicaladdresslow.md">NdisGetPhysicalAddressLow</a>



<a href="..\ndis\nf-ndis-ndissetphysicaladdresshigh.md">NdisSetPhysicalAddressHigh</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557129">NDIS_PHYSICAL_ADDRESS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisGetPhysicalAddressHigh macro%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

