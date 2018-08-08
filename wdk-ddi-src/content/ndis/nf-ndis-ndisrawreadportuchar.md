---
UID: NF:ndis.NdisRawReadPortUchar
title: NdisRawReadPortUchar macro
author: windows-driver-content
description: NdisRawReadPortUchar reads a byte from a given I/O port on the NIC.
old-location: netvista\ndisrawreadportuchar.htm
tech.root: netvista
ms.assetid: 5bda6d10-dd68-4385-b71c-8319e6ed0d4a
ms.author: windowsdriverdev
ms.date: 5/2/2018
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
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisRawReadPortUchar macro


## -description


<b>NdisRawReadPortUchar</b> reads a byte from a given I/O port on the NIC.


## -parameters




### -param Port [in]

Specifies the I/O port. This address falls in a range that was mapped during initialization with 
     <a href="https://msdn.microsoft.com/3e7fc02b-9562-44b9-8659-793a1d96d1e9">
     NdisMRegisterIoPortRange</a>.


### -param Data [out]

Pointer to a caller-supplied variable in which this function returns a byte read in from the
     port.


## -remarks



<b>NdisRawReadPortUchar</b> runs fast
    because it need not map a bus-relative I/O port address onto a host-dependent logical port address at
    every call.




## -see-also




<a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh975121">NdisMRegisterIoPortRange</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563782">NdisRawReadPortBufferUchar</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563801">NdisRawReadPortUlong</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563808">NdisRawReadPortUshort</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563829">NdisRawWritePortUchar</a>
 

 

