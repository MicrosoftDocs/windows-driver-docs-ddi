---
UID: NF:ndis.NdisRawReadPortBufferUchar
title: NdisRawReadPortBufferUchar macro (ndis.h)
description: NdisRawReadPortBufferUchar reads a specified number of bytes into a caller-supplied buffer.
old-location: netvista\ndisrawreadportbufferuchar.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["NdisRawReadPortBufferUchar macro"]
ms.keywords: NdisRawReadPortBufferUchar, NdisRawReadPortBufferUchar macro [Network Drivers Starting with Windows Vista], miniport_port_raw_ref_acd96d67-c82f-48dd-b6f1-cb77564e4bd6.xml, ndis/NdisRawReadPortBufferUchar, netvista.ndisrawreadportbufferuchar
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisRawReadPortBufferUchar   (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisRawReadPortBufferUchar   (NDIS 5.1)) in Windows XP.
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
 - NdisRawReadPortBufferUchar
 - ndis/NdisRawReadPortBufferUchar
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ndis.h
api_name:
 - NdisRawReadPortBufferUchar
---

# NdisRawReadPortBufferUchar macro


## -description

<b>NdisRawReadPortBufferUchar</b> reads a specified number of bytes into a caller-supplied buffer.

## -parameters

### -param Port 

[in]
Specifies the I/O port. This address falls in a range that was mapped during initialization with 
     <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismregisterioportrange">
     NdisMRegisterIoPortRange</a>.

### -param Buffer 

[out]
Pointer to a caller-allocated buffer, in resident memory, into which the bytes will be transferred
     from the NIC's port. The caller must allocate a buffer at least 
     sizeof(
     <i>Length</i> ).

### -param Length 

[in]
Specifies how many bytes to transfer from the NIC.

## -remarks

<b>NdisRawReadPortBufferUchar</b> reads each byte, one at a time, from the given I/O port into the given
    buffer.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a>



<a href="/windows-hardware/drivers/devtest/ndis-ndismregisterioportrange">NdisMRegisterIoPortRange</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisrawreadportbufferulong">NdisRawReadPortBufferUlong</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisrawreadportbufferushort">NdisRawReadPortBufferUshort</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisrawreadportuchar">NdisRawReadPortUchar</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisrawwriteportbufferuchar">NdisRawWritePortBufferUchar</a>
