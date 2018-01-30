---
UID: NF:ndis.NdisDeleteNPagedLookasideList
title: NdisDeleteNPagedLookasideList macro
author: windows-driver-content
description: The NdisDeleteNPagedLookasideList function removes a nonpaged lookaside list from the system.
old-location: netvista\ndisdeletenpagedlookasidelist.htm
old-project: netvista
ms.assetid: 0622d3db-8d28-4c15-a3d8-1092487b8096
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: ndis/NdisDeleteNPagedLookasideList, NdisDeleteNPagedLookasideList macro [Network Drivers Starting with Windows Vista], ndis_lookaside_ref_37df3d7d-0aa7-4d8e-b6a5-38ab85ca929e.xml, netvista.ndisdeletenpagedlookasidelist, NdisDeleteNPagedLookasideList
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
req.ddi-compliance: Irql_Miscellaneous_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: ndis.h
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ndis.h
apiname:
-	NdisDeleteNPagedLookasideList
product: Windows
targetos: Windows
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




### -param _L

TBD




#### - Lookaside [in]

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

<mshelp:link keywords="netvista.ndisfreetonpagedlookasidelist" tabindex="0"><b>
   NdisFreeToNPagedLookasideList</b></mshelp:link>

<mshelp:link keywords="netvista.ndisallocatefromnpagedlookasidelist" tabindex="0"><b>
   NdisAllocateFromNPagedLookasideList</b></mshelp:link>

<mshelp:link keywords="netvista.ndisinitializenpagedlookasidelist" tabindex="0"><b>
   NdisInitializeNPagedLookasideList</b></mshelp:link>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisDeleteNPagedLookasideList macro%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

