---
UID: NF:ndis.NdisRawWritePortUchar
title: NdisRawWritePortUchar macro (ndis.h)
description: NdisRawWritePortUchar writes a byte to an I/O port on the NIC.
old-location: netvista\ndisrawwriteportuchar.htm
tech.root: netvista
ms.assetid: 9fcbf570-d272-4373-86ca-8466fb5fc18c
ms.date: 05/02/2018
ms.keywords: NdisRawWritePortUchar, NdisRawWritePortUchar macro [Network Drivers Starting with Windows Vista], miniport_port_raw_ref_00cc5f8f-4965-4cc3-bdc6-25dcf2128582.xml, ndis/NdisRawWritePortUchar, netvista.ndisrawwriteportuchar
f1_keywords:
 - "ndis/NdisRawWritePortUchar"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisRawWritePortUchar (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisRawWritePortUchar (NDIS   5.1)) in Windows XP.
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
- NdisRawWritePortUchar
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisRawWritePortUchar macro


## -description


<b>NdisRawWritePortUchar</b> writes a byte to an I/O port on the NIC.


## -parameters




### -param Port [in]

Specifies the I/O port. This address falls in a range that was mapped during initialization with 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismregisterioportrange">
     NdisMRegisterIoPortRange</a>.


### -param Data [in]

Specifies the byte to be written.


## -remarks



<b>NdisRawWritePortUchar</b> runs fast because it need not map a bus-relative I/O port address onto a
    host-dependent logical port address at every call.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/ndis-ndismregisterioportrange">NdisMRegisterIoPortRange</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisrawreadportuchar">NdisRawReadPortUchar</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisrawwriteportbufferuchar">NdisRawWritePortBufferUchar</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisrawwriteportulong">NdisRawWritePortUlong</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisrawwriteportushort">NdisRawWritePortUshort</a>
 

 

