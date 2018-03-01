---
UID: NF:ndis.NdisRawReadPortUlong
title: NdisRawReadPortUlong macro
author: windows-driver-content
description: NdisRawReadPortUlong reads a ULONG value from a given I/O port on the NIC.
old-location: netvista\ndisrawreadportulong.htm
old-project: netvista
ms.assetid: 40ecda3a-67ff-48b6-8ee9-7527c7bd9c6c
ms.author: windowsdriverdev
ms.date: 2/27/2018
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
req.lib: ndis.h
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
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisRawReadPortUlong macro


## -description


<b>NdisRawReadPortUlong</b> reads a ULONG value from a given I/O port on the NIC.


## -syntax


````
VOID NdisRawReadPortUlong(
  [in]  ULONG_PTR Port,
  [out] PULONG    Data
);
````


## -parameters




### -param Port [in]

Specifies the I/O port. This address falls in a range that was mapped during initialization with 
     <a href="..\ndis\nf-ndis-ndismregisterioportrange.md">
     NdisMRegisterIoPortRange</a>.


### -param Data [out]

Pointer to a caller-supplied variable in which this function returns a ULONG value read in from
     the port.


## -remarks



<b>NdisRawReadPortUlong</b> runs fast
    because it need not map a bus-relative I/O port address onto a host-dependent logical port address at
    every call.




## -see-also

<a href="..\ndis\nf-ndis-ndismregisterioportrange.md">NdisMRegisterIoPortRange</a>



<a href="..\ndis\nf-ndis-ndisrawreadportushort.md">NdisRawReadPortUshort</a>



<a href="..\ndis\nf-ndis-ndisrawreadportuchar.md">NdisRawReadPortUchar</a>



<a href="..\ndis\nf-ndis-ndisrawreadportbufferulong.md">NdisRawReadPortBufferUlong</a>



<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>



<a href="..\ndis\nf-ndis-ndisrawwriteportulong.md">NdisRawWritePortUlong</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisRawReadPortUlong macro%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

