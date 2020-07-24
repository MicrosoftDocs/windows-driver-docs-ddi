---
UID: NS:ntifs._MEMORY_BASIC_INFORMATION
title: _MEMORY_BASIC_INFORMATION (ntifs.h)
description: Contains information about a range of pages in the virtual address space of a process.
old-location: kernel\memory_basic_information.htm
tech.root: kernel
ms.assetid: AFDDB789-E412-4EF7-8C77-2020EF81DF39
ms.date: 01/02/2020
keywords: ["_MEMORY_BASIC_INFORMATION structure"]
ms.keywords: "*PMEMORY_BASIC_INFORMATION, MEMORY_BASIC_INFORMATION, MEMORY_BASIC_INFORMATION structure [Kernel-Mode Driver Architecture], MEM_COMMIT, MEM_FREE, MEM_IMAGE, MEM_MAPPED, MEM_PRIVATE, MEM_RESERVE, PAGE_EXECUTE, PAGE_GUARD, PAGE_NOACCESS, PAGE_NOCACHE, PAGE_READONLY, PAGE_READWRITE, PAGE_WRITECOMBINE, PMEMORY_BASIC_INFORMATION, PMEMORY_BASIC_INFORMATION structure pointer [Kernel-Mode Driver Architecture], _MEMORY_BASIC_INFORMATION, kernel.memory_basic_information, ntifs/MEMORY_BASIC_INFORMATION, ntifs/PMEMORY_BASIC_INFORMATION"
f1_keywords:
 - "ntifs/MEMORY_BASIC_INFORMATION"
 - "MEMORY_BASIC_INFORMATION"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ntifs.h
api_name:
- MEMORY_BASIC_INFORMATION
targetos: Windows
req.typenames: MEMORY_BASIC_INFORMATION, *PMEMORY_BASIC_INFORMATION
---

# _MEMORY_BASIC_INFORMATION structure

## -description

Contains information about a range of pages in the virtual address space of a process. The [**ZwQueryVirtualMemory**](https://msdn.microsoft.com/library/windows/hardware/dn957455) routine uses this structure.

## -struct-fields

### -field BaseAddress

A pointer to the base address of the region of pages.

### -field AllocationBase

A pointer to the base address of a range of allocated pages. The page pointed to by the **BaseAddress** member is contained within this allocation range.

### -field AllocationProtect

The memory protection option when the region was initially allocated. This member can be one of the following constants defined in wdm.h, or 0 if the caller does not have access.

| Value | Meaning |
| ----- | ------- |
| PAGE_NOACCESS 0x01   | No access to the region of pages is allowed. An attempt to read, write, or execute within the region results in an access violation. |
| PAGE_EXECUTE 0x10    | Execute access to the region of pages is allowed. An attempt to read or write within the region results in an access violation. |
| PAGE_READONLY 0x02   | Read-only and execute access to the region of pages is allowed. An attempt to write within the region results in an access violation. |
| PAGE_READWRITE 0x04  | Read, write, and execute access to the region of pages is allowed. If write access to the underlying section is allowed, then a single copy of the pages are shared. Otherwise, the pages are shared read-only/copy-on-write. |
| PAGE_GUARD 0x100     | Read, write, and execute access to the  region of pages is allowed; however, access to the region causes a "guard region entered" condition to be raised in the subject process. |
| PAGE_NOCACHE 0x200   | Disable the placement of committed pages into the data cache. |
| PAGE_WRITECOMBINE 0x400 | Disable the placement of committed pages into the data cache, combine the writes as well. |

### -field PartitionId

Reserved for system use.

### -field RegionSize

The size of the region in bytes beginning at the base address in which all pages have identical attributes.

### -field State

The state of the pages in the region. This member can be one of the following values.

| State | Meaning |
| ----- | ------- |
| MEM_COMMIT 0x1000  | Indicates committed pages for which physical storage has been allocated, either in memory or in the paging file on disk. |
| MEM_FREE 0x10000   | Indicates free pages not accessible to the calling process and available to be allocated. |
| MEM_RESERVE 0x2000 | Indicates reserved pages where a range of the process's virtual address space is reserved without any physical storage being allocated. |

### -field Protect

The access protection of the pages in the region. This member is one of the values listed for the **AllocationProtect** member.

### -field Type

The type of pages in the region. The following types are defined.

| Type | Meaning |
| ---- | ------- |
| MEM_IMAGE 0x1000000 | Indicates that the memory pages within the region are mapped into the view of an image section. |
| MEM_MAPPED 0x40000 | Indicates that the memory pages within the region are mapped into the view of a section. |
| MEM_PRIVATE 0x20000 | Indicates that the memory pages within the region are private (that is, not shared by other processes). |

## -see-also

[**ZwQueryVirtualMemory**](https://msdn.microsoft.com/library/windows/hardware/dn957455)
