---
UID: NF:ndis.NdisRawWritePortBufferUlong
title: NdisRawWritePortBufferUlong macro
author: windows-driver-content
description: NdisRawWritePortBufferUlong writes a specified number of ULONG values from a caller-supplied buffer to a given I/O port.
old-location: netvista\ndisrawwriteportbufferulong.htm
old-project: netvista
ms.assetid: f97aa977-289b-4a46-b724-9a5c1b468b74
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: NdisRawWritePortBufferUlong, NdisRawWritePortBufferUlong macro [Network Drivers Starting with Windows Vista], miniport_port_raw_ref_6d507471-8935-42d8-8e13-8b82496bca57.xml, ndis/NdisRawWritePortBufferUlong, netvista.ndisrawwriteportbufferulong
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisRawWritePortBufferUlong   (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisRawWritePortBufferUlong   (NDIS 5.1)) in Windows XP.
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
-	NdisRawWritePortBufferUlong
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisRawWritePortBufferUlong macro


## -description


<b>NdisRawWritePortBufferUlong</b> writes a specified number of ULONG values from a caller-supplied buffer
  to a given I/O port.


## -syntax


````
VOID NdisRawWritePortBufferUlong(
  [in] ULONG_PTR Port,
  [in] PULONG    Buffer,
  [in] ULONG     Length
);
````


## -parameters




### -param Port [in]

Specifies the I/O port. This address falls in a range that was mapped during initialization with 
     <a href="..\ndis\nf-ndis-ndismregisterioportrange.md">
     NdisMRegisterIoPortRange</a>.


### -param Buffer [in]

Pointer to a caller-allocated resident buffer containing the ULONGs to be written.


### -param Length [in]

Specifies the number of ULONGs to write to the I/O port.


## -remarks



A miniport driver calls 
    <b>NdisRawWritePortBufferUlong</b> to transfer a sequence of ULONGs, one at a time, to a NIC.

<b>NdisRawWritePortBufferUlong</b> runs fast because it need not map a bus-relative port address onto a
    host-dependent logical port address at every call.




## -see-also

<a href="..\ndis\nf-ndis-ndisrawwriteportbufferushort.md">NdisRawWritePortBufferUshort</a>



<a href="..\ndis\nf-ndis-ndisrawwriteportbufferuchar.md">NdisRawWritePortBufferUchar</a>



<a href="..\ndis\nf-ndis-ndismregisterioportrange.md">NdisMRegisterIoPortRange</a>



<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>



<a href="..\ndis\nf-ndis-ndisrawwriteportulong.md">NdisRawWritePortUlong</a>



<a href="..\ndis\nf-ndis-ndisrawreadportbufferulong.md">NdisRawReadPortBufferUlong</a>



 

 


