---
UID: NF:ndis.NdisRawWritePortBufferUshort
title: NdisRawWritePortBufferUshort macro
author: windows-driver-content
description: NdisRawWritePortBufferUshort writes a specified number of USHORT values from a caller-supplied buffer to a given I/O port.
old-location: netvista\ndisrawwriteportbufferushort.htm
old-project: netvista
ms.assetid: 457b13e5-5917-4aa2-b471-bc9fde14f950
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: ndis/NdisRawWritePortBufferUshort, netvista.ndisrawwriteportbufferushort, NdisRawWritePortBufferUshort macro [Network Drivers Starting with Windows Vista], NdisRawWritePortBufferUshort, miniport_port_raw_ref_43adee77-b540-4147-92a3-0035618064de.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisRawWritePortBufferUshort   (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisRawWritePortBufferUshort   (NDIS 5.1)) in Windows XP.
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
-	NdisRawWritePortBufferUshort
product: Windows
targetos: Windows
req.typenames: *PNDIS_SHARED_MEMORY_USAGE, NDIS_SHARED_MEMORY_USAGE
---

# NdisRawWritePortBufferUshort macro


## -description


<b>NdisRawWritePortBufferUshort</b> writes a specified number of USHORT values from a caller-supplied buffer
  to a given I/O port.


## -syntax


````
VOID NdisRawWritePortBufferUshort(
  [in] ULONG_PTR Port,
  [in] PUSHORT   Buffer,
  [in] ULONG     Length
);
````


## -parameters




### -param Port [in]

Specifies the I/O port. This address falls in a range that was mapped during initialization with 
     <mshelp:link keywords="netvista.ndismregisterioportrange" tabindex="0"><b>
     NdisMRegisterIoPortRange</b></mshelp:link>.


### -param Buffer [in]

Pointer to a caller-allocated resident buffer containing the USHORTs to be written.


### -param Length [in]

Specifies the number of USHORTs to write to the I/O port.


## -remarks


A miniport driver calls 
    <b>NdisRawWritePortBufferUshort</b> to transfer a sequence of USHORTs, one at a time, to a NIC.

<b>NdisRawWritePortBufferUshort</b> runs fast because it need not map a bus-relative port address onto a
    host-dependent logical port address at every call.



## -see-also

<a href="..\ndis\nf-ndis-ndisrawwriteportbufferulong.md">NdisRawWritePortBufferUlong</a>

<a href="..\ndis\nf-ndis-ndisrawwriteportbufferuchar.md">NdisRawWritePortBufferUchar</a>

<a href="..\ndis\nf-ndis-ndismregisterioportrange.md">NdisMRegisterIoPortRange</a>

<a href="..\ndis\nf-ndis-ndisrawreadportbufferushort.md">NdisRawReadPortBufferUshort</a>

<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>

<a href="..\ndis\nf-ndis-ndisrawwriteportushort.md">NdisRawWritePortUshort</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisRawWritePortBufferUshort macro%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

