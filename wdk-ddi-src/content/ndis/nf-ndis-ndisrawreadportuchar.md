---
UID: NF:ndis.NdisRawReadPortUchar
title: NdisRawReadPortUchar macro
author: windows-driver-content
description: NdisRawReadPortUchar reads a byte from a given I/O port on the NIC.
old-location: netvista\ndisrawreadportuchar.htm
old-project: netvista
ms.assetid: 5bda6d10-dd68-4385-b71c-8319e6ed0d4a
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: NdisRawReadPortUchar, NdisRawReadPortUchar macro [Network Drivers Starting with Windows Vista], miniport_port_raw_ref_e478dfdb-7037-4a9e-8da5-3bc38561094f.xml, ndis/NdisRawReadPortUchar, netvista.ndisrawreadportuchar
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisRawReadPortUchar (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisRawReadPortUchar (NDIS   5.1)) in Windows XP.
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ndis.h
api_name:
-	NdisRawReadPortUchar
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisRawReadPortUchar macro


## -description


<b>NdisRawReadPortUchar</b> reads a byte from a given I/O port on the NIC.


## -syntax


````
VOID NdisRawReadPortUchar(
  [in]  ULONG_PTR Port,
  [out] PUCHAR    Data
);
````


## -parameters




### -param Port [in]

Specifies the I/O port. This address falls in a range that was mapped during initialization with 
     <a href="..\ndis\nf-ndis-ndismregisterioportrange.md">
     NdisMRegisterIoPortRange</a>.


### -param Data [out]

Pointer to a caller-supplied variable in which this function returns a byte read in from the
     port.


## -remarks



<b>NdisRawReadPortUchar</b> runs fast
    because it need not map a bus-relative I/O port address onto a host-dependent logical port address at
    every call.




## -see-also

<a href="..\ndis\nf-ndis-ndisrawreadportulong.md">NdisRawReadPortUlong</a>



<a href="..\ndis\nf-ndis-ndismregisterioportrange.md">NdisMRegisterIoPortRange</a>



<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>



<a href="..\ndis\nf-ndis-ndisrawwriteportuchar.md">NdisRawWritePortUchar</a>



<a href="..\ndis\nf-ndis-ndisrawreadportbufferuchar.md">NdisRawReadPortBufferUchar</a>



<a href="..\ndis\nf-ndis-ndisrawreadportushort.md">NdisRawReadPortUshort</a>



 

 


