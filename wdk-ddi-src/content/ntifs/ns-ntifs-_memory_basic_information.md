---
UID: NS:ntifs._MEMORY_BASIC_INFORMATION
title: "_MEMORY_BASIC_INFORMATION"
author: windows-driver-content
description: Contains information about a range of pages in the virtual address space of a process.
old-location: kernel\memory_basic_information.htm
old-project: kernel
ms.assetid: AFDDB789-E412-4EF7-8C77-2020EF81DF39
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: MEMORY_BASIC_INFORMATION, ntifs/PMEMORY_BASIC_INFORMATION, kernel.memory_basic_information, MEM_COMMIT, MEM_RESERVE, MEM_PRIVATE, MEM_IMAGE, PAGE_NOACCESS, MEMORY_BASIC_INFORMATION structure [Kernel-Mode Driver Architecture], PAGE_WRITECOMBINE, PAGE_READONLY, MEM_FREE, PAGE_EXECUTE, PMEMORY_BASIC_INFORMATION structure pointer [Kernel-Mode Driver Architecture], PMEMORY_BASIC_INFORMATION, PAGE_NOCACHE, ntifs/MEMORY_BASIC_INFORMATION, PAGE_READWRITE, PAGE_GUARD, *PMEMORY_BASIC_INFORMATION, _MEMORY_BASIC_INFORMATION, MEM_MAPPED
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntifs.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 10.
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
req.lib: 
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntifs.h
apiname:
-	MEMORY_BASIC_INFORMATION
product: Windows
targetos: Windows
req.typenames: MEMORY_BASIC_INFORMATION, *PMEMORY_BASIC_INFORMATION
---

# _MEMORY_BASIC_INFORMATION structure


## -description


Contains information about a range of pages in the virtual address space of a process. The 
<a href="..\ntifs\nf-ntifs-zwqueryvirtualmemory.md">ZwQueryVirtualMemory</a> routine uses this structure.


## -syntax


````
typedef struct _MEMORY_BASIC_INFORMATION {
  PVOID  BaseAddress;
  PVOID  AllocationBase;
  DWORD  AllocationProtect;
  SIZE_T RegionSize;
  DWORD  State;
  DWORD  Protect;
  DWORD  Type;
} MEMORY_BASIC_INFORMATION, *PMEMORY_BASIC_INFORMATION;
````


## -struct-fields




### -field BaseAddress

A pointer to the base address of the region of pages.


### -field AllocationBase

A pointer to the base address of a range of allocated pages. The page pointed to by the <b>BaseAddress</b> member is contained within this allocation range.


### -field AllocationProtect

The memory protection option when the region was initially allocated. This member can be one of the 
following constants defined in wdm.h, or 0 if the caller does not have access.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="PAGE_NOACCESS"></a><a id="page_noaccess"></a><dl>
<dt><b>PAGE_NOACCESS</b></dt>
<dt>0x01</dt>
</dl>
</td>
<td width="60%">
No access to the region of pages is allowed.
                                An attempt to read, write, or execute within
                                the region results in an access violation.

</td>
</tr>
<tr>
<td width="40%"><a id="PAGE_EXECUTE"></a><a id="page_execute"></a><dl>
<dt><b>PAGE_EXECUTE</b></dt>
<dt>0x10</dt>
</dl>
</td>
<td width="60%">
Execute access to the region of pages
                               is allowed. An attempt to read or write within
                               the region results in an access violation.

</td>
</tr>
<tr>
<td width="40%"><a id="PAGE_READONLY"></a><a id="page_readonly"></a><dl>
<dt><b>PAGE_READONLY</b></dt>
<dt>0x02</dt>
</dl>
</td>
<td width="60%">
Read-only and execute access to the region
                                of pages is allowed. An attempt to write within
                                the region results in an access violation.

</td>
</tr>
<tr>
<td width="40%"><a id="PAGE_READWRITE"></a><a id="page_readwrite"></a><dl>
<dt><b>PAGE_READWRITE</b></dt>
<dt>0x04</dt>
</dl>
</td>
<td width="60%">
Read, write, and execute access to the region
                                 of pages is allowed. If write access to the
                                 underlying section is allowed, then a single
                                 copy of the pages are shared. Otherwise,
                                 the pages are shared read-only/copy-on-write.

</td>
</tr>
<tr>
<td width="40%"><a id="PAGE_GUARD"></a><a id="page_guard"></a><dl>
<dt><b>PAGE_GUARD</b></dt>
<dt>0x100</dt>
</dl>
</td>
<td width="60%">
Read, write, and execute access to the
                             region of pages is allowed; however, access to
                             the region causes a "guard region entered"
                             condition to be raised in the subject process.

</td>
</tr>
<tr>
<td width="40%"><a id="PAGE_NOCACHE"></a><a id="page_nocache"></a><dl>
<dt><b>PAGE_NOCACHE</b></dt>
<dt>0x200</dt>
</dl>
</td>
<td width="60%">
Disable the placement of committed
                               pages into the data cache.

</td>
</tr>
<tr>
<td width="40%"><a id="PAGE_WRITECOMBINE"></a><a id="page_writecombine"></a><dl>
<dt><b>PAGE_WRITECOMBINE</b></dt>
<dt>0x400</dt>
</dl>
</td>
<td width="60%">
Disable the placement of committed
                                    pages into the data cache, combine the
                                    writes as well.

</td>
</tr>
</table>
 


### -field RegionSize

The size of the region in bytes beginning at
                               the base address in which all pages have
                               identical attributes.


### -field State

The state of the pages in the region. This member can be one of the following values. 



<table>
<tr>
<th>State</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="MEM_COMMIT"></a><a id="mem_commit"></a><dl>
<dt><b>MEM_COMMIT</b></dt>
<dt>0x1000</dt>
</dl>
</td>
<td width="60%">
Indicates committed pages for which physical storage has been allocated, either in memory or in the paging file on disk.

</td>
</tr>
<tr>
<td width="40%"><a id="MEM_FREE"></a><a id="mem_free"></a><dl>
<dt><b>MEM_FREE</b></dt>
<dt>0x10000</dt>
</dl>
</td>
<td width="60%">
Indicates free pages not accessible to the calling process and available to be allocated. 

</td>
</tr>
<tr>
<td width="40%"><a id="MEM_RESERVE"></a><a id="mem_reserve"></a><dl>
<dt><b>MEM_RESERVE</b></dt>
<dt>0x2000</dt>
</dl>
</td>
<td width="60%">
Indicates reserved pages where a range of the process's virtual address space is reserved without any physical storage being allocated.

</td>
</tr>
</table>
 


### -field Protect

The access protection of the pages in the region. This member is one of the values listed for the <b>AllocationProtect</b> member.


### -field Type

The type of pages in the region. The following types are defined. 



<table>
<tr>
<th>Type</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="MEM_IMAGE"></a><a id="mem_image"></a><dl>
<dt><b>MEM_IMAGE</b></dt>
<dt>0x1000000</dt>
</dl>
</td>
<td width="60%">
Indicates that the memory pages within the region are mapped into the view of an image section.

</td>
</tr>
<tr>
<td width="40%"><a id="MEM_MAPPED"></a><a id="mem_mapped"></a><dl>
<dt><b>MEM_MAPPED</b></dt>
<dt>0x40000</dt>
</dl>
</td>
<td width="60%">
Indicates that the memory pages within the region are mapped into the view of a section.

</td>
</tr>
<tr>
<td width="40%"><a id="MEM_PRIVATE"></a><a id="mem_private"></a><dl>
<dt><b>MEM_PRIVATE</b></dt>
<dt>0x20000</dt>
</dl>
</td>
<td width="60%">
Indicates that the memory pages within the region are private (that is, not shared by other processes).

</td>
</tr>
</table>
 


## -see-also

<a href="..\ntifs\nf-ntifs-zwqueryvirtualmemory.md">ZwQueryVirtualMemory</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20MEMORY_BASIC_INFORMATION structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

