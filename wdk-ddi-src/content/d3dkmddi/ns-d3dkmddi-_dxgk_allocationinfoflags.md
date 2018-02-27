---
UID: NS:d3dkmddi._DXGK_ALLOCATIONINFOFLAGS
title: "_DXGK_ALLOCATIONINFOFLAGS"
author: windows-driver-content
description: The DXGK_ALLOCATIONINFOFLAGS structure identifies properties for an allocation. The display miniport driver specifies these flags for the video memory manager.
old-location: display\dxgk_allocationinfoflags.htm
old-project: display
ms.assetid: 04bd00c3-83a8-44bb-9493-cf7f43f10602
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: DXGK_ALLOCATIONINFOFLAGS, DXGK_ALLOCATIONINFOFLAGS structure [Display Devices], DmStructs_4e6e499c-8427-4c0f-977d-92f648ab027e.xml, _DXGK_ALLOCATIONINFOFLAGS, d3dkmddi/DXGK_ALLOCATIONINFOFLAGS, display.dxgk_allocationinfoflags
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dkmddi.h
apiname:
-	DXGK_ALLOCATIONINFOFLAGS
product: Windows
targetos: Windows
req.typenames: DXGK_ALLOCATIONINFOFLAGS
---

# _DXGK_ALLOCATIONINFOFLAGS structure


## -description


The DXGK_ALLOCATIONINFOFLAGS structure identifies properties for an allocation. The display miniport driver specifies these flags for the video memory manager.


## -syntax


````
typedef struct _DXGK_ALLOCATIONINFOFLAGS {
  union {
    struct {
      UINT CpuVisible  :1;
      UINT PermanentSysMem  :1;
      UINT Cached  :1;
      UINT Protected  :1;
      UINT ExistingSysMem  :1;
      UINT ExistingKernelSysMem  :1;
      UINT FromEndOfSegment  :1;
      UINT Swizzled  :1;
      UINT Overlay  :1;
      UINT Capture  :1;
      UINT UseAlternateVA  :1;
      UINT SynchronousPaging  :1;
      UINT LinkMirrored  :1;
      UINT LinkInstanced  :1;
      UINT HistoryBuffer  :1;
#if (DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WDDM2_0)
      UINT AccessedPhysically  :1;
      UINT ExplicitResidencyNotification  :1;
      UINT Reserved  :2;
#else 
      UINT Reserved  :4;
#endif 
      UINT DXGK_ALLOC_RESERVED16  :1;
      UINT DXGK_ALLOC_RESERVED15  :1;
      UINT DXGK_ALLOC_RESERVED14  :1;
      UINT DXGK_ALLOC_RESERVED13  :1;
      UINT DXGK_ALLOC_RESERVED12  :1;
      UINT DXGK_ALLOC_RESERVED11  :1;
      UINT DXGK_ALLOC_RESERVED10  :1;
      UINT DXGK_ALLOC_RESERVED9  :1;
      UINT DXGK_ALLOC_RESERVED4  :1;
      UINT DXGK_ALLOC_RESERVED3  :1;
      UINT DXGK_ALLOC_RESERVED2  :1;
      UINT DXGK_ALLOC_RESERVED1  :1;
      UINT DXGK_ALLOC_RESERVED0  :1;
    };
    UINT Value;
  };
} DXGK_ALLOCATIONINFOFLAGS;
````


## -struct-fields




### -field CpuVisible

[out] A UINT value that specifies whether the allocation is directly accessible by the CPU. The display miniport driver must set this flag for the user-mode display driver to successfully call the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_lockcb.md">pfnLockCb</a> function on the allocation. If this flag is not set on the allocation, <b>pfnLockCb</b> returns an error.

Note that only the process that created a shared allocation can lock that allocation.

Setting this member is equivalent to setting the first bit of the 32-bit <b>Value</b> member (0x00000001).


### -field PermanentSysMem

[out] A UINT value that specifies whether a copy of the allocation should be kept in system memory even when the content is located in a memory segment. By default, a surface system memory backing store is lost when transferring an allocation to a memory segment. When the <b>PermanentSysMem</b> flag is specified and the allocation is evicted from a memory segment, the content of the allocation is discarded and not paged out if the allocation is not dirty (that is, the allocation was not the target of a write operation since it was paged in). 

A call to <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_lockcb.md">pfnLockCb</a> on the allocation always returns the system memory backing store for the allocation. If the allocation is located in a memory segment when the user-mode display driver calls <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_unlockcb.md">pfnUnlockCb</a>, the memory segment resource for the allocation is updated with the new content. This update appears, to the display miniport driver, as a regular paging operation through the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_buildpagingbuffer.md">DxgkDdiBuildPagingBuffer</a> function. Note that if the display miniport driver requires a minimal region size or alignment for a paging operation, this requirement should be reflected in the region that is being locked. When the driver sets <b>PermanentSysMem</b>, the driver must also set the <b>CpuVisible</b> member. The driver must not set <b>PermanentSysMem</b> on the primary surface.

Setting this member is equivalent to setting the second bit of the 32-bit <b>Value</b> member (0x00000002).


### -field Cached

[out] A UINT value that specifies whether the allocation backing store should be allocated as cached memory; by default, the allocation backing store is stored as write-combined memory. When a cached-memory allocation is used in a segment that is not cache coherent (for example, a memory segment or AGP segment), the video memory manager ensures coherency for the content of the allocation by flushing it from the processor's cache at the appropriate time. 

When the driver sets <b>Cached</b> and also sets the <b>ExistingSysMem</b> or <b>ExistingKernelSysMem</b> member, the driver indicates to the video memory manager that the existing memory was mapped cacheable. If the existing memory was mapped cacheable but the driver fails to set the <b>Cached</b> member, the video memory manager cannot ensure data coherency, and corruption occurs. The driver should set the <b>Cached</b> member for an allocation that is to be read by the application or the user-mode display driver. The driver should never set the <b>Cached</b> member for a write-only allocation. 

When the driver sets this member, the driver must also set the <b>CpuVisible</b> member. The driver must not set <b>Cached</b> on the primary surface.

Setting this member is equivalent to setting the third bit of the 32-bit <b>Value</b> member (0x00000004).


### -field Protected

[out] A UINT value that specifies whether the allocation backing store should be allocated in kernel memory instead of user address space to protect the allocation from potential direct CPU access by an application. The driver cannot set this member in combination with the <b>PermanentSysMem</b>, <b>ExistingSysMem</b>, or <b>ExistingKernelSysMem</b> member. The driver must not set <b>Protected</b> on the primary surface.

Setting this member is equivalent to setting the fourth bit of the 32-bit <b>Value</b> member (0x00000008).


### -field ExistingSysMem

[out] A UINT value that specifies whether the video memory manager should use the existing system memory range as a backing store for the allocation. The system memory range must be a valid user-mode address for the current process for the size of the allocation. The system memory range must also be page aligned and must be a page multiple in size. 

If the system memory range is a cacheable virtual address, the driver should set the <b>Cached</b> member to inform the video memory manager to ensure cache coherency on the allocation. If the <b>Cached</b> member is not specified, the video memory manager determines that the system memory range is uncacheable, write combined, or cacheable; however, in this situation, the driver either ensures cache coherency or determines that cache coherency is not an issue for the specified usage. 

Note that this type of allocation implicitly has the same lock semantics as an allocation in which the <b>PermanentSysMem</b> member is set. 

The driver cannot set <b>ExistingSysMem</b> in combination with the <b>PermanentSysMem</b>, <b>Protected</b>, or <b>ExistingKernelSysMem</b> member. The driver must not set <b>ExistingSysMem</b> on the primary surface.

Setting this member is equivalent to setting the fifth bit of the 32-bit <b>Value</b> member (0x00000010).


### -field ExistingKernelSysMem

[out] A UINT value that specifies whether the video memory manager should use the existing system memory range as a backing store for the allocation. The system memory range must be a valid kernel-mode address that is aligned on a page and a page multiple in size. 

If the system memory range is a cacheable virtual address, the driver should set the <b>Cached</b> member to inform the video memory manager to ensure cache coherency on the allocation. If the <b>Cached</b> member is not specified, the video memory manager determines that the system memory range is uncacheable, write combined, or cacheable; however, in this situation, the driver either ensures cache coherency or determines that cache coherency is not an issue for the specified usage. 

Note that this type of allocation implicitly has the same lock semantics as an allocation in which the <b>PermanentSysMem</b> member is set. 

The driver cannot set <b>ExistingKernelSysMem</b> in combination with the <b>PermanentSysMem</b>, <b>Protected</b>, or <b>ExistingSysMem</b> member. The driver must not set <b>ExistingKernelSysMem</b> on the primary surface.

Setting this member is equivalent to setting the sixth bit of the 32-bit <b>Value</b> member (0x00000020).


### -field FromEndOfSegment

[out] A UINT value that specifies whether the allocation should be allocated from the end of a segment during paging. The video memory manager scans a segment address space and looks for room for the allocation from the end of the segment instead of scanning from the start of the segment (which is the default behavior). However, the hinted and preferred segment information takes precedent over this flag.

Setting this member is equivalent to setting the seventh bit of the 32-bit <b>Value</b> member (0x00000040).


### -field Swizzled

[out] A UINT value that specifies whether the allocation is swizzled and requires special support by the video memory manager to lock the allocation. For more information about swizzled allocations, see <a href="https://msdn.microsoft.com/c9be52d9-36b2-4a0f-9629-01b31293af38">Locking Swizzled Allocations</a>.

Setting this member is equivalent to setting the eighth bit of the 32-bit <b>Value</b> member (0x00000080).


### -field Overlay

[out] A UINT value that specifies whether the allocation is for an overlay operation. Overlay allocations are pinned in memory, and the video memory manager cannot evict them unless the Timeout Detection and Recovery (TDR) process, Plug and Play (PnP) stop, or <a href="https://msdn.microsoft.com/780d37d9-40c6-4737-9042-473810868227">level three synchronization</a> occurs. Note that before level three synchronization occurs, overlays are typically destroyed. By default, overlay allocations are limited and cannot occupy more than the last 20 percent of a segment. If an overlay allocation is allocated in an aperture segment, the display miniport driver should limit the size of any other allocation that uses that aperture segment as an eviction segment to 80 percent of the segment size. The display miniport driver indicates that an allocation can use a segment for eviction by specifying the appropriate bit for the segment in the <b>EvictionSegmentSet</b> member of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_allocationinfo.md">DXGK_ALLOCATIONINFO</a> structure for the allocation. If the display miniport driver does not limit the size of another allocation, the video memory manager cannot evict that allocation through the segment because the pinned allocation (that is, the overlay allocation) occupies the area that is required for eviction. In this case, the content of the other allocation that is being evicted is lost, and the application that owns the lost allocation can no longer render with that allocation. 

Setting this member is equivalent to setting the ninth bit of the 32-bit <b>Value</b> member (0x00000100).


### -field Capture

[out] A UINT value that specifies whether the allocation is used for a capture operation. Capture allocations are pinned in memory similarly to overlay allocations. Therefore, the issues that apply to overlay allocations also apply to capture allocations. For more information about these issues, see the description of the <b>Overlay</b> flag. Note that before <a href="https://msdn.microsoft.com/780d37d9-40c6-4737-9042-473810868227">level three synchronization</a> occurs, captures are typically stopped. 

Setting this member is equivalent to setting the tenth bit of the 32-bit <b>Value</b> member (0x00000200).


### -field UseAlternateVA

[out] A UINT value that specifies whether the primary allocation can be locked. <b>UseAlternateVA</b> is valid only for the primary allocation. If <b>UseAlternateVA</b> is specified for any other allocation, the allocation is not created. When a primary allocation is created by using <b>UseAlternateVA</b>, a swizzling range for the primary allocation is set up when the allocation is created. 

Setting this member is equivalent to setting the eleventh bit of the 32-bit <b>Value</b> member (0x00000400).


### -field SynchronousPaging

[out] A UINT value that specifies whether the allocation should be paged in synchronously. If the display miniport driver sets this bit for an allocation, the video memory manager will wait until the allocation is no longer busy (that is, the video memory manager will wait until the graphics processing unit (GPU) reports all of the fences that reference the allocation) before the video memory manager submits a paging buffer that references the allocation. 

Similarly, the video memory manager will wait for a paging operation on a synchronous allocation to complete before the video memory manager allows the driver to submit a non-paging direct memory access (DMA) buffer.

Setting this member is equivalent to setting the twelfth bit of the 32-bit <b>Value</b> member (0x00000800).


### -field LinkMirrored

[out] A UINT value that specifies whether a single instance of an allocation should be replicated across all physical adapters in a logical adapter (that is, a link). The video memory manager calls the driver to page in and evict the allocation on all physical adapters with a single shared backing store in system memory.

Setting this member is equivalent to setting the thirteenth bit of the 32-bit <b>Value</b> member (0x00001000).


### -field LinkInstanced

[out] A UINT value that specifies whether different instances of an allocation will be paged in and evicted from all physical adapters in a logical adapter (that is, a link). One system memory backing store exists per physical adapter in a logical adapter.

Setting this member is equivalent to setting the fourteenth bit of the 32-bit <b>Value</b> member (0x00002000).


### -field HistoryBuffer

[out] A UINT value that specifies whether the  user-mode display driver allocates a history buffer. The display miniport driver must set this flag to indicate that the user-mode driver can manage the creation and destruction of history buffers.

When the display miniport driver sets <b>HistoryBuffer</b>, it must also set the <b>CpuVisible</b> flag. If the driver supports cache-coherent aperture segments, it must also set  <b>Cached</b>, and all other members must be set to zero.

Setting this member is equivalent to setting the fifteenth bit of the 32-bit <b>Value</b> member (0x00004000).

Supported starting with Windows 8.1.


### -field AccessedPhysically

The kernel mode driver sets the flag on allocations, which are accessed by their physical address. Such allocation will be allocated contiguously from GPU memory segments. The allocations will not be contiguous when allocated from system memory.

Setting this member is equivalent to setting the sixteenth bit of the 32-bit <b>Value</b> member (0x00008000).

Supported starting with Windows 10.


### -field ExplicitResidencyNotification

When this flags is specified, the driver receives a <b>NotifyResidency</b> paging buffer operation when the allocation residency is changed (evicted, commited). The flag can only be set when the <b>AccessedPhysically</b> flag is set.

Setting this member is equivalent to setting the seventeenth bit of the 32-bit <b>Value</b> member (0x00010000).

Supported starting with Windows 10.


### -field HardwareProtected

 


### -field CpuVisibleOnDemand

 


### -field Reserved

[in] This member is reserved and should be set to zero. 

[in] This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting 4 bits, from the sixteenth bit to the nineteenth bit (0x00078000), of the 32-bit <b>Value</b> member to zeros.


### -field DXGK_ALLOC_RESERVED16

[in] This member is reserved and should be set to zero.

Supported starting with Windows 8.


### -field DXGK_ALLOC_RESERVED15

[in] This member is reserved and should be set to zero.

Supported starting with Windows 8.


### -field DXGK_ALLOC_RESERVED14

[in] This member is reserved and should be set to zero.

Supported starting with Windows 8.


### -field DXGK_ALLOC_RESERVED13

[in] This member is reserved and should be set to zero.

Supported starting with Windows 8.


### -field DXGK_ALLOC_RESERVED12

[in] This member is reserved and should be set to zero.

Supported starting with Windows 8.


### -field DXGK_ALLOC_RESERVED11

[in] This member is reserved and should be set to zero.

Supported starting with Windows 8.


### -field DXGK_ALLOC_RESERVED10

[in] This member is reserved and should be set to zero.

Supported starting with Windows 8.


### -field DXGK_ALLOC_RESERVED9

[in] This member is reserved and should be set to zero.

Supported starting with Windows 8.


### -field DXGK_ALLOC_RESERVED4

[in] This member is reserved and should be set to zero.

Supported starting with Windows 8.


### -field DXGK_ALLOC_RESERVED3

[in] This member is reserved and should be set to zero.

Supported starting with Windows 8.


### -field DXGK_ALLOC_RESERVED2

[in] This member is reserved and should be set to zero.

Supported starting with Windows 8.


### -field DXGK_ALLOC_RESERVED1

[in] This member is reserved and should be set to zero.

Supported starting with Windows 8.


### -field DXGK_ALLOC_RESERVED0

[in] This member is reserved and should be set to zero.

Supported starting with Windows 8.


#### - Value

[out] A member in the union that <b>DXGK_ALLOCATIONINFOFLAGS</b> contains that can hold a 32-bit value that identifies properties of the allocation. 


## -remarks



You can specify properties of an allocation by setting bits in the 32-bit <b>Value</b> member or by setting individual members of the structure in the union that the <b>DXGK_ALLOCATIONINFOFLAGS</b> structure contains.




## -see-also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_unlockcb.md">pfnUnlockCb</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_buildpagingbuffer.md">DxgkDdiBuildPagingBuffer</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_allocationinfo.md">DXGK_ALLOCATIONINFO</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_lockcb.md">pfnLockCb</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_ALLOCATIONINFOFLAGS structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

