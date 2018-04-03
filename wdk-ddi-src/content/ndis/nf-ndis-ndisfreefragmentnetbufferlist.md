---
UID: NF:ndis.NdisFreeFragmentNetBufferList
title: NdisFreeFragmentNetBufferList function
author: windows-driver-content
description: Call the NdisFreeFragmentNetBufferList function to free a NET_BUFFER_LIST structure and all associated NET_BUFFER structures and MDL chains that were previously allocated by the calling NdisAllocateFragmentNetBufferList function.
old-location: netvista\ndisfreefragmentnetbufferlist.htm
old-project: netvista
ms.assetid: 2bbf85ee-8541-4d3d-87e5-0633bc35670b
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: NdisFreeFragmentNetBufferList, NdisFreeFragmentNetBufferList function [Network Drivers Starting with Windows Vista], ndis/NdisFreeFragmentNetBufferList, ndis_netbuf_functions_ref_e88011a7-4c83-4736-8a3f-3a2d1c3b2e6f.xml, netvista.ndisfreefragmentnetbufferlist
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	NdisFreeFragmentNetBufferList
product:
- Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisFreeFragmentNetBufferList function


## -description


Call the 
  <b>NdisFreeFragmentNetBufferList</b> function to free a 
  <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structure and all associated 
  <a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a> structures and MDL chains that were
  previously allocated by the calling 
  <a href="https://msdn.microsoft.com/40b6596b-7ab8-4336-8c38-21b9f32d8558">
  NdisAllocateFragmentNetBufferList</a> function.


## -parameters




### -param FragmentNetBufferList [in]

A pointer to a NET_BUFFER_LIST structure that was allocated by calling 
     <b>NdisAllocateFragmentNetBufferList</b>.


### -param DataOffsetDelta [in]

The amount, in bytes, to advance (add to the data offset) the fragment NET_BUFFER structures
     before freeing them. This value should match the value of the 
     <i>DataOffsetDelta</i> parameter that was passed to 
     <b>NdisAllocateFragmentNetBufferList</b> when the NET_BUFFER_LIST structure was created.


### -param FreeFragmentFlags [in]

NDIS flags that can be combined with an OR operation. Set this parameter to zero. There are
     currently no flags defined for this function.


## -returns



None




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a>



<a href="https://msdn.microsoft.com/40b6596b-7ab8-4336-8c38-21b9f32d8558">
   NdisAllocateFragmentNetBufferList</a>
 

 

