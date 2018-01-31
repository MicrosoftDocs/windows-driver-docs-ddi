---
UID: NF:ndis.NdisRawWritePortUchar
title: NdisRawWritePortUchar macro
author: windows-driver-content
description: NdisRawWritePortUchar writes a byte to an I/O port on the NIC.
old-location: netvista\ndisrawwriteportuchar.htm
old-project: netvista
ms.assetid: 9fcbf570-d272-4373-86ca-8466fb5fc18c
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: NdisRawWritePortUchar macro [Network Drivers Starting with Windows Vista], netvista.ndisrawwriteportuchar, ndis/NdisRawWritePortUchar, miniport_port_raw_ref_00cc5f8f-4965-4cc3-bdc6-25dcf2128582.xml, NdisRawWritePortUchar
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




#### - Port [in]

Specifies the I/O port. This address falls in a range that was mapped during initialization with 
     <mshelp:link keywords="netvista.ndismregisterioportrange" tabindex="0"><b>
     NdisMRegisterIoPortRange</b></mshelp:link>.


#### - Data [in]

Specifies the byte to be written.


## -remarks


<b>NdisRawWritePortUchar</b> runs fast because it need not map a bus-relative I/O port address onto a
    host-dependent logical port address at every call.



## -see-also

<a href="..\ndis\nf-ndis-ndisrawwriteportbufferuchar.md">NdisRawWritePortBufferUchar</a>

<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>

<a href="..\ndis\nf-ndis-ndisrawreadportuchar.md">NdisRawReadPortUchar</a>

<a href="..\ndis\nf-ndis-ndisrawwriteportulong.md">NdisRawWritePortUlong</a>

<a href="..\ndis\nf-ndis-ndismregisterioportrange.md">NdisMRegisterIoPortRange</a>

<a href="..\ndis\nf-ndis-ndisrawwriteportushort.md">NdisRawWritePortUshort</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisRawWritePortUchar macro%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

