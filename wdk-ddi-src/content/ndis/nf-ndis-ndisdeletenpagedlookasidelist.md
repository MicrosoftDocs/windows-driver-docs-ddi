---
UID: NF:ndis.NdisDeleteNPagedLookasideList
title: NdisDeleteNPagedLookasideList macro (ndis.h)
description: The NdisDeleteNPagedLookasideList function removes a nonpaged lookaside list from the system.
old-location: netvista\ndisdeletenpagedlookasidelist.htm
tech.root: netvista
ms.assetid: 0622d3db-8d28-4c15-a3d8-1092487b8096
ms.date: 05/02/2018
ms.keywords: NdisDeleteNPagedLookasideList, NdisDeleteNPagedLookasideList macro [Network Drivers Starting with Windows Vista], ndis/NdisDeleteNPagedLookasideList, ndis_lookaside_ref_37df3d7d-0aa7-4d8e-b6a5-38ab85ca929e.xml, netvista.ndisdeletenpagedlookasidelist
f1_keywords:
 - "ndis/NdisDeleteNPagedLookasideList"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see       NdisDeleteNPagedLookasideList (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see       NdisDeleteNPagedLookasideList (NDIS 5.1)) in Windows XP.
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
- NdisDeleteNPagedLookasideList
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisDeleteNPagedLookasideList macro


## -description


The 
  <b>NdisDeleteNPagedLookasideList</b> function removes a nonpaged lookaside list from the system.


## -parameters




### -param _L

A pointer to the head of the lookaside list to be deleted.


## -remarks



After freeing any remaining entries in the given lookaside list, 
    <b>NdisDeleteNPagedLookasideList</b> removes the list from the OS-maintained set of nonpaged lookaside
    lists.

However, 
    <b>NdisDeleteNPagedLookasideList</b> does not free the list head, for which the caller originally
    allocated the memory. An NDIS driver is responsible for calling the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfreememory">NdisFreeMemory</a> function to release any
    memory that it allocated.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatefromnpagedlookasidelist">
   NdisAllocateFromNPagedLookasideList</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfreetonpagedlookasidelist">
   NdisFreeToNPagedLookasideList</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisinitializenpagedlookasidelist">
   NdisInitializeNPagedLookasideList</a>
 

 

