---
UID: NF:wdm.ZwMapViewOfSectionEx
tech.root: kernel
title: ZwMapViewOfSectionEx
ms.date: 03/04/2024
targetos: Windows
description: 
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: wdm.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 24H2
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - ZwMapViewOfSectionEx
f1_keywords:
 - ZwMapViewOfSectionEx
 - wdm/ZwMapViewOfSectionEx
dev_langs:
 - c++
helpviewer_keywords:
 - ZwMapViewOfSectionEx
---

# ZwMapViewOfSectionEx function (wdm.h)

## -description

The **ZwMapViewOfSectionEx** routine maps a view of a section into the virtual address space of a subject process.

## -parameters

### -param SectionHandle [in]

Handle to a section object. This handle is created by a successful call to [ZwCreateSection](./nf-wdm-zwcreatesection.md) or [ZwOpenSection](./nf-wdm-zwopensection.md).

### -param ProcessHandle [in]

Handle to the object that represents the process that the view should be mapped into. Use the [ZwCurrentProcess](/windows-hardware/drivers/kernel/zwcurrentprocess) macro to specify the current process. The handle must have been opened with [**PROCESS_VM_OPERATION**](/windows/win32/procthread/process-security-and-access-rights) access.

### -param BaseAddress [in, out]

Pointer to a variable that receives the base address of the view. If the value of this parameter is not **NULL**, the view is allocated starting at the specified virtual address rounded down to the next 64-kilobyte address boundary.

### -param SectionOffset [in, out, optional]

A pointer to a variable that receives the offset, in bytes, from the beginning of the section to the view. If this pointer is not **NULL**, the offset is rounded down to the next allocation-granularity size boundary.

### -param ViewSize [in, out]

A pointer to a SIZE_T variable. If the initial value of this variable is zero, **ZwMapViewOfSectionEx** maps a view of the section that starts at *SectionOffset* and continues to the end of the section. Otherwise, the initial value specifies the view's size, in bytes. **ZwMapViewOfSectionEx** always rounds this value up to the nearest multiple of PAGE_SIZE before mapping the view.

On return, the value receives the actual size, in bytes, of the view.

### -param AllocationType [in]

Specifies a set of flags that describes the type of allocation to be performed for the specified region of pages. The valid flags are MEM_RESERVE, MEM_TOP_DOWN, MEM_LARGE_PAGES, MEM_DIFFERENT_IMAGE_BASE_OK and MEM_REPLACE_PLACEHOLDER. Although MEM_COMMIT is not allowed, it is implied unless MEM_RESERVE is specified. For more information about the MEM_*XXX* flags, see the description of the [VirtualAlloc](/windows/win32/api/memoryapi/nf-memoryapi-virtualalloc) and [MapViewOfFile3](/windows/win32/api/memoryapi/nf-memoryapi-mapviewoffile3) routines.

### -param PageProtection [in]

Specifies the [page protection](/windows/win32/Memory/memory-protection-constants) to be applied to the mapped view.

For section objects created with the SEC_IMAGE attribute, the PageProtection parameter has no effect, and can be set to any valid value such as PAGE_READONLY.

For section objects created with the SEC_IMAGE_NO_EXECUTE attribute, the PageProtection value must be set to PAGE_READONLY.

For non-image sections, the value of the PageProtection parameter must be compatible with the section's page protection that was specified when ZwCreateSection was called.  

**ZwMapViewOfSectionEx** always sets the cache type of the mapped pages to match the cache type supplied when the section object was created. For example, if ZwCreateSection was called with the SEC_NOCACHE flag, **ZwMapViewOfSectionEx** will map the pages uncached, regardless of whether the PageProtection parameter includes the PAGE_NOCACHE flag or not.

### -param ExtendedParameters [in, out, optional]

An optional pointer to one or more extended parameters of type [MEM_EXTENDED_PARAMETER](/windows/win32/api/winnt/ns-winnt-mem_extended_parameter). For more information about extended parameters, see the description of the [MapViewOfFile3](/windows/win32/api/memoryapi/nf-memoryapi-mapviewoffile3) routine.

### -param ExtendedParameterCount [in]

Specifies the number of elements in the ExtendedParameters array.

## -returns

**ZwMapViewOfSectionEx** returns an NTSTATUS value. Possible return values include the following:

| Return code | Description |
|---|---|
| **STATUS_SUCCESS** | The routine successfully performed the requested operation. |
| **STATUS_CONFLICTING_ADDRESSES** | The specified address range conflicts with a range that is already reserved. |
| **STATUS_INVALID_PAGE_PROTECTION** | The value specified for the *PageProtection* parameter is invalid. |
| **STATUS_SECTION_PROTECTION** | The value specified for the *PageProtection* parameter is incompatible with the page protection specified when the section was created. |

## -remarks

Several different views of a section can be concurrently mapped into the virtual address space of one or more processes.

Do not use **ZwMapViewOfSectionEx** to map a memory range from **\Device\PhysicalMemory** into user mode, unless your driver has directly allocated the memory range through [MmAllocatePagesForMdlEx](./nf-wdm-mmallocatepagesformdlex.md) or another method guaranteeing that no other system component has mapped the same memory range with a different [MEMORY_CACHING_TYPE](./ne-wdm-_memory_caching_type.md) value.

User applications cannot access **\Device\PhysicalMemory** directly starting with Windows Server 2003 with Service Pack 1 (SP1) and can access it only if the driver passes a handle to the application.

For more information about section objects, see [Section Objects and Views](/windows-hardware/drivers/kernel/section-objects-and-views).

If the call to this function occurs in user mode, you should use the name "**NtMapViewOfSectionEx**" instead of "**ZwMapViewOfSectionEx**".

For calls from kernel-mode drivers, the **Nt*Xxx*** and **Zw*Xxx*** versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the **Nt*Xxx*** and **Zw*Xxx*** versions of a routine, see [Using Nt and Zw Versions of the Native System Services Routines](/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines).

## -see-also

[Using Nt and Zw Versions of the Native System Services Routines](/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines)

[ZwCreateSection](./nf-wdm-zwcreatesection.md)

[ZwOpenSection](./nf-wdm-zwopensection.md)

[ZwMapViewOfSection](./nf-wdm-zwmapviewofsection.md)

[ZwUnmapViewOfSection](./nf-wdm-zwunmapviewofsection.md)

[MapViewOfFile3](/windows/win32/api/memoryapi/nf-memoryapi-mapviewoffile3)
