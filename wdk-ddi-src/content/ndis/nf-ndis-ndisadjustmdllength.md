---
UID: NF:ndis.NdisAdjustMdlLength
title: NdisAdjustMdlLength macro (ndis.h)
description: The NdisAdjustMdlLength function modifies the length of the data that is associated with an MDL.
old-location: netvista\ndisadjustmdllength.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["NdisAdjustMdlLength macro"]
ms.keywords: NdisAdjustMdlLength, NdisAdjustMdlLength macro [Network Drivers Starting with Windows Vista], ndis/NdisAdjustMdlLength, ndis_netbuf_functions_ref_babeb674-269d-4efc-add1-635666fd7863.xml, netvista.ndisadjustmdllength
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
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
req.irql: Any level (see Remarks section)
targetos: Windows
req.typenames: 
f1_keywords:
 - NdisAdjustMdlLength
 - ndis/NdisAdjustMdlLength
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ndis.h
api_name:
 - NdisAdjustMdlLength
---

# NdisAdjustMdlLength macro


## -description

The 
  <b>NdisAdjustMdlLength</b> function modifies the length of the data that is associated with an MDL.

## -parameters

### -param _Mdl 

[in]
A pointer to a memory descriptor list (MDL).

### -param _Length 

[in]
The number of bytes of data that the MDL describes.

## -remarks

The 
    <b>NdisAdjustMdlLength</b> function modifies the 
    <b>ByteCount</b> member of an MDL that was allocated by calling the 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatemdl">NdisAllocateMdl</a> function.

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
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatemdl">NdisAllocateMdl</a> when the MDL descriptor
    was allocated.

The caller of 
    <b>NdisAdjustMdlLength</b> must restore the length to its original value before it frees the MDL
    descriptor with 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfreemdl">NdisFreeMdl</a>.

Callers of 
    <b>NdisAdjustMdlLength</b> can run at any IRQL, but typically run at IRQL <= DISPATCH_LEVEL.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatemdl">NdisAllocateMdl</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfreemdl">NdisFreeMdl</a>
