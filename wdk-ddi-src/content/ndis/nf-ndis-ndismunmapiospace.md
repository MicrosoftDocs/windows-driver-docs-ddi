---
UID: NF:ndis.NdisMUnmapIoSpace
title: NdisMUnmapIoSpace function (ndis.h)
description: NdisMUnmapIoSpace releases a virtual range mapped by an initialization-time call to NdisMMapIoSpace.
old-location: netvista\ndismunmapiospace.htm
tech.root: netvista
ms.assetid: 068232d3-b160-4090-b72c-63d9a31c1567
ms.date: 05/02/2018
ms.keywords: NdisMUnmapIoSpace, NdisMUnmapIoSpace function [Network Drivers Starting with Windows Vista], miniport_memory_mapped_ref_b10c4068-0218-4349-8d87-5a9d9a32aac7.xml, ndis/NdisMUnmapIoSpace, netvista.ndismunmapiospace
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
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- ndis.lib
- ndis.dll
api_name:
- NdisMUnmapIoSpace
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisMUnmapIoSpace function


## -description


<b>NdisMUnmapIoSpace</b> releases a virtual range mapped by an initialization-time call to 
  <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/ndis-ndismmapiospace">NdisMMapIoSpace</a>.


## -parameters




### -param MiniportAdapterHandle [in]

Specifies the handle originally input to 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a>.


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
    <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/ndis-ndismmapiospace">NdisMMapIoSpace</a> must be released with a
    call to 
    <b>NdisMUnmapIoSpace</b>.

The 
    <i>Length</i> passed to 
    <b>NdisMUnmapIoSpace</b> must match the 
    <i>Length</i> originally passed to 
    <b>NdisMMapIoSpace</b>.

<b>NdisMUnmapIoSpace</b> can be called only from a miniport driver's 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a> and 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_halt">MiniportHaltEx</a> functions.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_halt">MiniportHaltEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/ndis-ndismmapiospace">NdisMMapIoSpace</a>
 

 

