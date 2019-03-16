---
UID: NF:ndis.NdisInitializeNPagedLookasideList
title: NdisInitializeNPagedLookasideList function (ndis.h)
description: The NdisInitializeNPagedLookasideList function initializes a lookaside list. After a successful initialization, nonpaged fixed-size blocks can be allocated from and freed to the lookaside list.
old-location: netvista\ndisinitializenpagedlookasidelist.htm
tech.root: netvista
ms.assetid: d240f2cc-18a6-4c2d-889f-e25a9486d5fe
ms.date: 05/02/2018
ms.keywords: NdisInitializeNPagedLookasideList, NdisInitializeNPagedLookasideList function [Network Drivers Starting with Windows Vista], ndis/NdisInitializeNPagedLookasideList, ndis_lookaside_ref_edf7a9cc-c6bc-405b-88bb-c27331c38069.xml, netvista.ndisinitializenpagedlookasidelist
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see       NdisInitializeNPagedLookasideList (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see         NdisInitializeNPagedLookasideList (NDIS 5.1)) in Windows XP.
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
req.irql: "<= DISPATCH_LEVEL (see Remarks section)"
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ndis.h
api_name:
- NdisInitializeNPagedLookasideList
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisInitializeNPagedLookasideList function


## -description


The 
  <b>NdisInitializeNPagedLookasideList</b> function initializes a lookaside list. After a successful
  initialization, nonpaged fixed-size blocks can be allocated from and freed to the lookaside list.


## -parameters




### -param Lookaside [in]

A pointer to an 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff556431">NPAGED_LOOKASIDE_LIST</a> structure that
     contains the caller-supplied lookaside list head to be initialized. The structure must be 16-byte aligned on 64-bit platforms. The driver must provide a list head
     that is resident—that is, in nonpaged system space. 


### -param Allocate [in, optional]

A function entry point that is either <b>NULL</b> or specifies the entry point of a caller-supplied 
     <i>Allocate</i> function that will allocate an entry of the size that is specified in the 
     <i>Size</i> member whenever it is called. If 
     <i>Allocate</i> is <b>NULL</b>, the 
     <a href="https://msdn.microsoft.com/df690a05-359d-44f0-b063-4fc21d6c4d76">
     NdisAllocateFromNPagedLookasideList</a> function subsequently allocates entries on behalf of the
     caller. If the caller provides an 
     <i>Allocate</i> function, it also must provide a 
     <i>Free</i> function.


### -param Free [in, optional]

A function entry point that is either <b>NULL</b> or specifies the entry point of a caller-supplied 
     <i>Free</i> function that will free an entry of the size that is specified in the 
     <i>Size</i> member whenever it is called. If 
     <i>Free</i> is <b>NULL</b>, the 
     <a href="https://msdn.microsoft.com/2405a405-177a-420a-9628-a340e0d0acb3">
     NdisFreeToNPagedLookasideList</a> function subsequently frees entries on behalf of the caller.


### -param Flags [in]

Must be zero. This parameter is reserved.


### -param Size [in]

The size, in bytes, of each entry to be subsequently allocated from the lookaside list.


### -param Tag [in]

A caller-supplied pool tag for lookaside list entries. The 
     <i>Tag</i> is a string of four characters that is delimited by single quote marks (for example, 'derF').
     The characters are usually specified in reverse order so they are easier to read when dumping pool or
     tracking pool usage in the debugger.


### -param Depth [in]

Must be zero. This parameter is also reserved.


## -returns



None




## -remarks



<b>NdisInitializeNPagedLookasideList</b> initializes the caller-supplied list head but allocates no memory
    for list entries. The initial entries are allocated on an as-needed basis either with calls to the 
    <a href="https://msdn.microsoft.com/df690a05-359d-44f0-b063-4fc21d6c4d76">
    NdisAllocateFromNPagedLookasideList</a> function or by the driver-supplied 
    <i>Allocate</i> callback function at the 
    <i>Allocate</i> parameter. The list is populated as the driver frees entries back to the list with the 
    <a href="https://msdn.microsoft.com/2405a405-177a-420a-9628-a340e0d0acb3">
    NdisFreeToNPagedLookasideList</a> function. Entries collect on the list until a system-determined but
    dynamically sized limit is reached. Then, any surplus entries in the lookaside list are returned to
    nonpaged pool, either by 
    <b>NdisFreeToNPagedLookasideList</b> or with calls to the driver-supplied 
    <i>Free</i> callback function at the 
    <i>Free</i> parameter.

All entries in the lookaside list are of the same size, which is specified in the 
    <i>Size</i> parameter. A lookaside list is particularly useful to drivers that must dynamically allocate
    and free fixed-size context areas in which to maintain run-time state about their outstanding I/O
    operations. For instance, connection-oriented NDIS drivers are likely to find lookaside lists
    particularly useful because such drivers usually maintain a dynamic set of context areas to track
    outgoing and incoming calls.

It is more efficient for a driver to allow the 
    <a href="https://msdn.microsoft.com/df690a05-359d-44f0-b063-4fc21d6c4d76">
    NdisAllocateFromNPagedLookasideList</a> and 
    <a href="https://msdn.microsoft.com/2405a405-177a-420a-9628-a340e0d0acb3">
    NdisFreeToNPagedLookasideList</a> functions to manage the allocation and deallocation of entries (see
    the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff544520">ExAllocatePoolWithTag</a> and 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff544590">ExFreePool</a> functions). However, a driver that
    tracks state internally about its memory usage might supply 
    <i>Allocate</i> and 
    <i>Free</i> functions to 
    <b>NdisInitializeNPagedLookasideList</b>.

Callers of 
    <b>NdisInitializeNPagedLookasideList</b> must be running at IRQL &lt;= DISPATCH_LEVEL, but are usually
    running at PASSIVE_LEVEL.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544520">ExAllocatePoolWithTag</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544590">ExFreePool</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556431">NPAGED_LOOKASIDE_LIST</a>



<a href="https://msdn.microsoft.com/df690a05-359d-44f0-b063-4fc21d6c4d76">
   NdisAllocateFromNPagedLookasideList</a>



<a href="https://msdn.microsoft.com/0622d3db-8d28-4c15-a3d8-1092487b8096">
   NdisDeleteNPagedLookasideList</a>



<a href="https://msdn.microsoft.com/2405a405-177a-420a-9628-a340e0d0acb3">
   NdisFreeToNPagedLookasideList</a>
 

 

