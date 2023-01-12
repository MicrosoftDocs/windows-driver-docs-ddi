---
UID: NF:wdm.ZwMapViewOfSection
title: ZwMapViewOfSection function (wdm.h)
description: The ZwMapViewOfSection routine maps a view of a section into the virtual address space of a subject process.
tech.root: kernel
ms.date: 12/14/2022
keywords: ["ZwMapViewOfSection function"]
ms.keywords: NtMapViewOfSection, ZwMapViewOfSection, ZwMapViewOfSection routine [Kernel-Mode Driver Architecture], k111_cdad5afa-13b3-415e-96e8-688e7984a9fd.xml, kernel.zwmapviewofsection, wdm/NtMapViewOfSection, wdm/ZwMapViewOfSection
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: PowerIrpDDis, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - ZwMapViewOfSection
 - wdm/ZwMapViewOfSection
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - ZwMapViewOfSection
---

## -description

The **ZwMapViewOfSection** routine maps a view of a section into the virtual address space of a subject process.

## -parameters

### -param SectionHandle [in]

Handle to a section object. This handle is created by a successful call to [ZwCreateSection](./nf-wdm-zwcreatesection.md) or [ZwOpenSection](./nf-wdm-zwopensection.md).

### -param ProcessHandle [in]

Handle to the object that represents the process that the view should be mapped into. Use the [ZwCurrentProcess](/windows-hardware/drivers/kernel/zwcurrentprocess) macro to specify the current process. The handle must have been opened with [**PROCESS_VM_OPERATION**](/windows/win32/procthread/process-security-and-access-rights) access.

### -param BaseAddress [in, out]

Pointer to a variable that receives the base address of the view. If the value of this parameter is not **NULL**, the view is allocated starting at the specified virtual address rounded down to the next 64-kilobyte address boundary.

### -param ZeroBits [in]

Specifies the number of high-order address bits that must be zero in the base address of the section view. The value of this parameter must be less than 21 and is used only if *BaseAddress* is **NULL**—in other words, when the caller allows the system to determine where to allocate the view.

### -param CommitSize [in]

Specifies the size, in bytes, of the initially committed region of the view. *CommitSize* is meaningful only for page-file backed sections and is rounded up to the nearest multiple of PAGE_SIZE. (For sections that map files, both the data and the image are committed at section-creation time.)

### -param SectionOffset [in, out, optional]

A pointer to a variable that receives the offset, in bytes, from the beginning of the section to the view. If this pointer is not **NULL**, the offset is rounded down to the next allocation-granularity size boundary.

### -param ViewSize [in, out]

A pointer to a SIZE_T variable. If the initial value of this variable is zero, **ZwMapViewOfSection** maps a view of the section that starts at *SectionOffset* and continues to the end of the section. Otherwise, the initial value specifies the view's size, in bytes. **ZwMapViewOfSection** always rounds this value up to the nearest multiple of PAGE_SIZE before mapping the view.

On return, the value receives the actual size, in bytes, of the view.

### -param InheritDisposition [in]

Specifies how the view is to be shared with child processes. The possible values are:

#### ViewShare

The view will be mapped into any child processes that are created in the future.

#### ViewUnmap

The view will not be mapped into child processes.

Drivers should typically specify **ViewUnmap** for this parameter.

### -param AllocationType [in]

Specifies a set of flags that describes the type of allocation to be performed for the specified region of pages. The valid flags are MEM_LARGE_PAGES, MEM_RESERVE, and MEM_TOP_DOWN. Although MEM_COMMIT is not allowed, it is implied unless MEM_RESERVE is specified. For more information about the MEM_*XXX* flags, see the description of the [VirtualAlloc](/windows/win32/api/memoryapi/nf-memoryapi-virtualalloc) routine.

### -param Win32Protect [in]

Specifies the type of protection for the region of initially committed pages. Device and intermediate drivers should set this value to PAGE_READWRITE.

## -returns

**ZwMapViewOfSection** returns an NTSTATUS value. Possible return values include the following:

| Return code | Description |
|---|---|
| **STATUS_SUCCESS** | The routine successfully performed the requested operation. |
| **STATUS_CONFLICTING_ADDRESSES** | The specified address range conflicts with an address range already reserved, or the specified cache attribute type conflicts with the address range's existing cache attribute. For example, if the memory being mapped lies within a large page that is already mapped as fully cached, then it is illegal to request to map this memory as non-cached or write combined. |
| **STATUS_INVALID_PAGE_PROTECTION** | The value specified for the *Protect* parameter is invalid. |
| **STATUS_SECTION_PROTECTION** | The value specified for the *AllocationType* parameter is incompatible with the protection type specified when the section was created. |

## -remarks

Several different views of a section can be concurrently mapped into the virtual address space of one or more processes.

If the specified section does not exist or the access requested is not allowed, **ZwMapViewOfSection** returns an error.

Do not use **ZwMapViewOfSection** to map a memory range from **\Device\PhysicalMemory** into user mode—unless your driver has directly allocated the memory range through [MmAllocatePagesForMdl](./nf-wdm-mmallocatepagesformdl.md) or another method guaranteeing that no other system component has mapped the same memory range with a different [MEMORY_CACHING_TYPE](./ne-wdm-_memory_caching_type.md) value.

User applications cannot access **\Device\PhysicalMemory** directly starting with Windows Server 2003 with Service Pack 1 (SP1) and can access it only if the driver passes a handle to the application.

For more information about section objects, see [Section Objects and Views](/windows-hardware/drivers/kernel/section-objects-and-views).

If the call to this function occurs in user mode, you should use the name "**NtMapViewOfSection**" instead of "**ZwMapViewOfSection**".

For calls from kernel-mode drivers, the **Nt*Xxx*** and **Zw*Xxx*** versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the **Nt*Xxx*** and **Zw*Xxx*** versions of a routine, see [Using Nt and Zw Versions of the Native System Services Routines](/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines).

## -see-also

[MEMORY_CACHING_TYPE](./ne-wdm-_memory_caching_type.md)

[MmAllocatePagesForMdl](./nf-wdm-mmallocatepagesformdl.md)

[Using Nt and Zw Versions of the Native System Services Routines](/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines)

[VirtualAlloc](/windows/win32/api/memoryapi/nf-memoryapi-virtualalloc)

[ZwCurrentProcess](/windows-hardware/drivers/kernel/zwcurrentprocess)

[ZwOpenSection](./nf-wdm-zwopensection.md)

[ZwUnmapViewOfSection](./nf-wdm-zwunmapviewofsection.md)