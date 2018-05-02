---
UID: NF:ndis.NdisAllocateReassembledNetBufferList
title: NdisAllocateReassembledNetBufferList function
author: windows-driver-content
description: Call the NdisAllocateReassembledNetBufferList function to reassemble a fragmented NET_BUFFER_LIST structure.
old-location: netvista\ndisallocatereassemblednetbufferlist.htm
old-project: netvista
ms.assetid: 6a7fcb43-93bf-4351-8198-1d788b1bcc8c
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: NdisAllocateReassembledNetBufferList, NdisAllocateReassembledNetBufferList function [Network Drivers Starting with Windows Vista], ndis/NdisAllocateReassembledNetBufferList, ndis_netbuf_functions_ref_20c58532-de90-4594-9bd8-5393a70c6b80.xml, netvista.ndisallocatereassemblednetbufferlist
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
-	NdisAllocateReassembledNetBufferList
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisAllocateReassembledNetBufferList function


## -description


Call the 
  <b>NdisAllocateReassembledNetBufferList</b> function to reassemble a fragmented 
  <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structure.


## -parameters




### -param FragmentNetBufferList

TBD


### -param NetBufferAndNetBufferListPoolHandle [in, optional]

A NET_BUFFER_LIST structure pool handle that was previously returned from the 
     <a href="https://msdn.microsoft.com/b117b472-0c26-41a9-b364-3d0cfbd26cc9">
     NdisAllocateNetBufferListPool</a> function. The 
     <b>fAllocateNetBuffer</b> member of the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/hh205394">NET_BUFFER_LIST_POOL_PARAMETERS</a> structure that the caller passed to 
     <b>NdisAllocateNetBufferListPool</b> must have been set to <b>TRUE</b>, and the 
     <b>DataSize</b> member set to zero. If this parameter is <b>NULL</b>, NDIS uses an internal pool.


### -param StartOffset [in]

The amount of data to skip at the beginning of each source 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a> structure. This amount is in addition
     to the value that is specified in the 
     <b>DataOffset</b> member of the NET_BUFFER structure.


### -param DataOffsetDelta [in]

The number of bytes of 
     <i>used data space</i> to add to in the reassembled NET_BUFFER structure.


### -param DataBackFill [in]

If allocation of 
     <i>unused data space</i> (backfill space) is required, this parameter specifies the number of bytes of 
     <i>unused data space</i> in addition to 
     <i>DataOffsetDelta</i> to allocate.


### -param AllocateReassembleFlags [in]

NDIS flags that can be combined with an OR operation. Set this parameter to zero. There are
     currently no flags defined for this function.


#### - FragmentedNetBufferList [in]

A pointer to the NET_BUFFER_LIST structure to reassemble.


## -returns



If the reassemble operation succeeds, 
     <b>NdisAllocateReassembledNetBufferList</b> returns a reassembled NET_BUFFER_LIST structure. If the
     operation fails, it returns <b>NULL</b>.




## -remarks



<b>NdisAllocateReassembledNetBufferList</b> allocates, initializes, and returns a new 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structure that includes one 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a> structure and one MDL chain. The new
    NET_BUFFER_LIST structure describes the same data as the fragmented source NET_BUFFER_LIST structure that
    the driver passed at 
    <i>FragmentedNetBufferList</i>. After skipping the number of bytes specified in 
    <i>StartOffset</i> in every fragmented NET_BUFFER structure, NDIS concatenates the remaining data in each
    fragmented NET_BUFFER structure into one reassembled NET_BUFFER structure. Reassembled NET_BUFFER_LIST
    structures do not include an initial 
    <a href="https://msdn.microsoft.com/e5d70be6-daa5-4d2e-94fd-5739edd8821e">
    NET_BUFFER_LIST_CONTEXT</a> structure.

Call the 
    <a href="https://msdn.microsoft.com/bcbb0c56-1500-45b2-bd20-03726ef7da77">
    NdisFreeReassembledNetBufferList</a> function to free a reassembled NET_BUFFER_LIST structure and all
    of the associated NET_BUFFER structures and MDL chains.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568389">NET_BUFFER_LIST_CONTEXT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh205394">NET_BUFFER_LIST_POOL_PARAMETERS</a>



<a href="https://msdn.microsoft.com/b117b472-0c26-41a9-b364-3d0cfbd26cc9">
   NdisAllocateNetBufferListPool</a>



<a href="https://msdn.microsoft.com/bcbb0c56-1500-45b2-bd20-03726ef7da77">
   NdisFreeReassembledNetBufferList</a>
 

 

