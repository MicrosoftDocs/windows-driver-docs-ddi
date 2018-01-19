---
UID: NF:ndis.NdisDeleteNPagedLookasideList
title: NdisDeleteNPagedLookasideList macro
author: windows-driver-content
description: The NdisDeleteNPagedLookasideList function removes a nonpaged lookaside list from the system.
old-location: netvista\ndisdeletenpagedlookasidelist.htm
old-project: netvista
ms.assetid: 0622d3db-8d28-4c15-a3d8-1092487b8096
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: NdisDeleteNPagedLookasideList
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see       NdisDeleteNPagedLookasideList (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see       NdisDeleteNPagedLookasideList (NDIS 5.1)) in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisDeleteNPagedLookasideList
req.alt-loc: ndis.h
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
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisDeleteNPagedLookasideList macro



## -description
The 
  <b>NdisDeleteNPagedLookasideList</b> function removes a nonpaged lookaside list from the system.



## -syntax

````
VOID NdisDeleteNPagedLookasideList(
  [in] PNPAGED_LOOKASIDE_LIST Lookaside
);
````


## -parameters

### -param Lookaside [in]

A pointer to the head of the lookaside list to be deleted.


## -remarks
After freeing any remaining entries in the given lookaside list, 
    <b>NdisDeleteNPagedLookasideList</b> removes the list from the OS-maintained set of nonpaged lookaside
    lists.

However, 
    <b>NdisDeleteNPagedLookasideList</b> does not free the list head, for which the caller originally
    allocated the memory. An NDIS driver is responsible for calling the 
    <a href="..\ndis\nf-ndis-ndisfreememory.md">NdisFreeMemory</a> function to release any
    memory that it allocated.


## -see-also
<dl>
<dt>
<a href="..\ndis\nf-ndis-ndisallocatefromnpagedlookasidelist.md">
   NdisAllocateFromNPagedLookasideList</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisfreetonpagedlookasidelist.md">
   NdisFreeToNPagedLookasideList</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisinitializenpagedlookasidelist.md">
   NdisInitializeNPagedLookasideList</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisDeleteNPagedLookasideList macro%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

