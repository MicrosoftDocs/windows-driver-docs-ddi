---
UID: NF:ndis.NdisFreeNetBufferList
title: NdisFreeNetBufferList function
author: windows-driver-content
description: Call the NdisFreeNetBufferList function to free a NET_BUFFER_LIST structure that was previously allocated from a NET_BUFFER_LIST structure pool.
old-location: netvista\ndisfreenetbufferlist.htm
tech.root: netvista
ms.assetid: fddfe5f8-900a-4f4c-8c78-a106a4a54d88
ms.date: 5/2/2018
ms.keywords: NdisFreeNetBufferList, NdisFreeNetBufferList function [Network Drivers Starting with Windows Vista], ndis/NdisFreeNetBufferList, ndis_netbuf_functions_ref_202dda58-f8c4-442b-9c18-9c9b2b7708af.xml, netvista.ndisfreenetbufferlist
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_NetBuffer_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ndis.lib
-	ndis.dll
api_name:
-	NdisFreeNetBufferList
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisFreeNetBufferList function


## -description


Call the 
  <b>NdisFreeNetBufferList</b> function to free a 
  <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structure that was previously
  allocated from a NET_BUFFER_LIST structure pool.


## -parameters




### -param NetBufferList [in]

A pointer to a NET_BUFFER_LIST structure that was allocated by calling the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff561609">NdisAllocateNetBufferList</a> or 
     <a href="https://msdn.microsoft.com/b872eff3-2d0a-4f01-874d-e00e09195801">
     NdisAllocateNetBufferAndNetBufferList</a> function.


## -returns



None




## -remarks



To allocate a 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structure from a pool, call
    the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff561609">NdisAllocateNetBufferList</a> or 
    <a href="https://msdn.microsoft.com/b872eff3-2d0a-4f01-874d-e00e09195801">
    NdisAllocateNetBufferAndNetBufferList</a> function.

The 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a> structures that are associated with
    the NET_BUFFER_LIST structure are not freed unless they were preallocated with the NET_BUFFER_LIST
    structure. You can reuse any NET_BUFFER structures that were not preallocated or you should free such
    structures separately.

If you allocated context space for a NET_BUFFER_LIST structure with the 
    <a href="https://msdn.microsoft.com/3bbad723-86bf-4206-9e51-52a66efaec20">
    NdisAllocateNetBufferListContext</a> function, you must free such context space before you free the
    NET_BUFFER_LIST structure. You must not attempt to free the context space that you allocated with 
    <b>NdisAllocateNetBufferList</b> or 
    <b>NdisAllocateNetBufferAndNetBufferList</b> by specifying the 
    <i>ContextSize</i> and 
    <i>ContextBackFill</i> parameters.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a>



<a href="https://msdn.microsoft.com/b872eff3-2d0a-4f01-874d-e00e09195801">
   NdisAllocateNetBufferAndNetBufferList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561609">NdisAllocateNetBufferList</a>



<a href="https://msdn.microsoft.com/3bbad723-86bf-4206-9e51-52a66efaec20">
   NdisAllocateNetBufferListContext</a>
 

 

