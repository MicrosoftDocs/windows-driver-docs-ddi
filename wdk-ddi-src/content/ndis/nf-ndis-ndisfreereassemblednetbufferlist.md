---
UID: NF:ndis.NdisFreeReassembledNetBufferList
title: NdisFreeReassembledNetBufferList function
author: windows-driver-content
description: Call the NdisFreeReassembledNetBufferList function to free a reassembled NET_BUFFER_LIST structure and the associated NET_BUFFER structure and MDL chain.
old-location: netvista\ndisfreereassemblednetbufferlist.htm
old-project: netvista
ms.assetid: bcbb0c56-1500-45b2-bd20-03726ef7da77
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: NdisFreeReassembledNetBufferList, NdisFreeReassembledNetBufferList function [Network Drivers Starting with Windows Vista], ndis/NdisFreeReassembledNetBufferList, ndis_netbuf_functions_ref_604900da-90fb-4986-880e-8fea63c240a0.xml, netvista.ndisfreereassemblednetbufferlist
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
-	NdisFreeReassembledNetBufferList
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisFreeReassembledNetBufferList function


## -description


Call the 
  <b>NdisFreeReassembledNetBufferList</b> function to free a reassembled 
  <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structure and the associated 
  <a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a> structure and MDL chain.


## -parameters




### -param ReassembledNetBufferList [in]

A pointer to a NET_BUFFER_LIST structure that the driver allocated by calling the 
     <a href="https://msdn.microsoft.com/6a7fcb43-93bf-4351-8198-1d788b1bcc8c">
     NdisAllocateReassembledNetBufferList</a> function.


### -param DataOffsetDelta [in]

The number of bytes to advance (add to) the 
     <b>DataOffset</b> member of the reassembled NET_BUFFER structure before freeing the structure. This value
     should match 
     <i>DataOffsetDelta</i> that the driver passed to 
     <b>NdisAllocateReassembledNetBufferList</b>.


### -param FreeReassembleFlags [in]

NDIS flags that can be combined with an OR operation. Set this parameter to zero. There are
     currently no flags defined for this function.


## -returns



None




## -remarks



<b>NdisFreeReassembledNetBufferList</b> frees a reassembled 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structure that the caller
    allocated by calling 
    <a href="https://msdn.microsoft.com/6a7fcb43-93bf-4351-8198-1d788b1bcc8c">
    NdisAllocateReassembledNetBufferList</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a>



<a href="https://msdn.microsoft.com/6a7fcb43-93bf-4351-8198-1d788b1bcc8c">
   NdisAllocateReassembledNetBufferList</a>
 

 

