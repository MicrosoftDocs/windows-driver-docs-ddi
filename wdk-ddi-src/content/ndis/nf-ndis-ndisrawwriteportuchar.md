---
UID: NF:ndis.NdisRawWritePortUchar
title: NdisRawWritePortUchar macro
author: windows-driver-content
description: NdisRawWritePortUchar writes a byte to an I/O port on the NIC.
old-location: netvista\ndisrawwriteportuchar.htm
old-project: netvista
ms.assetid: 9fcbf570-d272-4373-86ca-8466fb5fc18c
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: NdisRawWritePortUchar, NdisRawWritePortUchar macro [Network Drivers Starting with Windows Vista], miniport_port_raw_ref_00cc5f8f-4965-4cc3-bdc6-25dcf2128582.xml, ndis/NdisRawWritePortUchar, netvista.ndisrawwriteportuchar
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisRawWritePortUchar (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisRawWritePortUchar (NDIS   5.1)) in Windows XP.
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
-	NdisRawWritePortUchar
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisRawWritePortUchar macro


## -description


<b>NdisRawWritePortUchar</b> writes a byte to an I/O port on the NIC.


## -syntax


````
VOID NdisRawWritePortUchar(
  [in] ULONG_PTR Port,
  [in] UCHAR     Data
);
````


## -parameters




### -param Port [in]

Specifies the I/O port. This address falls in a range that was mapped during initialization with 
     <a href="..\ndis\nf-ndis-ndismregisterioportrange.md">
     NdisMRegisterIoPortRange</a>.


### -param Data [in]

Specifies the byte to be written.


## -remarks



<b>NdisRawWritePortUchar</b> runs fast because it need not map a bus-relative I/O port address onto a
    host-dependent logical port address at every call.




## -see-also

<a href="..\ndis\nf-ndis-ndisrawwriteportushort.md">NdisRawWritePortUshort</a>



<a href="..\ndis\nf-ndis-ndisrawreadportuchar.md">NdisRawReadPortUchar</a>



<a href="..\ndis\nf-ndis-ndisrawwriteportbufferuchar.md">NdisRawWritePortBufferUchar</a>



<a href="..\ndis\nf-ndis-ndismregisterioportrange.md">NdisMRegisterIoPortRange</a>



<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>



<a href="..\ndis\nf-ndis-ndisrawwriteportulong.md">NdisRawWritePortUlong</a>



 

 


