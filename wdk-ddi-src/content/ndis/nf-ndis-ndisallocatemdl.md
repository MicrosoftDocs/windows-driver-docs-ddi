---
UID: NF:ndis.NdisAllocateMdl
title: NdisAllocateMdl function
author: windows-driver-content
description: The NdisAllocateMdl function allocates an MDL that describes the memory buffer at the specified virtual address.
old-location: netvista\ndisallocatemdl.htm
old-project: netvista
ms.assetid: 4863fe31-2c89-47af-99ed-02055e67621d
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ndis_netbuf_functions_ref_73b9ab32-14a8-4441-a057-c6fe91ddfb43.xml, NdisAllocateMdl, ndis/NdisAllocateMdl, NdisAllocateMdl function [Network Drivers Starting with Windows Vista], netvista.ndisallocatemdl
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_NetBuffer_Function, NdisAllocateMdl
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	ndis.lib
-	ndis.dll
apiname:
-	NdisAllocateMdl
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisAllocateMdl function


## -description


The 
  <b>NdisAllocateMdl</b> function allocates an MDL that describes the memory buffer at the specified virtual
  address.


## -syntax


````
PMDL NdisAllocateMdl(
  _In_ NDIS_HANDLE NdisHandle,
  _In_ PVOID       VirtualAddress,
  _In_ UINT        Length
);
````


## -parameters




### -param NdisHandle [in]

An NDIS handle that was obtained during caller initialization. For more information, see 
     <a href="https://msdn.microsoft.com/752b0d64-2ca3-4dc0-a6cd-642e96af1f8f">Obtaining Pool Handles</a>.


### -param VirtualAddress [in]

A pointer to the base virtual address of the buffer that the MDL is to describe.

<div class="alert"><b>Important</b>  <p class="note">The <b>VirtualAddress</b> parameter for <b>NdisAllocateMdl</b> only accepts memory from the nonpaged pool. In other words, it requires memory from <a href="..\smcnt\nf-smcnt-exallocatepool.md">ExAllocatePool</a>*(NonPagedNx), <a href="..\ndis\nf-ndis-ndisallocatememorywithtagpriority.md">NdisAllocateMemoryWithTagPriority</a>, or <a href="..\ndis\nf-ndis-ndismallocatesharedmemory.md">NdisMAllocateSharedMemory</a>. In particular, it should <b>not</b> be used with memory from the stack, paged pool, driver global data, or other memory regions.

<p class="note">If a driver needs to build an MDL for one of these non-nonpaged pool regions, it should use the appropriate kernel APIs for that type of memory, such as <a href="..\wdm\nf-wdm-ioallocatemdl.md">IoAllocateMdl</a> combined with <a href="..\wdm\nf-wdm-mmprobeandlockpages.md">MmProbeAndLockPages.</a>


</div>
<div> </div>

### -param Length [in]

The size, in bytes, of the memory buffer.


## -returns



<b>NdisAllocateMdl</b> returns a pointer to the allocated MDL. If the allocation fails, the return value
     is <b>NULL</b>.




## -remarks



All MDLs that are allocated by calling 
    <b>NdisAllocateMdl</b> must be freed by calling the 
    <a href="..\ndis\nf-ndis-ndisfreemdl.md">NdisFreeMdl</a> function.

<b>NdisAllocateMdl</b> allocates memory and builds the MDL in one step. This process is different from 
    <a href="..\wdm\nf-wdm-ioallocatemdl.md">IoAllocateMdl</a>, which only allocates memory for
    the MDL, meaning the caller must build the MDL by calling either 
    <a href="..\wdm\nf-wdm-mmbuildmdlfornonpagedpool.md">MmBuildMdlForNonPagedPool</a> or 
    <a href="..\wdm\nf-wdm-mmprobeandlockpages.md">MmProbeAndLockPages.</a>





## -see-also

<a href="..\ndis\nf-ndis-ndismallocatesharedmemory.md">NdisMAllocateSharedMemory</a>



<a href="..\wdm\nf-wdm-ioallocatemdl.md">IoAllocateMdl</a>



<a href="..\wdm\nf-wdm-mmprobeandlockpages.md">MmProbeAndLockPages</a>



<a href="..\smcnt\nf-smcnt-exallocatepool.md">ExAllocatePool</a>



<a href="..\ndis\nf-ndis-ndisfreemdl.md">NdisFreeMdl</a>



<a href="..\wdm\nf-wdm-mmbuildmdlfornonpagedpool.md">MmBuildMdlForNonPagedPool</a>



<a href="..\ndis\nf-ndis-ndisallocatememorywithtagpriority.md">NdisAllocateMemoryWithTagPriority</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisAllocateMdl function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

