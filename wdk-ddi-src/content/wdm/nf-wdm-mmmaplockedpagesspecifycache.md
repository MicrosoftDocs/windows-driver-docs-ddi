---
UID: NF:wdm.MmMapLockedPagesSpecifyCache
title: MmMapLockedPagesSpecifyCache function (wdm.h)
description: The MmMapLockedPagesSpecifyCache routine maps the physical pages that are described by an MDL to a virtual address, and enables the caller to specify the cache attribute that is used to create the mapping.
tech.root: kernel
ms.date: 12/13/2022
keywords: ["MmMapLockedPagesSpecifyCache function"]
ms.keywords: MmMapLockedPagesSpecifyCache, MmMapLockedPagesSpecifyCache routine [Kernel-Mode Driver Architecture], k106_337c0e8a-c098-46a8-b820-db78be002148.xml, kernel.mmmaplockedpagesspecifycache, wdm/MmMapLockedPagesSpecifyCache
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: See Remarks section.
targetos: Windows
req.typenames: 
f1_keywords:
 - MmMapLockedPagesSpecifyCache
 - wdm/MmMapLockedPagesSpecifyCache
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - MmMapLockedPagesSpecifyCache
---

## -description

The **MmMapLockedPagesSpecifyCache** routine maps the physical pages that are described by an MDL to a virtual address, and enables the caller to specify the cache attribute that is used to create the mapping.

## -parameters

### -param MemoryDescriptorList [in]

A pointer to the MDL that is to be mapped. This MDL must describe physical pages that are locked down. A locked-down MDL can be built by the [MmProbeAndLockPages](/windows-hardware/drivers/ddi/wdm/nf-wdm-mmprobeandlockpages) or [MmAllocatePagesForMdlEx](/windows-hardware/drivers/ddi/wdm/nf-wdm-mmallocatepagesformdlex) routine. For mappings to user space, MDLs that are built by the [MmBuildMdlForNonPagedPool](/windows-hardware/drivers/ddi/wdm/nf-wdm-mmbuildmdlfornonpagedpool) routine can be used.

### -param AccessMode [in]

Specifies the access mode in which to map the MDL: **KernelMode** or **UserMode**. Almost all drivers should use **KernelMode**.

### -param CacheType [in]

Specifies a [MEMORY_CACHING_TYPE](/windows-hardware/drivers/ddi/wdm/ne-wdm-_memory_caching_type) value, which indicates the cache attribute to use to map the MDL. For more information, see the following Remarks section.

### -param RequestedAddress [in, optional]

If *AccessMode* = **UserMode**, this parameter specifies the starting user virtual address to map the MDL to, or set to **NULL** to allow the system to choose the starting address. The system might round down the requested address to fit address boundary requirements, so callers must check the return value.

### -param BugCheckOnFailure [in]

Specifies the behavior of the routine for *AccessMode* = **KernelMode** if the MDL cannot be mapped because of low system resources. If **TRUE**, the system issues a bug check. If **FALSE**, the routine returns **NULL**. Drivers must set this parameter to **FALSE**.

### -param Priority [in]

An **MM_PAGE_PRIORITY** value that indicates the importance of success when page table entries (PTEs) are scarce. Starting with Windows 8, the specified priority value can be bitwise-ORed with the **MdlMappingNoWrite** or **MdlMappingNoExecute** flags to specify memory in which writes or instruction execution are disabled. For more information about the possible values for *Priority*, see [MmGetSystemAddressForMdlSafe](../wdm/nf-wdm-mmgetsystemaddressformdlsafe.md).

## -returns

**MmMapLockedPagesSpecifyCache** returns the starting address of the mapped pages. If the pages cannot be mapped and *BugCheckOnFailure* is **FALSE**, the routine returns **NULL**.

## -remarks

Use [MmUnmapLockedPages](/windows-hardware/drivers/ddi/wdm/nf-wdm-mmunmaplockedpages) to unmap the physical pages that were mapped by **MmMapLockedPagesSpecifyCache**.

If *AccessMode* is **KernelMode**, and if **MmMapLockedPagesSpecifyCache** cannot map the specified pages, the routine returns **NULL** (if *BugCheckOnFailure* = **FALSE**), or the operating system issues a bug check (if *BugCheckOnFailure* = **TRUE**).

If *AccessMode* is **UserMode**, be aware of the following details:

- If the specified pages cannot be mapped, the routine raises an exception. Callers that specify **UserMode** must wrap the call to **MmMapLockedPagesSpecifyCache** in a **try/except** block. For more information, see [Handling Exceptions](/windows-hardware/drivers/kernel/handling-exceptions).

- The routine returns a user address that is valid in the context of the process in which the driver is running. For example, if a 64-bit driver is running in the context of a 32-bit application, the buffer is mapped to an address in the 32-bit address range of the application.

- A non-executable mapping is always created when *AccessMode* is **UserMode**. Therefore, using the **MdlMappingNoExecute** flag with the *Priority* parameter is unnecessary in this scenario. However, the **MdlMappingNoWrite** flag can still be used with the *Priority* parameter in this scenario to request a read-only mapping.

- The non-executable protection of the mapping and any write protection of the mapping specified by using the **MdlMappingNoWrite** flag with the *Priority* parameter cannot be changed by code that is running in user mode. For example, if a driver maps some pages into a user process and specifies the **MdlMappingNoWrite** flag, the system guarantees that the process cannot modify the pages.

The routine uses the *CacheType* parameter only if the pages that are described by the MDL do not already have a cache type associated with them. However, in nearly all cases, the pages already have an associated cache type, and this cache type is used by the new mapping. An exception to this rule is for pages that are allocated by [MmAllocatePagesForMdl](/windows-hardware/drivers/ddi/wdm/nf-wdm-mmallocatepagesformdl), which do not have a specific cache type associated with them. For such pages, the *CacheType* parameter determines the cache type of the mapping.

A driver must not try to create more than one system-address-space mapping for an MDL. Additionally, because an MDL that is built by the [MmBuildMdlForNonPagedPool](/windows-hardware/drivers/ddi/wdm/nf-wdm-mmbuildmdlfornonpagedpool) routine is already mapped to the system address space, a driver must not try to map this MDL into the system address space again by using the **MmMapLockedPagesSpecifyCache** routine (although creating user-address-space mappings is allowed). If it is not known whether a locked-down MDL already has a system-address-space mapping, a driver can use the [MmGetSystemAddressForMdlSafe](../wdm/nf-wdm-mmgetsystemaddressformdlsafe.md) macro instead of **MmMapLockedPagesSpecifyCache**. If the MDL is already mapped into the system address space, **MmGetSystemAddressForMdlSafe** will return the existing system-address-space mapping instead of creating a new mapping.

> [!WARNING]
> A driver that maps kernel memory into user address space must avoid exposing potentially sensitive kernel data to untrusted processes. Uninitialized buffers, such as buffers that are allocated from pool, must be explicitly filled with zeros before they are mapped. In addition, the size of a user-mode buffer that is allocated from pool must be a multiple of the virtual memory page size to prevent any part of the pages in the buffer from being used for other allocations. Finally, buffers must not be freed back to the pool while they are still mapped to user address space.

If *AccessMode* is **UserMode**, the caller must be running at IRQL <= APC_LEVEL. If *AccessMode* is **KernelMode**, the caller must be running at IRQL <= DISPATCH_LEVEL.

## -see-also

[MmAllocatePagesForMdl](/windows-hardware/drivers/ddi/wdm/nf-wdm-mmallocatepagesformdl)

[MmAllocatePagesForMdlEx](/windows-hardware/drivers/ddi/wdm/nf-wdm-mmallocatepagesformdlex)

[MmBuildMdlForNonPagedPool](/windows-hardware/drivers/ddi/wdm/nf-wdm-mmbuildmdlfornonpagedpool)

[MmGetSystemAddressForMdlSafe](../wdm/nf-wdm-mmgetsystemaddressformdlsafe.md)

[MmProbeAndLockPages](/windows-hardware/drivers/ddi/wdm/nf-wdm-mmprobeandlockpages)

[MmUnmapLockedPages](/windows-hardware/drivers/ddi/wdm/nf-wdm-mmunmaplockedpages)
