---
UID: NF:ndis.NdisRetrieveUlong
title: NdisRetrieveUlong macro
author: windows-driver-content
description: The NdisRetrieveUlong function retrieves a ULONG value from the source address, avoiding alignment faults.
old-location: netvista\ndisretrieveulong.htm
old-project: netvista
ms.assetid: 41788885-d8a1-4459-82a0-261b39862530
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.ndisretrieveulong, ndis_memory_ref_929d856f-6798-499a-aa9a-0f5e7181b972.xml, NdisRetrieveUlong, NdisRetrieveUlong macro [Network Drivers Starting with Windows Vista], ndis/NdisRetrieveUlong
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
req.lib: ndis.h
req.dll: 
req.irql: See Remarks section
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ndis.h
apiname:
-	NdisRetrieveUlong
product: Windows
targetos: Windows
req.typenames: "*PNDIS_SHARED_MEMORY_USAGE, NDIS_SHARED_MEMORY_USAGE"
---

# NdisRetrieveUlong macro


## -description


The 
  <b>NdisRetrieveUlong</b> function retrieves a ULONG value from the source address, avoiding alignment
  faults.


## -syntax


````
VOID NdisRetrieveUlong(
  [in] PULONG DestinationAddress,
  [in] PULONG SourceAddress
);
````


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

<a href="..\ndis\nf-ndis-ndisstoreulong.md">NdisStoreUlong</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisRetrieveUlong macro%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

