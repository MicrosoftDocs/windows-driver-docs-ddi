---
UID: NF:ndis.NdisRawReadPortUshort
title: NdisRawReadPortUshort macro
author: windows-driver-content
description: NdisRawReadPortUshort reads a USHORT value from a given I/O port on the NIC.
old-location: netvista\ndisrawreadportushort.htm
old-project: netvista
ms.assetid: 88dbdd78-43a4-4ae2-ae49-336a0a621c5c
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: NdisRawReadPortUshort, NdisRawReadPortUshort macro [Network Drivers Starting with Windows Vista], miniport_port_raw_ref_5d9255b3-3679-4cd2-bc07-baa0dc2c684f.xml, ndis/NdisRawReadPortUshort, netvista.ndisrawreadportushort
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisRawReadPortUshort (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisRawReadPortUshort (NDIS   5.1)) in Windows XP.
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
-	NdisRawReadPortUshort
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisRawReadPortUshort macro


## -description


<b>NdisRawReadPortUshort</b> reads a USHORT value from a given I/O port on the NIC.


## -syntax


````
VOID NdisRawReadPortUshort(
  [in]  ULONG_PTR Port,
  [out] PUSHORT   Data
);
````


## -parameters




### -param Port [in]

Specifies the I/O port. This address falls in a range that was mapped during initialization with 
     <a href="..\ndis\nf-ndis-ndismregisterioportrange.md">
     NdisMRegisterIoPortRange</a>.


### -param Data [out]

Pointer to a caller-supplied variable in which this function returns a USHORT value read in from
     the port.


## -remarks



<b>NdisRawReadPortUshort</b> runs fast because it need not map a bus-relative I/O port address onto a
    host-dependent logical port address at every call.




## -see-also

<a href="..\ndis\nf-ndis-ndisrawwriteportushort.md">NdisRawWritePortUshort</a>



<a href="..\ndis\nf-ndis-ndisrawreadportuchar.md">NdisRawReadPortUchar</a>



<a href="..\ndis\nf-ndis-ndisrawreadportbufferushort.md">NdisRawReadPortBufferUshort</a>



<a href="..\ndis\nf-ndis-ndisrawreadportulong.md">NdisRawReadPortUlong</a>



<a href="..\ndis\nf-ndis-ndismregisterioportrange.md">NdisMRegisterIoPortRange</a>



<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>



 

 


