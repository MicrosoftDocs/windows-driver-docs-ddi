---
UID: NF:ndis.NdisRawWritePortBufferUchar
title: NdisRawWritePortBufferUchar macro
author: windows-driver-content
description: NdisRawWritePortBufferUchar writes a specified number of bytes from a caller-supplied buffer to a given I/O port.
old-location: netvista\ndisrawwriteportbufferuchar.htm
old-project: netvista
ms.assetid: 2e802f1c-1d27-43cb-a69d-023519806fc2
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: NdisRawWritePortBufferUchar macro [Network Drivers Starting with Windows Vista], NdisRawWritePortBufferUchar, miniport_port_raw_ref_4b54b55d-c94d-4401-8d16-4650d80c620c.xml, netvista.ndisrawwriteportbufferuchar, ndis/NdisRawWritePortBufferUchar
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisRawWritePortBufferUchar   (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisRawWritePortBufferUchar   (NDIS 5.1)) in Windows XP.
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ndis.h
apiname:
-	NdisRawWritePortBufferUchar
product: Windows
targetos: Windows
req.typenames: "*PNDIS_SHARED_MEMORY_USAGE, NDIS_SHARED_MEMORY_USAGE"
---

# NdisRawWritePortBufferUchar macro


## -description


<b>NdisRawWritePortBufferUchar</b> writes a specified number of bytes from a caller-supplied buffer to a
  given I/O port.


## -syntax


````
VOID NdisRawWritePortBufferUchar(
  [in] ULONG_PTR Port,
  [in] PUCHAR    Buffer,
  [in] ULONG     Length
);
````


## -parameters




### -param Port [in]

Specifies the I/O port. This address falls in a range that was mapped during initialization with 
     <a href="..\ndis\nf-ndis-ndismregisterioportrange.md">
     NdisMRegisterIoPortRange</a>.


### -param Buffer [in]

Pointer to a caller-allocated resident buffer containing the bytes to be written.


### -param Length [in]

Specifies the number of bytes to write to the I/O port.


## -remarks



A miniport driver calls 
    <b>NdisRawWritePortBufferUchar</b> to transfer a sequence of bytes, one at a time, to a NIC.

<b>NdisRawWritePortBufferUchar</b> runs fast because it need not map a bus-relative port address onto a
    host-dependent logical port address at every call.




## -see-also

<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>



<a href="..\ndis\nf-ndis-ndismregisterioportrange.md">NdisMRegisterIoPortRange</a>



<a href="..\ndis\nf-ndis-ndisrawwriteportbufferulong.md">NdisRawWritePortBufferUlong</a>



<a href="..\ndis\nf-ndis-ndisrawreadportbufferuchar.md">NdisRawReadPortBufferUchar</a>



<a href="..\ndis\nf-ndis-ndisrawwriteportuchar.md">NdisRawWritePortUchar</a>



<a href="..\ndis\nf-ndis-ndisrawwriteportbufferushort.md">NdisRawWritePortBufferUshort</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisRawWritePortBufferUchar macro%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

