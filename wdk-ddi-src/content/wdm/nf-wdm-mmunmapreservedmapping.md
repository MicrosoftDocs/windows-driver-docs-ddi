---
UID: NF:wdm.MmUnmapReservedMapping
title: MmUnmapReservedMapping function
author: windows-driver-content
description: The MmUnmapReservedMapping routine unmaps a memory buffer that was mapped by the MmMapLockedPagesWithReservedMapping routine.
old-location: kernel\mmunmapreservedmapping.htm
old-project: kernel
ms.assetid: 5f2bb0ef-af54-48e7-a2f5-8c8877bedb4a
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: MmUnmapReservedMapping, MmUnmapReservedMapping routine [Kernel-Mode Driver Architecture], k106_48bc7719-e11c-4c70-a976-c7fbecbff464.xml, kernel.mmunmapreservedmapping, wdm/MmUnmapReservedMapping
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows XP and later versions of Windows.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	MmUnmapReservedMapping
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# MmUnmapReservedMapping function


## -description


The <b>MmUnmapReservedMapping</b> routine unmaps a memory buffer that was mapped by the <a href="..\wdm\nf-wdm-mmmaplockedpageswithreservedmapping.md">MmMapLockedPagesWithReservedMapping</a> routine. 


## -syntax


````
VOID MmUnmapReservedMapping(
  _In_ PVOID BaseAddress,
  _In_ ULONG PoolTag,
  _In_ PMDLX MemoryDescriptorList
);
````


## -parameters




### -param BaseAddress [in]

Pointer to the beginning of the reserved virtual memory range. This must be an address returned by <a href="..\wdm\nf-wdm-mmmaplockedpageswithreservedmapping.md">MmMapLockedPagesWithReservedMapping</a>. 


### -param PoolTag [in]

Specifies the pool tag for the reserved memory buffer. This must be identical to the value specified in the <i>PoolTag</i> parameter of the call to <a href="..\wdm\nf-wdm-mmallocatemappingaddress.md">MmAllocateMappingAddress</a> that initially reserved the buffer.


### -param MemoryDescriptorList [in]

Pointer to the MDL that describes the physical memory mapping.


## -returns



None




## -see-also

<a href="..\wdm\nf-wdm-mmallocatemappingaddress.md">MmAllocateMappingAddress</a>



<a href="..\wdm\nf-wdm-mmfreemappingaddress.md">MmFreeMappingAddress</a>



<a href="..\wdm\nf-wdm-mmmaplockedpageswithreservedmapping.md">MmMapLockedPagesWithReservedMapping</a>



 

 


