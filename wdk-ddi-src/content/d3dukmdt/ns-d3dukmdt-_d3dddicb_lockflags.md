---
UID: NS:d3dukmdt._D3DDDICB_LOCKFLAGS
title: _D3DDDICB_LOCKFLAGS (d3dukmdt.h)
description: The D3DDDICB_LOCKFLAGS structure identifies how to lock an allocation.
old-location: display\d3dddicb_lockflags.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["D3DDDICB_LOCKFLAGS structure"]
ms.keywords: D3DDDICB_LOCKFLAGS, D3DDDICB_LOCKFLAGS structure [Display Devices], D3D_other_Structs_6238800f-60d9-472d-aa18-10343abbcee7.xml, _D3DDDICB_LOCKFLAGS, d3dukmdt/D3DDDICB_LOCKFLAGS, display.d3dddicb_lockflags
req.header: d3dukmdt.h
req.include-header: D3dukmdt.h
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
req.irql: 
targetos: Windows
req.typenames: D3DDDICB_LOCKFLAGS
f1_keywords:
 - _D3DDDICB_LOCKFLAGS
 - d3dukmdt/_D3DDDICB_LOCKFLAGS
 - D3DDDICB_LOCKFLAGS
 - d3dukmdt/D3DDDICB_LOCKFLAGS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dukmdt.h
api_name:
 - _D3DDDICB_LOCKFLAGS
 - D3DDDICB_LOCKFLAGS
---

# _D3DDDICB_LOCKFLAGS structure


## -description

The D3DDDICB_LOCKFLAGS structure identifies how to lock an allocation.

## -struct-fields

### -field ReadOnly

A UINT value that specifies whether the locked allocation can only be read from. Setting this member is equivalent to setting the first bit of the 32-bit  <b>Value</b> member (0x00000001).

### -field WriteOnly

A UINT value that specifies whether the locked allocation can only be written to. Setting this member is equivalent to setting the second bit of the 32-bit <b>Value</b> member (0x00000002).

### -field DonotWait

A UINT value that specifies whether the video memory manager should wait to lock the allocation. If this member is set, the memory manager fails the call to <a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_lockcb">pfnLockCb</a> with D3DERR_WASSTILLDRAWING if the graphics hardware is using the allocation.

Setting this member is equivalent to setting the third bit of the 32-bit <b>Value</b> member (0x00000004).

### -field IgnoreSync

A UINT value that specifies whether the video memory manager should check whether the graphics hardware is using the allocation. If this member is set, the memory manager should not check.

<b>IgnoreSync</b> can be set only with an allocation that can be placed in an aperture segment. It cannot be set with a swizzled allocation, or with a cached allocation when cache coherency is not supported by the graphics adapter.

Setting this member is equivalent to setting the fourth bit of the 32-bit <b>Value</b> member (0x00000008).

### -field LockEntire

A UINT value that specifies whether the entire allocation region is locked rather than just a subregion.

Setting this member is equivalent to setting the fifth bit of the 32-bit <b>Value</b> member (0x00000010).

### -field DonotEvict

A UINT value that specifies whether the video memory manager should evict the allocation so that the lock can succeed. If this member is set, the memory manager should not evict the allocation. If the allocation must be evicted to handle the lock request, the memory manager fails the call to <a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_lockcb">pfnLockCb</a> with D3DERR_NOTAVAILABLE. Eviction might be necessary when all of the deswizzling apertures are exhausted.

Setting this member is equivalent to setting the sixth bit of the 32-bit <b>Value</b> member (0x00000020).

### -field AcquireAperture

A UINT value that specifies whether the video memory manager should call the display miniport driver's <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_acquireswizzlingrange">DxgkDdiAcquireSwizzlingRange</a> function to set up an unswizzling aperture for the allocation.

An allocation that was locked without setting <b>AcquireAperture</b> cannot be locked again with <b>AcquireAperture</b> set.

<b>AcquireAperture</b> cannot be set if the allocation can be located only in an aperture segment.

Setting this member is equivalent to setting the seventh bit of the 32-bit <b>Value</b> member (0x00000040).

### -field Discard

A UINT value that specifies whether the video memory manager can rename or multiple-buffer the allocation. For more information about renaming allocations, see <a href="/windows-hardware/drivers/display/requesting-to-rename-an-allocation">Requesting to Rename an Allocation</a>.

<b>Discard</b> is ignored for pinned, primary, or shared allocations.

Setting this member is equivalent to setting the eighth bit of the 32-bit <b>Value</b> member (0x00000080).

### -field NoExistingReference

A UINT value that specifies whether the user-mode display driver currently does not have queued in its command buffer a reference to any instance of the allocation that is being locked. The driver should use the <b>NoExistingReference</b> member after the video memory manager fails the lock request by using only the <b>Discard</b> flag and after the driver flushes its current command buffer to the kernel. The driver should use <b>NoExistingReference</b> in combination with <b>Discard</b>.

Setting this member is equivalent to setting the ninth bit of the 32-bit <b>Value</b> member (0x00000100).

### -field UseAlternateVA

A UINT value that specifies whether the display miniport driver can lock an allocation at a different physical address than the allocation's current segment location or with a different memory footprint than was previously allocated. When this flag is specified, the display miniport driver can update the base address and size of the physical address range that the allocation is CPU accessible through (by updating the <b>RangeSize</b> and <b>CPUTranslatedAddress</b> members of the <a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_acquireswizzlingrange">DXGKARG_ACQUIRESWIZZLINGRANGE</a> structure in a call to the <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_acquireswizzlingrange">DxgkDdiAcquireSwizzlingRange</a> function). When this flag is specified, the video memory manager attempts to allocate a new virtual address to handle the lock request rather than use the allocation backing store virtual address. However, if the video memory manager cannot allocate the new virtual address, the lock request fails.

This flag is also used to lock swizzled or tiled allocations that are currently located in a non-AGP aperture segment. In this type of lock, the video memory manager maps the alternate virtual address to a physical address range that can be unswizzled or untiled on the fly and then redirects the memory access to the system memory pages.

The video memory manager creates the alternate virtual address when the allocation is first locked with <b>UseAlternateVA</b> and releases the virtual address in one of the following scenarios:

<ul>
<li>
The allocation is not accessible to the CPU, and the swizzling range is released for reuse by another allocation.

</li>
<li>
The allocation is not accessible to the CPU and is being evicted.

</li>
<li>
The allocation is being destroyed.

</li>
<li>
The allocation is being paged in after it was evicted while under lock.

</li>
</ul>
Be aware that <b>UseAlternateVA</b> can only be used on the primary allocation if the primary allocation was created by specifying the <b>UseAlternateVA</b> bit-field flag in the <b>Flags</b> member of the <a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_allocationinfo">DXGK_ALLOCATIONINFO</a> structure in a call to the display miniport driver's <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_createallocation">DxgkDdiCreateAllocation</a> function. A primary allocation that is created in such a way can only be locked with the <b>UseAlternateVA</b> flag.

<b>UseAlternateVA</b> cannot be used on a shared allocation.

An allocation that was locked with <b>UseAlternateVA</b> set cannot be locked again.

<div class="alert"><b>Note</b>  If the user-mode display driver has set <b>UseAlternateVA</b> in the <b>Flags</b> member of the <b>D3DDDICB_LOCKFLAGS</b> structure during a call to the <a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_lockcb">pfnLockCb</a> function, the display miniport driver should not call the <a href="/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkcb_exclude_adapter_access">DxgkCbExcludeAdapterAccess</a> function.</div>
<div> </div>
Setting this member is equivalent to setting the tenth bit of the 32-bit <b>Value</b> member (0x00000200).

### -field IgnoreReadSync

A UINT value that specifies whether the video memory manager should wait only for pending Graphics Processing Unit (GPU) write operations to the allocation to complete. If this member is set, the memory manager is not required to wait for GPU read operations to complete. That is, as soon as the last GPU write operation completes, the lock can return even though the GPU might still be reading from the allocation.

<b>IgnoreReadSync</b> can be set only with an allocation that can be placed in an aperture segment. It cannot be set with a swizzled allocation, or with a cached allocation when cache coherency is not supported by the graphics adapter.

Setting this member is equivalent to setting the eleventh bit of the 32-bit <b>Value</b> member (0x00000400).

### -field Reserved

This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting the remaining 21 bits (0xFFFFF800) of the 32-bit <b>Value</b> member to zeros.

### -field Value

A member in the union that is contained in D3DDDICB_LOCKFLAGS that can hold one 32-bit value that identifies how to lock an allocation.

## -remarks

When you use a D3DDDICB_LOCKFLAGS structure to specify how to lock an allocation, you must adhere to the following rules:

<ul>
<li>
Simultaneously specifying the <b>ReadOnly</b> and <b>WriteOnly</b> members is invalid.

</li>
<li>
The <b>IgnoreSync</b> member has no effect if specified with the <b>Discard</b> member.

</li>
<li>
The <b>DonotWait</b> member has no effect if specified with the <b>Discard</b> member.

</li>
<li>
Simultaneously specifying the <b>IgnoreSync</b> and <b>AcquireAperture</b> members is invalid.

</li>
<li>
Because specifying the <b>UseAlternateVA</b> member indicates that an aperture is acquired, the <b>AcquireAperture</b> member must also be set.

</li>
<li>
Retired or offered allocations cannot be locked. See also <a href="/windows-hardware/drivers/display/requesting-to-rename-an-allocation">Requesting to Rename an Allocation</a>.

</li>
<li>
An allocation can be locked only if it was created with the <b>CpuVisible</b>  member set in the <a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_allocationinfoflags">DXGK_ALLOCATIONINFOFLAGS</a> structure.

</li>
<li>
Only the owner (creator) of a shared allocation can lock it, unless it's a GDI non-managed primary allocation.

</li>
<li>
An allocation that is locked with a swizzled range must be unlocked before it can be locked again.

</li>
</ul>

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddicb_lock">D3DDDICB_LOCK</a>



<a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_allocationinfoflags">DXGK_ALLOCATIONINFOFLAGS</a>



<a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_acquireswizzlingrange">DxgkDdiAcquireSwizzlingRange</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_lockcb">pfnLockCb</a>

