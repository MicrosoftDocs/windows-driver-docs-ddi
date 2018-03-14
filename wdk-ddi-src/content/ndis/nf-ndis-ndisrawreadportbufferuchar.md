---
UID: NF:ndis.NdisRawReadPortBufferUchar
title: NdisRawReadPortBufferUchar macro
author: windows-driver-content
description: NdisRawReadPortBufferUchar reads a specified number of bytes into a caller-supplied buffer.
old-location: netvista\ndisrawreadportbufferuchar.htm
old-project: netvista
ms.assetid: de629357-6176-4c98-ba71-ac1eea0c8ff1
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: NdisRawReadPortBufferUchar, NdisRawReadPortBufferUchar macro [Network Drivers Starting with Windows Vista], miniport_port_raw_ref_acd96d67-c82f-48dd-b6f1-cb77564e4bd6.xml, ndis/NdisRawReadPortBufferUchar, netvista.ndisrawreadportbufferuchar
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisRawReadPortBufferUchar   (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisRawReadPortBufferUchar   (NDIS 5.1)) in Windows XP.
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
-	NdisRawReadPortBufferUchar
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisRawReadPortBufferUchar macro


## -description


<b>NdisRawReadPortBufferUchar</b> reads a specified number of bytes into a caller-supplied buffer.


## -syntax


````
VOID NdisRawReadPortBufferUchar(
  [in]  ULONG_PTR Port,
  [out] PUCHAR    Buffer,
  [in]  ULONG     Length
);
````


## -parameters




### -param Port [in]

Specifies the I/O port. This address falls in a range that was mapped during initialization with 
     <a href="..\ndis\nf-ndis-ndismregisterioportrange.md">
     NdisMRegisterIoPortRange</a>.


### -param Buffer [out]

Pointer to a caller-allocated buffer, in resident memory, into which the bytes will be transferred
     from the NIC's port. The caller must allocate a buffer at least 
     sizeof(
     <i>Length</i> ).


### -param Length [in]

Specifies how many bytes to transfer from the NIC.


## -remarks



<b>NdisRawReadPortBufferUchar</b> reads each byte, one at a time, from the given I/O port into the given
    buffer.




## -see-also

<a href="..\ndis\nf-ndis-ndisrawreadportuchar.md">NdisRawReadPortUchar</a>



<a href="..\ndis\nf-ndis-ndisrawreadportbufferushort.md">NdisRawReadPortBufferUshort</a>



<a href="..\ndis\nf-ndis-ndisrawwriteportbufferuchar.md">NdisRawWritePortBufferUchar</a>



<a href="..\ndis\nf-ndis-ndismregisterioportrange.md">NdisMRegisterIoPortRange</a>



<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>



<a href="..\ndis\nf-ndis-ndisrawreadportbufferulong.md">NdisRawReadPortBufferUlong</a>



 

 


