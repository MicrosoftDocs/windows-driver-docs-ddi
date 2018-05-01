---
UID: NF:ndis.NdisRawReadPortUlong
title: NdisRawReadPortUlong macro
author: windows-driver-content
description: NdisRawReadPortUlong reads a ULONG value from a given I/O port on the NIC.
old-location: netvista\ndisrawreadportulong.htm
old-project: netvista
ms.assetid: 40ecda3a-67ff-48b6-8ee9-7527c7bd9c6c
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: NdisRawReadPortUlong, NdisRawReadPortUlong macro [Network Drivers Starting with Windows Vista], miniport_port_raw_ref_a5c1ea12-2ff0-4546-9244-8137c365eb8f.xml, ndis/NdisRawReadPortUlong, netvista.ndisrawreadportulong
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisRawReadPortUlong (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisRawReadPortUlong (NDIS   5.1)) in Windows XP.
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
-	NdisRawReadPortUlong
product: Windows
targetos: Windows
req.typenames: 
---

# NdisRawReadPortUlong macro


## -description


<b>NdisRawReadPortUlong</b> reads a ULONG value from a given I/O port on the NIC.


## -parameters




### -param Port [in]

Specifies the I/O port. This address falls in a range that was mapped during initialization with 
     <a href="https://msdn.microsoft.com/3e7fc02b-9562-44b9-8659-793a1d96d1e9">
     NdisMRegisterIoPortRange</a>.


### -param Data [out]

Pointer to a caller-supplied variable in which this function returns a ULONG value read in from
     the port.


## -remarks



<b>NdisRawReadPortUlong</b> runs fast
    because it need not map a bus-relative I/O port address onto a host-dependent logical port address at
    every call.




## -see-also




<a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh975121">NdisMRegisterIoPortRange</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563785">NdisRawReadPortBufferUlong</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563794">NdisRawReadPortUchar</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563808">NdisRawReadPortUshort</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563832">NdisRawWritePortUlong</a>
 

 

