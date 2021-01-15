---
UID: NS:d3dkmddi._DXGK_ALLOCATIONINFOFLAGS_WDDM2_0
title: _DXGK_ALLOCATIONINFOFLAGS_WDDM2_0 (d3dkmddi.h)
description: The DXGK_ALLOCATIONINFOFLAGS_WDDM2_0 structure identifies properties for an allocation. The display miniport driver specifies these flags for the video memory manager.
ms.date: 08/05/2020
keywords: ["_DXGK_ALLOCATIONINFOFLAGS_WDDM2_0 structure"]
ms.keywords: DXGK_ALLOCATIONINFOFLAGS_WDDM2_0, DXGK_ALLOCATIONINFOFLAGS_WDDM2_0 structure [Display Devices], d3dkmddi/DXGK_ALLOCATIONINFOFLAGS, display.dxgk_allocationinfoflags
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Available starting in Windows 10.
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
targetos: Windows
tech.root: display
req.typenames: DXGK_ALLOCATIONINFOFLAGS_WDDM2_0
f1_keywords:
 - _DXGK_ALLOCATIONINFOFLAGS_WDDM2_0
 - d3dkmddi/_DXGK_ALLOCATIONINFOFLAGS_WDDM2_0
 - DXGK_ALLOCATIONINFOFLAGS_WDDM2_0
 - d3dkmddi/DXGK_ALLOCATIONINFOFLAGS_WDDM2_0
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGK_ALLOCATIONINFOFLAGS_WDDM2_0
 - DXGK_ALLOCATIONINFOFLAGS_WDDM2_0
---

# _DXGK_ALLOCATIONINFOFLAGS_WDDM2_0 structure


## -description

The DXGK_ALLOCATIONINFOFLAGS_WDDM2_0 structure identifies properties for an allocation.

## -struct-fields

### -field CpuVisible

[out] A UINT value that specifies whether the allocation is directly accessible by the CPU. The display miniport driver must set this flag for the user-mode display driver to successfully call the [**pfnLockCb**](../d3dumddi/nc-d3dumddi-pfnd3dddi_lockcb.md) function on the allocation. If this flag is not set on the allocation, **pfnLockCb** returns an error.

Note that only the process that created a shared allocation can lock that allocation.

Setting this member is equivalent to setting the first bit of the 32-bit **Value** member (0x00000001).

### -field PermanentSysMem

[out] A UINT value that specifies whether a copy of the allocation should be kept in system memory even when the content is located in a memory segment. By default, a surface system memory backing store is lost when transferring an allocation to a memory segment. When the **PermanentSysMem** flag is specified and the allocation is evicted from a memory segment, the content of the allocation is discarded and not paged out if the allocation is not dirty (that is, the allocation was not the target of a write operation since it was paged in).

A call to [**pfnLockCb**](../d3dumddi/nc-d3dumddi-pfnd3dddi_lockcb.md) on the allocation always returns the system memory backing store for the allocation. If the allocation is located in a memory segment when the user-mode display driver calls [**pfnUnlockCb**](../d3dumddi/nc-d3dumddi-pfnd3dddi_unlockcb.md), the memory segment resource for the allocation is updated with the new content. This update appears, to the display miniport driver, as a regular paging operation through the [**DxgkDdiBuildPagingBuffer**](nc-d3dkmddi-dxgkddi_buildpagingbuffer.md) function. Note that if the display miniport driver requires a minimal region size or alignment for a paging operation, this requirement should be reflected in the region that is being locked. When the driver sets **PermanentSysMem**, the driver must also set the **CpuVisible** member. The driver must not set **PermanentSysMem** on the primary surface.

Setting this member is equivalent to setting the second bit of the 32-bit **Value** member (0x00000002).

### -field Cached

[out] A UINT value that specifies whether the allocation backing store should be allocated as cached memory; by default, the allocation backing store is stored as write-combined memory. When a cached-memory allocation is used in a segment that is not cache coherent (for example, a memory segment or AGP segment), the video memory manager ensures coherency for the content of the allocation by flushing it from the processor's cache at the appropriate time.

When the driver sets **Cached** and also sets the **ExistingSysMem** or **ExistingKernelSysMem** member, the driver indicates to the video memory manager that the existing memory was mapped cacheable. If the existing memory was mapped cacheable but the driver fails to set the **Cached** member, the video memory manager cannot ensure data coherency, and corruption occurs. The driver should set the **Cached** member for an allocation that is to be read by the application or the user-mode display driver. The driver should never set the **Cached** member for a write-only allocation.

When the driver sets this member, the driver must also set the **CpuVisible** member. The driver must not set **Cached** on the primary surface.

Setting this member is equivalent to setting the third bit of the 32-bit **Value** member (0x00000004).

### -field Protected

[out] A UINT value that specifies whether the allocation backing store should be allocated in kernel memory instead of user address space to protect the allocation from potential direct CPU access by an application. The driver cannot set this member in combination with the **PermanentSysMem**, **ExistingSysMem**, or **ExistingKernelSysMem** member. The driver must not set **Protected** on the primary surface.

Setting this member is equivalent to setting the fourth bit of the 32-bit **Value** member (0x00000008).

### -field ExistingSysMem

[out] A UINT value that specifies whether the video memory manager should use the existing system memory range as a backing store for the allocation. The system memory range must be a valid user-mode address for the current process for the size of the allocation. The system memory range must also be page aligned and must be a page multiple in size.

If the system memory range is a cacheable virtual address, the driver should set the **Cached** member to inform the video memory manager to ensure cache coherency on the allocation. If the **Cached** member is not specified, the video memory manager determines that the system memory range is uncacheable, write combined, or cacheable; however, in this situation, the driver either ensures cache coherency or determines that cache coherency is not an issue for the specified usage.

Note that this type of allocation implicitly has the same lock semantics as an allocation in which the **PermanentSysMem** member is set.

The driver cannot set **ExistingSysMem** in combination with the **PermanentSysMem**, **Protected**, or **ExistingKernelSysMem** member. The driver must not set **ExistingSysMem** on the primary surface.

Setting this member is equivalent to setting the fifth bit of the 32-bit **Value** member (0x00000010).

### -field ExistingKernelSysMem

[out] A UINT value that specifies whether the video memory manager should use the existing system memory range as a backing store for the allocation. The system memory range must be a valid kernel-mode address that is aligned on a page and a page multiple in size.

If the system memory range is a cacheable virtual address, the driver should set the **Cached** member to inform the video memory manager to ensure cache coherency on the allocation. If the **Cached** member is not specified, the video memory manager determines that the system memory range is uncacheable, write combined, or cacheable; however, in this situation, the driver either ensures cache coherency or determines that cache coherency is not an issue for the specified usage.

Note that this type of allocation implicitly has the same lock semantics as an allocation in which the **PermanentSysMem** member is set.

The driver cannot set **ExistingKernelSysMem** in combination with the **PermanentSysMem**, **Protected**, or **ExistingSysMem** member. The driver must not set **ExistingKernelSysMem** on the primary surface.

Setting this member is equivalent to setting the sixth bit of the 32-bit **Value** member (0x00000020).

### -field FromEndOfSegment

[out] A UINT value that specifies whether the allocation should be allocated from the end of a segment during paging. The video memory manager scans a segment address space and looks for room for the allocation from the end of the segment instead of scanning from the start of the segment (which is the default behavior). However, the hinted and preferred segment information takes precedent over this flag.

Setting this member is equivalent to setting the seventh bit of the 32-bit **Value** member (0x00000040).

### -field DisableLargePageMapping

[out] A UINT value that specifies whether large page mapping for the allocation should be disabled. Support for Large Pages for drivers was added starting in WDDM2.1. The large pages are used when translating virtual addresses, where the lowest level page table is replaced by a large page that has equal coverage of the level 0 page table. This flag disables that, and uses a page table for the address translation.

Setting this member is equivalent to setting the eighth bit of the 32-bit **Value** member (0x00000080).

### -field Overlay

[out] A UINT value that specifies whether the allocation is for an overlay operation. Overlay allocations are pinned in memory, and the video memory manager cannot evict them unless the Timeout Detection and Recovery (TDR) process, Plug and Play (PnP) stop, or [level three synchronization](/windows-hardware/drivers/display/threading-and-synchronization-third-level) occurs. Note that before level three synchronization occurs, overlays are typically destroyed. By default, overlay allocations are limited and cannot occupy more than the last 20 percent of a segment. If an overlay allocation is allocated in an aperture segment, the display miniport driver should limit the size of any other allocation that uses that aperture segment as an eviction segment to 80 percent of the segment size. The display miniport driver indicates that an allocation can use a segment for eviction by specifying the appropriate bit for the segment in the **EvictionSegmentSet** member of the [**DXGK_ALLOCATIONINFO**](ns-d3dkmddi-_dxgk_allocationinfo.md) structure for the allocation. If the display miniport driver does not limit the size of another allocation, the video memory manager cannot evict that allocation through the segment because the pinned allocation (that is, the overlay allocation) occupies the area that is required for eviction. In this case, the content of the other allocation that is being evicted is lost, and the application that owns the lost allocation can no longer render with that allocation.

Setting this member is equivalent to setting the ninth bit of the 32-bit **Value** member (0x00000100).

### -field Capture

[out] A UINT value that specifies whether the allocation is used for a capture operation. Capture allocations are pinned in memory similarly to overlay allocations. Therefore, the issues that apply to overlay allocations also apply to capture allocations. For more information about these issues, see the description of the **Overlay** flag. Note that before [level three synchronization](/windows-hardware/drivers/display/threading-and-synchronization-third-level) occurs, captures are typically stopped.

Setting this member is equivalent to setting the tenth bit of the 32-bit **Value** member (0x00000200).

### -field CreateInVpr

[out] A UINT value that specifies whether the allocation should be created in the video protected range. This member is used for hardware digital rights management (DRM) in WDDM versions >= WDDM 2.1.

Setting this member is equivalent to setting the eleventh bit of the 32-bit **Value** member (0x00000400).

### -field Reserved00

[in] For WDDM versions earlier than WDDM 2.1, this member is reserved and should be set to zero.

Setting this member is equivalent to setting the eleventh bit of the 32-bit **Value** member (0x00000400).

### -field DXGK_ALLOC_RESERVED17

[in] This member is reserved and should be set to zero.

Setting this member is equivalent to setting the twelfth bit of the 32-bit **Value** member (0x00000800).

### -field Reserved02

[in] This member is reserved and should be set to zero.

Setting this member is equivalent to setting the thirteenth bit of the 32-bit **Value** member (0x00001000).

### -field Reserved03

[in] This member is reserved and should be set to zero.

Setting this member is equivalent to setting the fourteenth bit of the 32-bit **Value** member (0x00002000).

### -field HistoryBuffer

[out] A UINT value that specifies whether the user-mode display driver allocates a history buffer. The display miniport driver must set this flag to indicate that the user-mode driver can manage the creation and destruction of history buffers.

When the display miniport driver sets **HistoryBuffer**, it must also set the **CpuVisible** flag. If the driver supports cache-coherent aperture segments, it must also set  **Cached**, and all other members must be set to zero.

Setting this member is equivalent to setting the fifteenth bit of the 32-bit **Value** member (0x00004000).

### -field AccessedPhysically

The kernel mode driver sets the flag on allocations, which are accessed by their physical address. Such allocation will be allocated contiguously from GPU memory segments. The allocations will not be contiguous when allocated from system memory.

Setting this member is equivalent to setting the sixteenth bit of the 32-bit **Value** member (0x00008000).

### -field ExplicitResidencyNotification

When this flags is specified, the driver receives a **NotifyResidency** paging buffer operation when the allocation residency is changed (evicted, commited). The flag can only be set when the **AccessedPhysically** flag is set.

Setting this member is equivalent to setting the seventeenth bit of the 32-bit **Value** member (0x00010000).

### -field HardwareProtected

When this member is set, the allocation will hold content used for hardware DRM.

### -field CpuVisibleOnDemand

When this member is set, the video memory manager will try to allocate the virtual address for the allocation when it is mapped/locked. This will result in the allocation not having a permanent virtual address, which reduces the amount of virtual address space used. It behaves similarly to the **CpuVisible** flag in that it’s an allocation directly accessible by the CPU, but it just gets the virtual address for it “on demand” instead of being permanently assigned.

### -field Reserved

[in] This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting 4 bits, from the sixteenth bit to the nineteenth bit (0x00078000), of the 32-bit **Value** member to zeros.

### -field DXGK_ALLOC_RESERVED16

[in] This member is reserved and should be set to zero.

### -field DXGK_ALLOC_RESERVED15

[in] This member is reserved and should be set to zero.

### -field DXGK_ALLOC_RESERVED14

[in] This member is reserved and should be set to zero.

### -field DXGK_ALLOC_RESERVED13

[in] This member is reserved and should be set to zero.

### -field DXGK_ALLOC_RESERVED12

[in] This member is reserved and should be set to zero.

### -field DXGK_ALLOC_RESERVED11

[in] This member is reserved and should be set to zero.

### -field DXGK_ALLOC_RESERVED10

[in] This member is reserved and should be set to zero.

### -field DXGK_ALLOC_RESERVED9

[in] This member is reserved and should be set to zero.

### -field DXGK_ALLOC_RESERVED4

[in] This member is reserved and should be set to zero.

### -field DXGK_ALLOC_RESERVED3

[in] This member is reserved and should be set to zero.

### -field DXGK_ALLOC_RESERVED2

[in] This member is reserved and should be set to zero.

### -field DXGK_ALLOC_RESERVED1

[in] This member is reserved and should be set to zero.

### -field DXGK_ALLOC_RESERVED0

[in] This member is reserved and should be set to zero.

### -field Value

[out] A member in the union that **DXGK_ALLOCATIONINFOFLAGS_WDDM2_0** contains that can hold a 32-bit value that identifies properties of the allocation.

## -remarks

A display miniport driver that targets any WDDM version >= WDDM 2.0 uses this structure to specify these flags for the video memory manager. Drivers that target WDDM versions earlier than WDDM 2.0 should use [**DXGK_ALLOCATIONINFOFLAGS**]( ns-d3dkmddi-_dxgk_allocationinfoflags.md).

You can specify properties of an allocation by setting bits in the 32-bit **Value** member or by setting individual members of the structure in the union that the **DXGK_ALLOCATIONINFOFLAGS** structure contains.

## -see-also

[**DXGK_ALLOCATIONINFO**](ns-d3dkmddi-_dxgk_allocationinfo.md)

[**DXGK_ALLOCATIONINFOFLAGS**]( ns-d3dkmddi-_dxgk_allocationinfoflags.md)

[**DxgkDdiBuildPagingBuffer**](nc-d3dkmddi-dxgkddi_buildpagingbuffer.md)

[**pfnLockCb**](../d3dumddi/nc-d3dumddi-pfnd3dddi_lockcb.md)

[**pfnUnlockCb**](../d3dumddi/nc-d3dumddi-pfnd3dddi_unlockcb.md)

