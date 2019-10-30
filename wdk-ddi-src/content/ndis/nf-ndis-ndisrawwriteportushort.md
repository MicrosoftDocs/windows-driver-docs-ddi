---
UID: NF:ndis.NdisRawWritePortUshort
title: NdisRawWritePortUshort macro (ndis.h)
description: NdisRawWritePortUshort writes a USHORT value to an I/O port on the NIC.
old-location: netvista\ndisrawwriteportushort.htm
tech.root: netvista
ms.assetid: f8ad7d35-5832-4258-8666-2c0f1f893f10
ms.date: 05/02/2018
ms.keywords: NdisRawWritePortUshort, NdisRawWritePortUshort macro [Network Drivers Starting with Windows Vista], miniport_port_raw_ref_6c164b75-fcfb-4251-803a-ca7cbe623b4d.xml, ndis/NdisRawWritePortUshort, netvista.ndisrawwriteportushort
ms.topic: macro
f1_keywords:
 - "ndis/NdisRawWritePortUshort"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisRawWritePortUshort (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisRawWritePortUshort (NDIS   5.1)) in Windows XP.
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
- NdisRawWritePortUshort
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisRawWritePortUshort macro


## -description


<b>NdisRawWritePortUshort</b> writes a USHORT value to an I/O port on the NIC.


## -parameters




### -param Port [in]

Specifies the I/O port. This address falls in a range that was mapped during initialization with 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismregisterioportrange">
     NdisMRegisterIoPortRange</a>.


### -param Data [in]

Specifies the USHORT to be written.


## -remarks



<b>NdisRawWritePortUshort</b> runs fast because it need not map a bus-relative I/O port address onto a
    host-dependent logical port address at every call.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/ndis-ndismregisterioportrange">NdisMRegisterIoPortRange</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisrawreadportushort">NdisRawReadPortUshort</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisrawwriteportbufferushort">NdisRawWritePortBufferUshort</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisrawwriteportuchar">NdisRawWritePortUchar</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisrawwriteportulong">NdisRawWritePortUlong</a>
 

 

