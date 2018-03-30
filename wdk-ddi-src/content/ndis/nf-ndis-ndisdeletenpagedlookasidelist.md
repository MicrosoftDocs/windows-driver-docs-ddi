---
UID: NF:ndis.NdisDeleteNPagedLookasideList
title: NdisDeleteNPagedLookasideList macro
author: windows-driver-content
description: The NdisDeleteNPagedLookasideList function removes a nonpaged lookaside list from the system.
old-location: netvista\ndisdeletenpagedlookasidelist.htm
old-project: netvista
ms.assetid: 0622d3db-8d28-4c15-a3d8-1092487b8096
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: NdisDeleteNPagedLookasideList, NdisDeleteNPagedLookasideList macro [Network Drivers Starting with Windows Vista], ndis/NdisDeleteNPagedLookasideList, ndis_lookaside_ref_37df3d7d-0aa7-4d8e-b6a5-38ab85ca929e.xml, netvista.ndisdeletenpagedlookasidelist
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
-	NdisDeleteNPagedLookasideList
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisDeleteNPagedLookasideList macro


## -description


The 
  <b>NdisDeleteNPagedLookasideList</b> function removes a nonpaged lookaside list from the system.


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
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff562577">NdisFreeMemory</a> function to release any
    memory that it allocated.




## -see-also




<a href="https://msdn.microsoft.com/df690a05-359d-44f0-b063-4fc21d6c4d76">
   NdisAllocateFromNPagedLookasideList</a>



<a href="https://msdn.microsoft.com/2405a405-177a-420a-9628-a340e0d0acb3">
   NdisFreeToNPagedLookasideList</a>



<a href="https://msdn.microsoft.com/d240f2cc-18a6-4c2d-889f-e25a9486d5fe">
   NdisInitializeNPagedLookasideList</a>
 

 

<<<<<<< HEAD
=======
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisDeleteNPagedLookasideList macro%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

>>>>>>> parent of 2d896a8e266... Added changes
