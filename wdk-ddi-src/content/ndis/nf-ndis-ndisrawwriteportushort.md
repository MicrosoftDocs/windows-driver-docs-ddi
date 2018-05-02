---
UID: NF:ndis.NdisRawWritePortUshort
title: NdisRawWritePortUshort macro
author: windows-driver-content
description: NdisRawWritePortUshort writes a USHORT value to an I/O port on the NIC.
old-location: netvista\ndisrawwriteportushort.htm
old-project: netvista
ms.assetid: f8ad7d35-5832-4258-8666-2c0f1f893f10
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: NdisRawWritePortUshort, NdisRawWritePortUshort macro [Network Drivers Starting with Windows Vista], miniport_port_raw_ref_6c164b75-fcfb-4251-803a-ca7cbe623b4d.xml, ndis/NdisRawWritePortUshort, netvista.ndisrawwriteportushort
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ndis.h
api_name:
-	NdisRawWritePortUshort
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
     <a href="https://msdn.microsoft.com/3e7fc02b-9562-44b9-8659-793a1d96d1e9">
     NdisMRegisterIoPortRange</a>.


### -param Data [in]

Specifies the USHORT to be written.


## -remarks



<b>NdisRawWritePortUshort</b> runs fast because it need not map a bus-relative I/O port address onto a
    host-dependent logical port address at every call.




## -see-also




<a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh975121">NdisMRegisterIoPortRange</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563808">NdisRawReadPortUshort</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563824">NdisRawWritePortBufferUshort</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563829">NdisRawWritePortUchar</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563832">NdisRawWritePortUlong</a>
 

 

