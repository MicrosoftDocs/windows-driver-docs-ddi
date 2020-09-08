---
UID: NF:ndis.NdisRawReadPortBufferUlong
title: NdisRawReadPortBufferUlong macro (ndis.h)
description: NdisRawReadPortBufferUlong reads a specified number of ULONGs into a caller-supplied buffer.
old-location: netvista\ndisrawreadportbufferulong.htm
tech.root: netvista
ms.assetid: 86a0b7c4-ef3a-4dd9-961d-35f96182e30c
ms.date: 05/02/2018
keywords: ["NdisRawReadPortBufferUlong macro"]
ms.keywords: NdisRawReadPortBufferUlong, NdisRawReadPortBufferUlong macro [Network Drivers Starting with Windows Vista], miniport_port_raw_ref_0696e0e4-976c-4d17-a482-054d5d441608.xml, ndis/NdisRawReadPortBufferUlong, netvista.ndisrawreadportbufferulong
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisRawReadPortBufferUlong   (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisRawReadPortBufferUlong   (NDIS 5.1)) in Windows XP.
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
targetos: Windows
req.typenames: 
f1_keywords:
 - NdisRawReadPortBufferUlong
 - ndis/NdisRawReadPortBufferUlong
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ndis.h
api_name:
 - NdisRawReadPortBufferUlong
---

# NdisRawReadPortBufferUlong macro


## -description

<b>NdisRawReadPortBufferUlong</b> reads a specified number of ULONGs into a caller-supplied buffer.

## -parameters

### -param Port 

[in]
Specifies the I/O port. This address falls in a range that was mapped during initialization with 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismregisterioportrange">
     NdisMRegisterIoPortRange</a>.

### -param Buffer 

[out]
Pointer to a caller-allocated buffer, in resident memory, into which the ULONGs will be
     transferred from the NIC. The caller must allocate a buffer at least (
     <b>sizeof</b>(ULONG)
     *
     <i>Length</i> ).

### -param Length 

[in]
Specifies how many ULONGs to transfer from the NIC.

## -remarks

<b>NdisRawReadPortBufferUlong</b> reads each ULONG value, one at a time, from the given I/O port into the
    given buffer.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/ndis-ndismregisterioportrange">NdisMRegisterIoPortRange</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisrawreadportbufferuchar">NdisRawReadPortBufferUchar</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisrawreadportbufferushort">NdisRawReadPortBufferUshort</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisrawreadportulong">NdisRawReadPortUlong</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisrawwriteportbufferulong">NdisRawWritePortBufferUlong</a>

