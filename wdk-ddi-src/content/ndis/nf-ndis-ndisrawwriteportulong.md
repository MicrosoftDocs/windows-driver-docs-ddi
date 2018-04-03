---
UID: NF:ndis.NdisRawWritePortUlong
title: NdisRawWritePortUlong macro
author: windows-driver-content
description: NdisRawWritePortUlong writes a ULONG value to an I/O port on the NIC.
old-location: netvista\ndisrawwriteportulong.htm
old-project: netvista
ms.assetid: 24abe892-7d49-4bc4-8862-e375f9862a5f
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: NdisRawWritePortUlong, NdisRawWritePortUlong macro [Network Drivers Starting with Windows Vista], miniport_port_raw_ref_54b23b9a-fb43-4591-a123-6c564850f5cf.xml, ndis/NdisRawWritePortUlong, netvista.ndisrawwriteportulong
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ndis.h
api_name:
-	NdisRawWritePortUlong
product:
- Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisRawWritePortUlong macro


## -description


<b>NdisRawWritePortUlong</b> writes a ULONG value to an I/O port on the NIC.


## -parameters




### -param Port [in]

Specifies the I/O port. This address falls in a range that was mapped during initialization with 
     <a href="https://msdn.microsoft.com/3e7fc02b-9562-44b9-8659-793a1d96d1e9">
     NdisMRegisterIoPortRange</a>.


### -param Data [in]

Specifies the ULONG to be written.


## -remarks



<b>NdisRawWritePortUlong</b> runs fast because it need not map a bus-relative I/O port address onto a
    host-dependent logical port address at every call.




## -see-also




<a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh975121">NdisMRegisterIoPortRange</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563801">NdisRawReadPortUlong</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563816">NdisRawWritePortBufferUlong</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563829">NdisRawWritePortUchar</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564510">NdisRawWritePortUshort</a>
 

 

