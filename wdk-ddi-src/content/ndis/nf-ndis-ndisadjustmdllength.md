---
UID: NF:ndis.NdisAdjustMdlLength
title: NdisAdjustMdlLength macro
author: windows-driver-content
description: The NdisAdjustMdlLength function modifies the length of the data that is associated with an MDL.
old-location: netvista\ndisadjustmdllength.htm
old-project: netvista
ms.assetid: d52d985c-3ebc-45a0-8073-ac26c77441c9
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: NdisAdjustMdlLength
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisAdjustMdlLength
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
req.irql: Any level (see Remarks section)
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisAdjustMdlLength macro



## -description
The 
  <b>NdisAdjustMdlLength</b> function modifies the length of the data that is associated with an MDL.



## -syntax

````
VOID NdisAdjustMdlLength(
  [in] PMDL Mdl,
  [in] UINT Length
);
````


## -parameters

### -param Mdl [in]

A pointer to a memory descriptor list (MDL).


### -param Length [in]

The number of bytes of data that the MDL describes.


## -remarks
The 
    <b>NdisAdjustMdlLength</b> function modifies the 
    <b>ByteCount</b> member of an MDL that was allocated by calling the 
    <a href="..\ndis\nf-ndis-ndisallocatemdl.md">NdisAllocateMdl</a> function.

The caller of 
    <b>NdisAdjustMdlLength</b> can pass only an MDL descriptor that the caller allocated. It cannot pass an
    MDL descriptor that another driver allocated.

For example, the driver of a bus-master DMA NIC calls 
    <b>NdisAdjustMdlLength</b> with MDL descriptors that it allocated to specify receive MDLs in its shared
    memory block. Before such a driver indicates received data, it calls 
    <b>NdisAdjustMdlLength</b> to make the MDL descriptor that it will include in the receive indication match
    the size of the received data if it is less than the size of the NIC's receive buffer.

The length that is passed to 
    <b>NdisAdjustMdlLength</b> cannot be larger than the length that was passed to 
    <a href="..\ndis\nf-ndis-ndisallocatemdl.md">NdisAllocateMdl</a> when the MDL descriptor
    was allocated.

The caller of 
    <b>NdisAdjustMdlLength</b> must restore the length to its original value before it frees the MDL
    descriptor with 
    <a href="..\ndis\nf-ndis-ndisfreemdl.md">NdisFreeMdl</a>.

Callers of 
    <b>NdisAdjustMdlLength</b> can run at any IRQL, but typically run at IRQL &lt;= DISPATCH_LEVEL.


## -see-also
<dl>
<dt>
<a href="..\ndis\nf-ndis-ndisallocatemdl.md">NdisAllocateMdl</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisfreemdl.md">NdisFreeMdl</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisAdjustMdlLength macro%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

