---
UID: NF:ndis.NdisFreeRWLock
title: NdisFreeRWLock function
author: windows-driver-content
description: The NdisFreeRWLock function frees a read/write lock that was previously allocated with the NdisAllocateRWLock function.
old-location: netvista\ndisfreerwlock.htm
old-project: netvista
ms.assetid: 1f54e8fe-e6a2-4ddd-9451-289d3df21fde
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.ndisfreerwlock, NdisFreeRWLock, ndis/NdisFreeRWLock, NdisFreeRWLock function [Network Drivers Starting with Windows Vista], ndis_processor_group_ref_f711221a-f265-446e-86bc-7b5b4d17f7d9.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.20 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	ndis.lib
-	ndis.dll
apiname:
-	NdisFreeRWLock
product: Windows
targetos: Windows
req.typenames: "*PNDIS_SHARED_MEMORY_USAGE, NDIS_SHARED_MEMORY_USAGE"
---

# NdisFreeRWLock function


## -description


The 
  <b>NdisFreeRWLock</b> function frees a read/write lock that was previously allocated with the 
  <a href="..\ndis\nf-ndis-ndisallocaterwlock.md">NdisAllocateRWLock</a> function.


## -syntax


````
VOID NdisFreeRWLock(
  _In_ PNDIS_RW_LOCK_EX Lock
);
````


## -parameters




### -param Lock [in]

A pointer to an opaque 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff567279">NDIS_RW_LOCK_EX</a> variable that represents a
     lock. The caller can use this lock to gain write or read access to resources that are shared among
     non-ISR driver threads.


## -returns



None




## -remarks



NDIS drivers call the 
    <b>NdisFreeRWLock</b> function to free the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff567279">NDIS_RW_LOCK_EX</a> structure and any associated
    resources that were previously allocated with the 
    <a href="..\ndis\nf-ndis-ndisallocaterwlock.md">NdisAllocateRWLock</a> function.

A driver must call the 
    <a href="..\ndis\nf-ndis-ndisreleaserwlock.md">NdisReleaseRWLock</a> function to release a
    read/write lock before it calls the 
    <b>NdisFreeRWLock</b> function.




## -see-also

<a href="..\ndis\nf-ndis-ndisreleaserwlock.md">NdisReleaseRWLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567279">NDIS_RW_LOCK_EX</a>



<a href="..\ndis\nf-ndis-ndisallocaterwlock.md">NdisAllocateRWLock</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisFreeRWLock function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

