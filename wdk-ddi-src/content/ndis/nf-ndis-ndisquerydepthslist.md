---
UID: NF:ndis.NdisQueryDepthSList
title: NdisQueryDepthSList macro (ndis.h)
description: The NdisQueryDepthSList function returns the current number of entries in a given sequenced, singly linked list.
old-location: netvista\ndisquerydepthslist.htm
tech.root: netvista
ms.assetid: 76b076d1-640b-4378-bf6d-36d87a8a5042
ms.date: 05/02/2018
keywords: ["NdisQueryDepthSList macro"]
ms.keywords: NdisQueryDepthSList, NdisQueryDepthSList macro [Network Drivers Starting with Windows Vista], ndis/NdisQueryDepthSList, ndis_interlocked_ref_f44c64cf-029a-408e-84a0-a8c09bc91592.xml, netvista.ndisquerydepthslist
f1_keywords:
 - "ndis/NdisQueryDepthSList"
 - "NdisQueryDepthSList"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisQueryDepthSList (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisQueryDepthSList (NDIS   5.1)) in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_Miscellaneous_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ndis.h
api_name:
- NdisQueryDepthSList
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisQueryDepthSList macro


## -description


The 
  <b>NdisQueryDepthSList</b> function returns the current number of entries in a given sequenced, singly
  linked list.


## -parameters




### -param SListHead [in]

A pointer to the head of the S-List to be queried, which the caller already initialized with 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisinitializeslisthead">NdisInitializeSListHead</a>.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisinitializeslisthead">NdisInitializeSListHead</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisinterlockedpopentryslist">NdisInterlockedPopEntrySList</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisinterlockedpushentryslist">
   NdisInterlockedPushEntrySList</a>
 

 

