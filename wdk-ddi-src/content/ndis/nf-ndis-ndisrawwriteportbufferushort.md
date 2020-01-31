---
UID: NF:ndis.NdisRawWritePortBufferUshort
title: NdisRawWritePortBufferUshort macro (ndis.h)
description: NdisRawWritePortBufferUshort writes a specified number of USHORT values from a caller-supplied buffer to a given I/O port.
old-location: netvista\ndisrawwriteportbufferushort.htm
tech.root: netvista
ms.assetid: 457b13e5-5917-4aa2-b471-bc9fde14f950
ms.date: 05/02/2018
ms.keywords: NdisRawWritePortBufferUshort, NdisRawWritePortBufferUshort macro [Network Drivers Starting with Windows Vista], miniport_port_raw_ref_43adee77-b540-4147-92a3-0035618064de.xml, ndis/NdisRawWritePortBufferUshort, netvista.ndisrawwriteportbufferushort
f1_keywords:
 - "ndis/NdisRawWritePortBufferUshort"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisRawWritePortBufferUshort   (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisRawWritePortBufferUshort   (NDIS 5.1)) in Windows XP.
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
- NdisRawWritePortBufferUshort
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisRawWritePortBufferUshort macro


## -description


<b>NdisRawWritePortBufferUshort</b> writes a specified number of USHORT values from a caller-supplied buffer
  to a given I/O port.


## -parameters




### -param Port [in]

Specifies the I/O port. This address falls in a range that was mapped during initialization with 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismregisterioportrange">
     NdisMRegisterIoPortRange</a>.


### -param Buffer [in]

Pointer to a caller-allocated resident buffer containing the USHORTs to be written.


### -param Length [in]

Specifies the number of USHORTs to write to the I/O port.


## -remarks



A miniport driver calls 
    <b>NdisRawWritePortBufferUshort</b> to transfer a sequence of USHORTs, one at a time, to a NIC.

<b>NdisRawWritePortBufferUshort</b> runs fast because it need not map a bus-relative port address onto a
    host-dependent logical port address at every call.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/ndis-ndismregisterioportrange">NdisMRegisterIoPortRange</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisrawreadportbufferushort">NdisRawReadPortBufferUshort</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisrawwriteportbufferuchar">NdisRawWritePortBufferUchar</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisrawwriteportbufferulong">NdisRawWritePortBufferUlong</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisrawwriteportushort">NdisRawWritePortUshort</a>
 

 

