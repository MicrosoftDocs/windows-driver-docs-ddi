---
UID: NF:ndis.NdisRetrieveUlong
title: NdisRetrieveUlong macro
author: windows-driver-content
description: The NdisRetrieveUlong function retrieves a ULONG value from the source address, avoiding alignment faults.
old-location: netvista\ndisretrieveulong.htm
old-project: netvista
ms.assetid: 41788885-d8a1-4459-82a0-261b39862530
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: NdisRetrieveUlong, NdisRetrieveUlong macro [Network Drivers Starting with Windows Vista], ndis/NdisRetrieveUlong, ndis_memory_ref_929d856f-6798-499a-aa9a-0f5e7181b972.xml, netvista.ndisretrieveulong
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ndis.h
api_name:
-	NdisRetrieveUlong
product:
- Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisRetrieveUlong macro


## -description


The 
  <b>NdisRetrieveUlong</b> function retrieves a ULONG value from the source address, avoiding alignment
  faults.


## -parameters




### -param Destination

TBD


### -param Source

TBD






#### - DestinationAddress [in]

A pointer to a ULONG-aligned memory location in which to store the value.


#### - SourceAddress [in]

A pointer to a memory location from which to retrieve the ULONG value.


## -remarks



The given 
    <i>DestinationAddress</i> is assumed to be aligned on a ULONG boundary.

Callers of 
    <b>NdisRetrieveUlong</b> can be running at any IRQL if the given addresses are in nonpaged pool.
    Otherwise, callers must be running at IRQL &lt; DISPATCH_LEVEL.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff564573">NdisStoreUlong</a>
 

 

