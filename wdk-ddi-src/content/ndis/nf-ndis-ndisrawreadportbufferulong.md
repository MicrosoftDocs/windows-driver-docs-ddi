---
UID: NF:ndis.NdisRawReadPortBufferUlong
title: NdisRawReadPortBufferUlong macro (ndis.h)
description: NdisRawReadPortBufferUlong reads a specified number of ULONGs into a caller-supplied buffer.
old-location: netvista\ndisrawreadportbufferulong.htm
tech.root: netvista
ms.assetid: 86a0b7c4-ef3a-4dd9-961d-35f96182e30c
ms.date: 05/02/2018
ms.keywords: NdisRawReadPortBufferUlong, NdisRawReadPortBufferUlong macro [Network Drivers Starting with Windows Vista], miniport_port_raw_ref_0696e0e4-976c-4d17-a482-054d5d441608.xml, ndis/NdisRawReadPortBufferUlong, netvista.ndisrawreadportbufferulong
ms.topic: macro
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisRawReadPortBufferUlong   (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisRawReadPortBufferUlong   (NDIS 5.1)) in Windows XP.
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
-	NdisRawReadPortBufferUlong
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisRawReadPortBufferUlong macro


## -description


<b>NdisRawReadPortBufferUlong</b> reads a specified number of ULONGs into a caller-supplied buffer.


## -parameters




### -param Port [in]

Specifies the I/O port. This address falls in a range that was mapped during initialization with 
     <a href="https://msdn.microsoft.com/3e7fc02b-9562-44b9-8659-793a1d96d1e9">
     NdisMRegisterIoPortRange</a>.


### -param Buffer [out]

Pointer to a caller-allocated buffer, in resident memory, into which the ULONGs will be
     transferred from the NIC. The caller must allocate a buffer at least (
     <b>sizeof</b>(ULONG)
     *
     <i>Length</i> ).


### -param Length [in]

Specifies how many ULONGs to transfer from the NIC.


## -remarks



<b>NdisRawReadPortBufferUlong</b> reads each ULONG value, one at a time, from the given I/O port into the
    given buffer.




## -see-also




<a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh975121">NdisMRegisterIoPortRange</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563782">NdisRawReadPortBufferUchar</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563791">NdisRawReadPortBufferUshort</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563801">NdisRawReadPortUlong</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563816">NdisRawWritePortBufferUlong</a>
 

 

