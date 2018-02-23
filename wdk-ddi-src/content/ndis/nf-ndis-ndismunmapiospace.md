---
UID: NF:ndis.NdisMUnmapIoSpace
title: NdisMUnmapIoSpace function
author: windows-driver-content
description: NdisMUnmapIoSpace releases a virtual range mapped by an initialization-time call to NdisMMapIoSpace.
old-location: netvista\ndismunmapiospace.htm
old-project: netvista
ms.assetid: 068232d3-b160-4090-b72c-63d9a31c1567
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: NdisMUnmapIoSpace, miniport_memory_mapped_ref_b10c4068-0218-4349-8d87-5a9d9a32aac7.xml, NdisMUnmapIoSpace function [Network Drivers Starting with Windows Vista], netvista.ndismunmapiospace, ndis/NdisMUnmapIoSpace
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisMUnmapIoSpace (NDIS 5.1)) in   Windows Vista. Supported for NDIS 5.1 drivers (see    NdisMUnmapIoSpace (NDIS 5.1)) in   Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_Miniport_Driver_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	ndis.lib
-	ndis.dll
apiname:
-	NdisMUnmapIoSpace
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisMUnmapIoSpace function


## -description


<b>NdisMUnmapIoSpace</b> releases a virtual range mapped by an initialization-time call to 
  <a href="..\ndis\nf-ndis-ndismmapiospace.md">NdisMMapIoSpace</a>.


## -syntax


````
VOID NdisMUnmapIoSpace(
  _In_ NDIS_HANDLE MiniportAdapterHandle,
  _In_ PVOID       VirtualAddress,
  _In_ UINT        Length
);
````


## -parameters




### -param MiniportAdapterHandle [in]

Specifies the handle originally input to 
     <a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>.


### -param VirtualAddress [in]

Specifies the base virtual address for the mapped range that was returned by 
     <b>NdisMMapIoSpace</b>.


### -param Length [in]

Specifies the number of bytes in the range that was mapped with 
     <b>NdisMMapIoSpace</b>.


## -returns



None




## -remarks



When a miniport driver is unloading, any memory range that it mapped during initialization with 
    <a href="..\ndis\nf-ndis-ndismmapiospace.md">NdisMMapIoSpace</a> must be released with a
    call to 
    <b>NdisMUnmapIoSpace</b>.

The 
    <i>Length</i> passed to 
    <b>NdisMUnmapIoSpace</b> must match the 
    <i>Length</i> originally passed to 
    <b>NdisMMapIoSpace</b>.

<b>NdisMUnmapIoSpace</b> can be called only from a miniport driver's 
    <a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a> and 
    <a href="..\ndis\nc-ndis-miniport_halt.md">MiniportHaltEx</a> functions.




## -see-also

<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>



<a href="..\ndis\nc-ndis-miniport_halt.md">MiniportHaltEx</a>



<a href="..\ndis\nf-ndis-ndismmapiospace.md">NdisMMapIoSpace</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisMUnmapIoSpace function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

