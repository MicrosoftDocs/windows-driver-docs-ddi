---
UID: NF:ndis.NdisGetPhysicalAddressLow
title: NdisGetPhysicalAddressLow macro
author: windows-driver-content
description: NdisGetPhysicalAddressLow returns the low-order part of a given physical address.
old-location: netvista\ndisgetphysicaladdresslow.htm
old-project: netvista
ms.assetid: a2e9e398-7b47-49eb-b587-7c42a0162f90
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: miniport_memory_shared_ref_20e686ee-bdd4-484d-b3c5-af6bbb764059.xml, netvista.ndisgetphysicaladdresslow, ndis/NdisGetPhysicalAddressLow, NdisGetPhysicalAddressLow, NdisGetPhysicalAddressLow macro [Network Drivers Starting with Windows Vista]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
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
req.lib: ndis.h
req.dll: 
req.irql: Any level
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ndis.h
apiname:
-	NdisGetPhysicalAddressLow
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisGetPhysicalAddressLow macro


## -description


<b>NdisGetPhysicalAddressLow</b> returns the low-order part of a given physical address.


## -syntax


````
ULONG NdisGetPhysicalAddressLow(
  [in] NDIS_PHYSICAL_ADDRESS PhysicalAddress
);
````


## -parameters




### -param _PhysicalAddress [in]

Specifies a physical address of an OS-dependent size.


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff557129">NDIS_PHYSICAL_ADDRESS</a>

<a href="..\ndis\nf-ndis-ndissetphysicaladdresslow.md">NdisSetPhysicalAddressLow</a>

<a href="..\ndis\nf-ndis-ndisgetphysicaladdresshigh.md">NdisGetPhysicalAddressHigh</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisGetPhysicalAddressLow macro%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

