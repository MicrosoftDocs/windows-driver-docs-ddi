---
UID: NF:ndis.NdisAllocateFromNPagedLookasideList
title: NdisAllocateFromNPagedLookasideList macro
description: The NdisAllocateFromNPagedLookasideList function removes the first entry from the given lookaside list head. If the lookaside list currently is empty, an entry is allocated from nonpaged pool.
old-location: netvista\ndisallocatefromnpagedlookasidelist.htm
tech.root: netvista
ms.assetid: df690a05-359d-44f0-b063-4fc21d6c4d76
ms.date: 05/02/2018
ms.keywords: NdisAllocateFromNPagedLookasideList, NdisAllocateFromNPagedLookasideList macro [Network Drivers Starting with Windows Vista], ndis/NdisAllocateFromNPagedLookasideList, ndis_lookaside_ref_455986e8-a34c-44df-b454-87416d8eccf7.xml, netvista.ndisallocatefromnpagedlookasidelist
ms.topic: macro
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see       NdisAllocateFromNPagedLookasideList (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers   (see       NdisAllocateFromNPagedLookasideList (NDIS 5.1)) in Windows XP.
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ndis.h
api_name:
-	NdisAllocateFromNPagedLookasideList
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisAllocateFromNPagedLookasideList macro


## -description


The 
  <b>NdisAllocateFromNPagedLookasideList</b> function removes the first entry from the given lookaside list
  head. If the lookaside list currently is empty, an entry is allocated from nonpaged pool.


## -parameters




### -param _L

A pointer to the head of the lookaside list from which the entry will be allocated. The caller
     already initialized the list head with the 
     <a href="https://msdn.microsoft.com/d240f2cc-18a6-4c2d-889f-e25a9486d5fe">
     NdisInitializeNPagedLookasideList</a> function.


## -remarks



If the lookaside list is not empty, 
    <b>NdisAllocateFromNPagedLookasideList</b> removes the first entry from the list and returns its address
    to the caller. If the lookaside list is empty, 
    <b>NdisAllocateFromNPagedLookasideList</b> either calls the 
    <i>Allocate</i> function, specified in the 
    <i>Allocate</i> parameter of the 
    <a href="https://msdn.microsoft.com/d240f2cc-18a6-4c2d-889f-e25a9486d5fe">
    NdisInitializeNPagedLookasideList</a> function, that the caller specified at list initialization, if
    any, or it allocates an entry on behalf of the caller. 
    <b>NdisAllocateFromNPagedLookasideList</b> returns <b>NULL</b> if the caller-supplied 
    <i>Allocate</i> function, if any, or if this function itself cannot allocate an nonpaged entry.

All entries that are allocated from a nonpaged lookaside list are of a fixed size, that was specified
    when the driver originally called 
    <b>NdisInitializeNPagedLookasideList</b>. Consequently, a lookaside list is particularly useful to
    drivers that must allocate fixed-size blocks in which to maintain state in response to dynamic I/O
    demand. For example, any connection-oriented NDIS driver might allocate the VC context areas that it
    needs from a lookaside list as VCs are created and release each such entry back to the lookaside list
    with the 
    <a href="https://msdn.microsoft.com/2405a405-177a-420a-9628-a340e0d0acb3">
    NdisFreeToNPagedLookasideList</a> function as each VC is torn down.




## -see-also




<a href="https://msdn.microsoft.com/0622d3db-8d28-4c15-a3d8-1092487b8096">
   NdisDeleteNPagedLookasideList</a>



<a href="https://msdn.microsoft.com/2405a405-177a-420a-9628-a340e0d0acb3">
   NdisFreeToNPagedLookasideList</a>



<a href="https://msdn.microsoft.com/d240f2cc-18a6-4c2d-889f-e25a9486d5fe">
   NdisInitializeNPagedLookasideList</a>
 

 

