---
UID: NF:ndis.NdisRawWritePortUlong
title: NdisRawWritePortUlong macro (ndis.h)
description: NdisRawWritePortUlong writes a ULONG value to an I/O port on the NIC.
old-location: netvista\ndisrawwriteportulong.htm
tech.root: netvista
ms.assetid: 24abe892-7d49-4bc4-8862-e375f9862a5f
ms.date: 05/02/2018
keywords: ["NdisRawWritePortUlong macro"]
ms.keywords: NdisRawWritePortUlong, NdisRawWritePortUlong macro [Network Drivers Starting with Windows Vista], miniport_port_raw_ref_54b23b9a-fb43-4591-a123-6c564850f5cf.xml, ndis/NdisRawWritePortUlong, netvista.ndisrawwriteportulong
f1_keywords:
 - "ndis/NdisRawWritePortUlong"
 - "NdisRawWritePortUlong"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisRawWritePortUlong (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisRawWritePortUlong (NDIS   5.1)) in Windows XP.
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
- NdisRawWritePortUlong
targetos: Windows
req.typenames: 
---

# NdisRawWritePortUlong macro


## -description


<b>NdisRawWritePortUlong</b> writes a ULONG value to an I/O port on the NIC.


## -parameters




### -param Port [in]

Specifies the I/O port. This address falls in a range that was mapped during initialization with 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismregisterioportrange">
     NdisMRegisterIoPortRange</a>.


### -param Data [in]

Specifies the ULONG to be written.


## -remarks



<b>NdisRawWritePortUlong</b> runs fast because it need not map a bus-relative I/O port address onto a
    host-dependent logical port address at every call.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/ndis-ndismregisterioportrange">NdisMRegisterIoPortRange</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisrawreadportulong">NdisRawReadPortUlong</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisrawwriteportbufferulong">NdisRawWritePortBufferUlong</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisrawwriteportuchar">NdisRawWritePortUchar</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisrawwriteportushort">NdisRawWritePortUshort</a>
 

 

