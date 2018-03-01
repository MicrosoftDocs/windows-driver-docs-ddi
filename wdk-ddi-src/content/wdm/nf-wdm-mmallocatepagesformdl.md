---
UID: NF:wdm.MmAllocatePagesForMdl
title: MmAllocatePagesForMdl function
author: windows-driver-content
description: The MmAllocatePagesForMdl routine allocates zero-filled, nonpaged, physical memory pages to an MDL.
old-location: kernel\mmallocatepagesformdl.htm
old-project: kernel
ms.assetid: 06b52af0-c2d3-444e-8714-4fce4181dddc
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: MmAllocatePagesForMdl, MmAllocatePagesForMdl routine [Kernel-Mode Driver Architecture], k106_bb9bac91-62a6-45f8-9133-0d23eda07b1e.xml, kernel.mmallocatepagesformdl, wdm/MmAllocatePagesForMdl
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 2000 and later versions of Windows; however, MmAllocatePagesForMdlEx should be used instead of MmAllocatePagesForMdl in Windows Server 2003 Service Pack 1 (SP1) and later versions of Windows.
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
req.irql: See Remarks section.
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	MmAllocatePagesForMdl
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# MmAllocatePagesForMdl function


## -description


The <b>MmAllocatePagesForMdl</b> routine allocates zero-filled, nonpaged, physical memory pages to an MDL.


## -syntax


````
PMDL MmAllocatePagesForMdl(
  _In_ PHYSICAL_ADDRESS LowAddress,
  _In_ PHYSICAL_ADDRESS HighAddress,
  _In_ PHYSICAL_ADDRESS SkipBytes,
  _In_ SIZE_T           TotalBytes
);
````


## -parameters




### -param LowAddress [in]

Specifies the physical address of the start of the first address range from which the allocated pages can come. If <b>MmAllocatePagesForMdl</b> cannot allocate the requested number of bytes in the first address range, it iterates through additional address ranges to get more pages. At each iteration, <b>MmAllocatePagesForMdl</b> adds the value of <i>SkipBytes</i> to the previous start address to obtain the start of the next address range.


### -param HighAddress [in]

Specifies the physical address of the end of the first address range from which the allocated pages can come. 


### -param SkipBytes [in]

Specifies the number of bytes to skip from the start of the previous address range from which the allocated pages can come. <i>SkipBytes</i> must be an integer multiple of the virtual memory page size, in bytes. 


### -param TotalBytes [in]

Specifies the total number of bytes to allocate for the MDL. 


## -returns



<b>MmAllocatePagesForMdl</b> returns one of the following:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>MDL pointer</b></dt>
</dl>
</td>
<td width="60%">
The MDL pointer describes a set of physical pages in the specified address range. If the requested number of bytes is not available, the MDL describes as much physical memory as is available. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b><b>NULL</b></b></dt>
</dl>
</td>
<td width="60%">
There are no physical memory pages in the specified address ranges, or there is not enough memory pool for the MDL itself. 

</td>
</tr>
</table>
 




## -remarks



Drivers that are running in Windows Server 2003 Service Pack 1 (SP1) and later versions of Windows should use the <a href="..\wdm\nf-wdm-mmallocatepagesformdlex.md">MmAllocatePagesForMdlEx</a> routine instead of <b>MmAllocatePagesForMdl</b>. <b>MmAllocatePagesForMdlEx</b> provides better performance than <b>MmAllocatePagesForMdl</b> by avoiding unnecessary flushes of the <a href="https://msdn.microsoft.com/e934e278-40ba-42a9-a0fa-11e12c0a315d">TLB</a> and cache memory.

The physical memory pages that are returned by <b>MmAllocatePagesForMdl</b> are typically not contiguous pages. <b>MmAllocatePagesForMdl</b> always fills the allocated pages in the returned MDL with zeros.

<b>MmAllocatePagesForMdl</b> is designed to be used by kernel-mode drivers that do not need corresponding virtual addresses (that is, they need physical pages and do not need the pages to be physically contiguous) or by kernel-mode drivers that can achieve substantial performance gains if physical memory for a device is allocated in a specific physical address range. A driver for an AGP graphics card is an example of such a driver.

Depending on how much physical memory is currently available in the requested ranges, <b>MmAllocatePagesForMdl</b> might return an MDL that describes less memory than was requested. The routine returns <b>NULL</b> if no memory was allocated. The caller should check the amount of memory that is actually allocated to the MDL. 

The caller must use <a href="..\wdm\nf-wdm-mmfreepagesfrommdl.md">MmFreePagesFromMdl</a> to release the memory pages that are described by an MDL that was created by <b>MmAllocatePagesForMdl</b>. After calling <b>MmFreePagesFromMdl</b>, the caller must also call <a href="..\wdm\nf-wdm-exfreepool.md">ExFreePool</a> to release the memory that is allocated for the MDL structure itself.

In Windows 2000 and later versions of Windows, the maximum amount of memory that <b>MmAllocatePagesForMdl</b> can allocate in a single call is (4 gigabytes - PAGE_SIZE). The routine can satisfy an allocation request for this amount only if enough pages are available.

<b>MmAllocatePagesForMdl</b> runs at IRQL &lt;= APC_LEVEL. Windows Server 2008 and later versions of the Windows operating system enable <b>MmAllocatePagesForMdl</b> callers to call at DISPATCH_LEVEL. However, you can improve driver performance by calling at APC_LEVEL or below. 




## -see-also

<a href="..\wdm\nf-wdm-mmfreepagesfrommdl.md">MmFreePagesFromMdl</a>



<a href="..\wdm\nf-wdm-mmallocatepagesformdlex.md">MmAllocatePagesForMdlEx</a>



<a href="..\wdm\nf-wdm-mmmaplockedpages.md">MmMapLockedPages</a>



<a href="..\wdm\nf-wdm-exfreepool.md">ExFreePool</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20MmAllocatePagesForMdl routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

