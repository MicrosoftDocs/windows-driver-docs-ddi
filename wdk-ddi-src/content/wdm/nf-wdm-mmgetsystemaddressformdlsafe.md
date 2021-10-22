---
UID: NF:wdm.MmGetSystemAddressForMdlSafe
tech.root: 
title: MmGetSystemAddressForMdlSafe
ms.date: 07/16/2021
targetos: Windows
description: "Learn more about: MmGetSystemAddressForMdlSafe"
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: wdm.h
req.idl: 
req.include-header: 
req.irql: <= DISPATCH_LEVEL
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 2000
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
 - MmGetSystemAddressForMdlSafe
f1_keywords:
 - MmGetSystemAddressForMdlSafe
 - wdm/MmGetSystemAddressForMdlSafe
dev_langs:
 - c++
---

## -description

The **MmGetSystemAddressForMdlSafe** macro returns a nonpaged system-space virtual address for the buffer that the specified MDL describes.

## -parameters

### -param Mdl [in]


Pointer to a buffer whose corresponding base virtual address is to be mapped.

### -param Priority [in]


Specifies an **MM_PAGE_PRIORITY** value that indicates the importance of success under low available PTE conditions. Specify a priority value of **LowPagePriority**, **NormalPagePriority**, or **HighPagePriority**. Starting with Windows 8, the specified priority value can be bitwise-ORed with the **MdlMappingNoWrite** or **MdlMappingNoExecute** flags.

*   **LowPagePriority** indicates that the mapping request can fail if the system is fairly low on resources. An example of this situation is a noncritical network connection where the driver can handle the mapping failure.

*   **NormalPagePriority** indicates that the mapping request can fail if the system is very low on resources. An example of this situation is a noncritical local file system request.

*   **HighPagePriority** indicates that the mapping request must not fail unless the system is completely out of resources. An example of this situation is the paging file path in a driver.

*   **MdlMappingNoWrite** indicates that the mapped physical pages are to be configured as no-write (read only) memory. Starting with Windows 8, this flag bit can be bitwise-ORed with the **MM_PAGE_PRIORITY** value to specify memory in which writes are disabled.

*   **MdlMappingNoExecute** indicates that the mapped physical pages are to be configured as no-execute memory. Starting with Windows 8, this flag bit can be bitwise-ORed with the **MM_PAGE_PRIORITY** value to specify memory in which instruction execution is disabled. As a best practice, drivers written for Windows 8 and later versions of Windows should always specify no-execute memory unless executable memory is explicitly required.


## -returns

**MmGetSystemAddressForMdlSafe** returns the base system-space virtual address that maps the physical pages that the specified MDL describes. If the pages are not already mapped to system address space and the attempt to map them fails, **NULL** is returned.

## -remarks

This routine maps the physical pages that are described by the specified MDL into system address space, if they are not already mapped to system address space.

Drivers of programmed-I/O (PIO) devices call this routine to map a user-mode buffer, which is described by the MDL at **Irp->MdlAddress** and which is already mapped to a user-mode virtual address range, to a range in system address space.

On entry to this routine, the specified MDL must describe physical pages that are locked down. A locked-down MDL can be built by using the [**MmProbeAndLockPages**](./nf-wdm-mmprobeandlockpages.md), [**MmBuildMdlForNonPagedPool**](./nf-wdm-mmbuildmdlfornonpagedpool.md), [**IoBuildPartialMdl**](./nf-wdm-iobuildpartialmdl.md), or [**MmAllocatePagesForMdlEx**](./nf-wdm-mmallocatepagesformdlex.md) routine.

When the system-address-space mapping that is returned by **MmGetSystemAddressForMdlSafe** is no longer needed, it must be released. The steps that are required to release the mapping depend on how the MDL was built. These are the four possible cases:

*   If the MDL was built by a call to the **MmProbeAndLockPages** routine, it is not necessary to explicitly release the system-address-space mapping. Instead, a call to the [**MmUnlockPages**](./nf-wdm-mmunlockpages.md) routine releases the mapping, if one was allocated.

*   If the MDL was built by a call to the **MmBuildMdlForNonPagedPool** routine, **MmGetSystemAddressForMdlSafe** reuses the existing system-address-space mapping instead of creating a new one. In this case, no cleanup is required (that is, unlocking and unmapping are not necessary).

*   If the MDL was built by a call to the **IoBuildPartialMdl** routine, the driver must call either the **MmPrepareMdlForReuse** routine or the [**IoFreeMdl**](./nf-wdm-iofreemdl.md) routine to release the system-address-space mapping.

*   If the MDL was built by a call to the **MmAllocatePagesForMdlEx** routine, the driver must call the **MmUnmapLockedPages** routine to release the system-address-space mapping. If **MmGetSystemAddressForMdlSafe** is called more than one time for an MDL, subsequent **MmGetSystemAddressForMdlSafe** calls simply return the mapping that was created by the first call. One call to **MmUnmapLockedPages** is sufficient to release this mapping.

Starting with Windows 7 and Windows Server 2008 R2, it is not necessary to explicitly call **MmUnmapLockedPages** for an MDL that was created by **MmAllocatePagesForMdlEx**. Instead, a call to the [**MmFreePagesFromMdl**](./nf-wdm-mmfreepagesfrommdl.md) routine releases the system-address-space mapping, if one was allocated.

To create a new system-address-space mapping, **MmGetSystemAddressForMdlSafe** calls **MmMapLockedPagesSpecifyCache** with the _CacheType_ parameter set to **MmCached**. A driver that requires a cache type other than **MmCached** should call **MmMapLockedPagesSpecifyCache** directly instead of calling **MmGetSystemAddressForMdlSafe**. For more information about the _CacheType_ parameter, see [**MmMapLockedPagesSpecifyCache**](./nf-wdm-mmmaplockedpagesspecifycache.md).

In a call to **MmMapLockedPagesSpecifyCache**, the specified cache type is used only if the pages that are described by the MDL do not already have a cache type associated with them. However, in nearly all cases, the pages already have an associated cache type, and this cache type is used by the new mapping. An exception to this rule is for pages that are allocated by **MmAllocatePagesForMdl**, which sets the cache type to **MmCached** regardless of the original cache type of the pages.

Only one thread at a time can safely call **MmGetSystemAddressForMdlSafe** for a particular MDL because this routine assumes that the calling thread owns the MDL. However, **MmGetSystemAddressForMdlSafe** can be called more than one time for the same MDL either by making all calls from the same thread or, if the calls are from multiple threads, by explicitly synchronizing the calls.

If a driver must split a request into smaller requests, the driver can allocate additional MDLs, or the driver can use the **IoBuildPartialMdl** routine.

The returned base address has the same offset as the virtual address in the MDL.

Windows 98 does not support **MmGetSystemAddressForMdlSafe**. Use [**MmGetSystemAddressForMdl**](./nf-wdm-mmgetsystemaddressformdl.md) instead.

Because this macro calls [**MmMapLockedPagesSpecifyCache**](./nf-wdm-mmmaplockedpagesspecifycache.md), using it may require linking to NtosKrnl.lib.

## -see-also
