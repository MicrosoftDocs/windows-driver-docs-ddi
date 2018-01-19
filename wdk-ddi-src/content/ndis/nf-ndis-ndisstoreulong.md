---
UID: NF:ndis.NdisStoreUlong
title: NdisStoreUlong macro
author: windows-driver-content
description: The NdisStoreUlong function stores a ULONG value at a particular address, avoiding alignment faults.
old-location: netvista\ndisstoreulong.htm
old-project: netvista
ms.assetid: 4fb0b803-1fe2-409b-8543-dddc5df67fe4
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: NdisStoreUlong
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for existing drivers in  NDIS 6.0 and later, but new drivers should use RtlStoreUlong instead.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisStoreUlong
req.alt-loc: ndis.h
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
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisStoreUlong macro



## -description
The 
  <b>NdisStoreUlong</b> function stores a ULONG value at a particular address, avoiding alignment
  faults.



## -syntax

````
VOID NdisStoreUlong(
  [in] PULONG DestinationAddress,
  [in] ULONG  Value
);
````


## -parameters

### -param DestinationAddress [in]

A pointer to a location in which to store a given ULONG value.


### -param Value [in]

The value to be stored.


## -remarks
Callers of 
    <b>NdisStoreUlong</b> can be running at any IRQL if 
    <i>DestinationAddress</i> points to nonpaged pool. Otherwise, the caller must be running at IRQL &lt;
    DISPATCH_LEVEL.


## -see-also
<dl>
<dt>
<a href="..\ndis\nf-ndis-ndisretrieveulong.md">NdisRetrieveUlong</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisStoreUlong macro%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

