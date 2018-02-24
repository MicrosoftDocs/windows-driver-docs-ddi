---
UID: NF:ntddk.MmAllocateNonCachedMemory
title: MmAllocateNonCachedMemory function
author: windows-driver-content
description: The MmAllocateNonCachedMemory routine allocates a virtual address range of noncached and cache-aligned memory.
old-location: kernel\mmallocatenoncachedmemory.htm
old-project: kernel
ms.assetid: aabad72e-2636-47cd-9986-f50ab5101e68
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: MmAllocateNonCachedMemory, kernel.mmallocatenoncachedmemory, MmAllocateNonCachedMemory routine [Kernel-Mode Driver Architecture], k106_a52baa62-3e10-4158-98e5-5e4dce16ee6a.xml, ntddk/MmAllocateNonCachedMemory
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlMmApcLte, HwStorPortProhibitedDDIs, SpNoWait, StorPortStartIo
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<=APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	MmAllocateNonCachedMemory
product: Windows
targetos: Windows
req.typenames: "*PWHEA_RAW_DATA_FORMAT, WHEA_RAW_DATA_FORMAT"
---

# MmAllocateNonCachedMemory function


## -description


The <b>MmAllocateNonCachedMemory</b> routine allocates a virtual address range of noncached and cache-aligned memory.


## -syntax


````
PVOID MmAllocateNonCachedMemory(
  _In_ SIZE_T NumberOfBytes
);
````


## -parameters




### -param NumberOfBytes [in]

Specifies the size in bytes of the range to be allocated. 


## -returns



If the requested memory cannot be allocated, the return value is <b>NULL</b>. Otherwise, it is the base virtual address of the allocated range. 




## -remarks



<b>MmAllocateNonCachedMemory</b> can be called from a <a href="..\wdm\nc-wdm-driver_initialize.md">DriverEntry</a> routine to allocate a noncached block of virtual memory for various device-specific buffers. The function always returns a full multiple of the virtual memory page size, of nonpaged system-address-space memory, regardless of the requested allocation size.

Noncached allocations are aligned on an integral multiple of the processor's data-cache-line size to prevent cache and coherency problems.

The physical memory pages that <b>MmAllocateNonCachedMemory</b> returns are typically not contiguous pages.

<div class="alert"><b>Note</b>  Memory that <b>MmAllocateNonCachedMemory</b> allocates is uninitialized. A kernel-mode driver must first zero this memory if it is going to make it visible to user-mode software (to avoid leaking potentially privileged contents).</div>
<div> </div>



## -see-also

<a href="..\ntddk\nf-ntddk-mmfreenoncachedmemory.md">MmFreeNonCachedMemory</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552087">KeGetDcacheFillSize</a>



<a href="..\ntddk\nf-ntddk-mmallocatecontiguousmemoryspecifycache.md">MmAllocateContiguousMemorySpecifyCache</a>



<a href="..\wdm\nc-wdm-pallocate_common_buffer.md">AllocateCommonBuffer</a>



<a href="..\ntddk\nf-ntddk-mmallocatecontiguousmemory.md">MmAllocateContiguousMemory</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20MmAllocateNonCachedMemory routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

