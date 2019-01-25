---
UID: NF:ndis.NdisRawReadPortUshort
title: NdisRawReadPortUshort macro (ndis.h)
description: NdisRawReadPortUshort reads a USHORT value from a given I/O port on the NIC.
old-location: netvista\ndisrawreadportushort.htm
tech.root: netvista
ms.assetid: 88dbdd78-43a4-4ae2-ae49-336a0a621c5c
ms.date: 05/02/2018
ms.keywords: NdisRawReadPortUshort, NdisRawReadPortUshort macro [Network Drivers Starting with Windows Vista], miniport_port_raw_ref_5d9255b3-3679-4cd2-bc07-baa0dc2c684f.xml, ndis/NdisRawReadPortUshort, netvista.ndisrawreadportushort
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
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisRawReadPortUshort macro


## -description


<b>NdisRawReadPortUshort</b> reads a USHORT value from a given I/O port on the NIC.


## -parameters




### -param Port [in]

Specifies the I/O port. This address falls in a range that was mapped during initialization with 
     <a href="https://msdn.microsoft.com/3e7fc02b-9562-44b9-8659-793a1d96d1e9">
     NdisMRegisterIoPortRange</a>.


### -param Data [out]

Pointer to a caller-supplied variable in which this function returns a USHORT value read in from
     the port.


## -remarks



<b>NdisRawReadPortUshort</b> runs fast because it need not map a bus-relative I/O port address onto a
    host-dependent logical port address at every call.




## -see-also




<a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh975121">NdisMRegisterIoPortRange</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563791">NdisRawReadPortBufferUshort</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563794">NdisRawReadPortUchar</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563801">NdisRawReadPortUlong</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564510">NdisRawWritePortUshort</a>
 

 

