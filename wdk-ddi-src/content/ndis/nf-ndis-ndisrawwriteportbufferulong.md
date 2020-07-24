---
UID: NF:ndis.NdisRawWritePortBufferUlong
title: NdisRawWritePortBufferUlong macro (ndis.h)
description: NdisRawWritePortBufferUlong writes a specified number of ULONG values from a caller-supplied buffer to a given I/O port.
old-location: netvista\ndisrawwriteportbufferulong.htm
tech.root: netvista
ms.assetid: f97aa977-289b-4a46-b724-9a5c1b468b74
ms.date: 05/02/2018
keywords: ["NdisRawWritePortBufferUlong macro"]
ms.keywords: NdisRawWritePortBufferUlong, NdisRawWritePortBufferUlong macro [Network Drivers Starting with Windows Vista], miniport_port_raw_ref_6d507471-8935-42d8-8e13-8b82496bca57.xml, ndis/NdisRawWritePortBufferUlong, netvista.ndisrawwriteportbufferulong
f1_keywords:
 - "ndis/NdisRawWritePortBufferUlong"
 - "NdisRawWritePortBufferUlong"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisRawWritePortBufferUlong   (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisRawWritePortBufferUlong   (NDIS 5.1)) in Windows XP.
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ndis.h
api_name:
- NdisRawWritePortBufferUlong
targetos: Windows
req.typenames: 
---

# NdisRawWritePortBufferUlong macro


## -description


<b>NdisRawWritePortBufferUlong</b> writes a specified number of ULONG values from a caller-supplied buffer
  to a given I/O port.


## -parameters




### -param Port [in]

Specifies the I/O port. This address falls in a range that was mapped during initialization with 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismregisterioportrange">
     NdisMRegisterIoPortRange</a>.


### -param Buffer [in]

Pointer to a caller-allocated resident buffer containing the ULONGs to be written.


### -param Length [in]

Specifies the number of ULONGs to write to the I/O port.


## -remarks



A miniport driver calls 
    <b>NdisRawWritePortBufferUlong</b> to transfer a sequence of ULONGs, one at a time, to a NIC.

<b>NdisRawWritePortBufferUlong</b> runs fast because it need not map a bus-relative port address onto a
    host-dependent logical port address at every call.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/ndis-ndismregisterioportrange">NdisMRegisterIoPortRange</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisrawreadportbufferulong">NdisRawReadPortBufferUlong</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisrawwriteportbufferuchar">NdisRawWritePortBufferUchar</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisrawwriteportbufferushort">NdisRawWritePortBufferUshort</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisrawwriteportulong">NdisRawWritePortUlong</a>
 

 

