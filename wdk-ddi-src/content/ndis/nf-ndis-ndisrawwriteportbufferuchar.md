---
UID: NF:ndis.NdisRawWritePortBufferUchar
title: NdisRawWritePortBufferUchar macro (ndis.h)
description: NdisRawWritePortBufferUchar writes a specified number of bytes from a caller-supplied buffer to a given I/O port.
old-location: netvista\ndisrawwriteportbufferuchar.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["NdisRawWritePortBufferUchar macro"]
ms.keywords: NdisRawWritePortBufferUchar, NdisRawWritePortBufferUchar macro [Network Drivers Starting with Windows Vista], miniport_port_raw_ref_4b54b55d-c94d-4401-8d16-4650d80c620c.xml, ndis/NdisRawWritePortBufferUchar, netvista.ndisrawwriteportbufferuchar
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisRawWritePortBufferUchar   (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisRawWritePortBufferUchar   (NDIS 5.1)) in Windows XP.
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
 - NdisRawWritePortBufferUchar
 - ndis/NdisRawWritePortBufferUchar
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ndis.h
api_name:
 - NdisRawWritePortBufferUchar
---

# NdisRawWritePortBufferUchar macro


## -description

<b>NdisRawWritePortBufferUchar</b> writes a specified number of bytes from a caller-supplied buffer to a
  given I/O port.

## -parameters

### -param Port 

[in]
Specifies the I/O port. This address falls in a range that was mapped during initialization with 
     <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismregisterioportrange">
     NdisMRegisterIoPortRange</a>.

### -param Buffer 

[in]
Pointer to a caller-allocated resident buffer containing the bytes to be written.

### -param Length 

[in]
Specifies the number of bytes to write to the I/O port.

## -remarks

A miniport driver calls 
    <b>NdisRawWritePortBufferUchar</b> to transfer a sequence of bytes, one at a time, to a NIC.

<b>NdisRawWritePortBufferUchar</b> runs fast because it need not map a bus-relative port address onto a
    host-dependent logical port address at every call.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a>



<a href="/windows-hardware/drivers/devtest/ndis-ndismregisterioportrange">NdisMRegisterIoPortRange</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisrawreadportbufferuchar">NdisRawReadPortBufferUchar</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisrawwriteportbufferulong">NdisRawWritePortBufferUlong</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisrawwriteportbufferushort">NdisRawWritePortBufferUshort</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisrawwriteportuchar">NdisRawWritePortUchar</a>
