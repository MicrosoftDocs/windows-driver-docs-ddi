---
UID: NF:ndis.NdisFreeToNPagedLookasideList
title: NdisFreeToNPagedLookasideList macro (ndis.h)
description: The NdisFreeToNPagedLookasideList function returns an entry to the given lookaside list.
old-location: netvista\ndisfreetonpagedlookasidelist.htm
tech.root: netvista
ms.assetid: 2405a405-177a-420a-9628-a340e0d0acb3
ms.date: 05/02/2018
ms.keywords: NdisFreeToNPagedLookasideList, NdisFreeToNPagedLookasideList macro [Network Drivers Starting with Windows Vista], ndis/NdisFreeToNPagedLookasideList, ndis_lookaside_ref_8c12e884-8f7b-4bcc-9631-2173003e4ef6.xml, netvista.ndisfreetonpagedlookasidelist
ms.topic: macro
f1_keywords:
 - "ndis/NdisFreeToNPagedLookasideList"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see       NdisFreeToNPagedLookasideList (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see       NdisFreeToNPagedLookasideList (NDIS 5.1)) in Windows XP.
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ndis.h
api_name:
- NdisFreeToNPagedLookasideList
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisFreeToNPagedLookasideList macro


## -description


The 
  <b>NdisFreeToNPagedLookasideList</b> function returns an entry to the given lookaside list.


## -parameters




### -param _L

A pointer to the head of the lookaside list to which the entry will be returned.

### -param _E

A pointer to the entry to be freed.

## -remarks



If the lookaside list has not reached the system-determined maximum number of entries, 
    <i>Entry</i> is inserted at the front of the lookaside list. If the list has reached its maximum size, 
    <i>Entry</i> is released to nonpaged pool. That is, 
    <b>NdisFreeToNPagedLookasideList</b> either calls the driver's 
    <i>Free</i> function, specified in the 
    <i>Free</i> parameter if the driver provided one to the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisinitializenpagedlookasidelist">
    NdisInitializeNPagedLookasideList</a> function, or it frees the given entry itself.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisallocatefromnpagedlookasidelist">
   NdisAllocateFromNPagedLookasideList</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisdeletenpagedlookasidelist">
   NdisDeleteNPagedLookasideList</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisinitializenpagedlookasidelist">
   NdisInitializeNPagedLookasideList</a>
 

 

