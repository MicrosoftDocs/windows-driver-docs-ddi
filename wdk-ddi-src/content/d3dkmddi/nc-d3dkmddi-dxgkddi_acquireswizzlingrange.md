---
UID: NC:d3dkmddi.DXGKDDI_ACQUIRESWIZZLINGRANGE
title: DXGKDDI_ACQUIRESWIZZLINGRANGE
author: windows-driver-content
description: The DxgkDdiAcquireSwizzlingRange function makes an allocation accessible through the central processing unit (CPU) aperture for the given segment.
old-location: display\dxgkddiacquireswizzlingrange.htm
old-project: display
ms.assetid: f861e055-70db-4e0a-9c62-87e2d41f92ae
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _DD_MULTISAMPLEQUALITYLEVELSDATA, DD_MULTISAMPLEQUALITYLEVELSDATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DxgkDdiAcquireSwizzlingRange
req.alt-loc: d3dkmddi.h
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
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---

# DXGKDDI_ACQUIRESWIZZLINGRANGE callback



## -description
The <i>DxgkDdiAcquireSwizzlingRange</i> function makes an allocation accessible through the central processing unit (CPU) aperture for the given segment.



## -prototype

````
DXGKDDI_ACQUIRESWIZZLINGRANGE DxgkDdiAcquireSwizzlingRange;

NTSTATUS APIENTRY DxgkDdiAcquireSwizzlingRange(
  _In_    const HANDLE                        hAdapter,
  _Inout_       DXGKARG_ACQUIRESWIZZLINGRANGE *pAcquireSwizzlingRange
)
{ ... }
````


## -parameters

### -param hAdapter [in]

[in] A handle to a context block that is associated with a display adapter. The display miniport driver previously provided this handle to the Microsoft DirectX graphics kernel subsystem in the <i>MiniportDeviceContext</i> output parameter of the <a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a> function.


### -param pAcquireSwizzlingRange [in, out]

[in/out] A pointer to a <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_acquireswizzlingrange.md">DXGKARG_ACQUIRESWIZZLINGRANGE</a> structure that contains information for making an allocation accessible through the CPU aperture.


## -returns
<i>DxgkDdiAcquireSwizzlingRange</i> returns one of the following values:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl><i>DxgkDdiAcquireSwizzlingRange</i> successfully made the allocation accessible.
<dl>
<dt><b>STATUS_GRAPHICS_UNSWIZZLING_APERTURE_UNSUPPORTED</b></dt>
</dl><i>DxgkDdiAcquireSwizzlingRange</i> could not program the swizzling range for the allocation. The video memory manager fails to acquire the swizzling range without making futher attempts.
<dl>
<dt><b>STATUS_GRAPHICS_UNSWIZZLING_APERTURE_UNAVAILABLE</b></dt>
</dl><i>DxgkDdiAcquireSwizzlingRange</i> could not program the swizzling range for the allocation because another swizzling range is currently using the graphics processing unit (GPU) resources that are required. The video memory manager attempts to release a range that is currently in use and then attempts to set up the swizzling range again.

 


## -remarks
The <i>DxgkDdiAcquireSwizzlingRange</i> function is called after the user-mode display driver requests a virtual address that references the bits of an allocation (that is, after the user-mode display driver calls the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_lockcb.md">pfnLockCb</a> function with the <b>AcquireAperture</b> bit-field flag set in the <b>Flags</b> member of the <a href="..\d3dumddi\ns-d3dumddi-_d3dddicb_lock.md">D3DDDICB_LOCK</a> structure and while the allocation is currently located in a CPU-accessible memory segment). If the <b>AcquireAperture</b> bit-field flag is not set in the call to <b>pfnLockCb</b>, <i>DxgkDdiAcquireSwizzlingRange</i> is not called, and the allocation must be in a format that the user-mode display driver or an application can process. 

When <i>DxgkDdiAcquireSwizzlingRange</i> is called, the display miniport driver must make the specified allocation (that is, the <b>hAllocation</b> member of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_acquireswizzlingrange.md">DXGKARG_ACQUIRESWIZZLINGRANGE</a> structure that the <i>pAcquireSwizzlingRange</i> parameter points to) accessible through the CPU aperture for the specified segment (that is, the <b>SegmentId</b> member of DXGKARG_ACQUIRESWIZZLINGRANGE). The allocation must appear exactly as it appears in computer memory after an unswizzling eviction. 

Not all of the requests by the user-mode display driver are accessible to the display miniport driver. Swizzling ranges that the video memory manager acquired are cached based on the allocation that they are associated with and the specified private data. On the first request by the user-mode display driver to access an allocation, the display miniport driver's <i>DxgkDdiAcquireSwizzlingRange</i> function is called to make the allocation accessible. On subsequent requests with matching private data, the previously setup mapping is used to access the allocation. 

The video memory manager calls the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_releaseswizzlingrange.md">DxgkDdiReleaseSwizzlingRange</a> function to release a swizzling range  when an allocation is evicted or destroyed, or when another allocation requires an aperture. An allocation can be associated with any number of swizzling ranges (for example, one aperture per MIP level). 

The number of swizzling ranges that an adapter supports is exposed by the driver in the <b>NumberOfSwizzlingRanges</b> member of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_drivercaps.md">DXGK_DRIVERCAPS</a> structure when the driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_queryadapterinfo.md">DxgkDdiQueryAdapterInfo</a> function is called. All ranges are equal (that is, any range can unswizzle or untile any type of swizzling or tiling). The video memory manager arbitrates the available swizzling ranges among all of the applications that require them.

The driver must use memory-mapped I/O (MMIO) to set up a swizzling range. These swizzling-range accesses must not interfere with the execution of the GPU (that is, the GPU must not be idle when <i>DxgkDdiAcquireSwizzlingRange</i> is called). 

All calls to <i>DxgkDdiAcquireSwizzlingRange</i> are serialized among themselves but not with any other DDI function. 

If the GPU supports swizzling ranges that redirect CPU accesses to non-CPU-accessible memory segments or system memory, the user-mode display driver can set the combination of <b>AcquireAperture</b> and <b>UseAlternateVA</b> bit-field flags in the <b>Flags</b> member of the <a href="..\d3dumddi\ns-d3dumddi-_d3dddicb_lock.md">D3DDDICB_LOCK</a> structure in a call to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_lockcb.md">pfnLockCb</a> function to lock the allocation. In this situation, the video memory manager calls the display miniport driver's <i>DxgkDdiAcquireSwizzlingRange</i> function to acquire a swizzling range for the allocation even though the allocation is located in a non-CPU-accessible memory segment or an aperture segment. Swizzling ranges are associated with some GPU resources (for example, PCI aperture ranges) that the driver manages and are not accessible to or accounted for by the video memory manager. 

A call to <i>DxgkDdiAcquireSwizzlingRange</i> to acquire a swizzling range might fail because a driver-managed resource ran out. Although the swizzling range itself is free, it might not be usable because of the missing resource. The driver can indicate that a swizzling range is unavailable to the video memory manager by returning STATUS_GRAPHICS_UNSWIZZLING_APERTURE_UNAVAILABLE from <i>DxgkDdiAcquireSwizzlingRange</i>. The video memory manager next attempts to release a swizzling range that is currently in use and then calls the driver's <i>DxgkDdiAcquireSwizzlingRange</i> function again to set up the new swizzling range. If all of the swizzling ranges are released and the driver still fails with STATUS_GRAPHICS_UNSWIZZLING_APERTURE_UNAVAILABLE, the video memory manager fails to acquire a swizzling range for the allocation.

<i>DxgkDdiAcquireSwizzlingRange</i> should be made pageable.


## -see-also
<dl>
<dt>
<a href="..\d3dumddi\ns-d3dumddi-_d3dddicb_lock.md">D3DDDICB_LOCK</a>
</dt>
<dt>
<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_drivercaps.md">DXGK_DRIVERCAPS</a>
</dt>
<dt>
<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_acquireswizzlingrange.md">DXGKARG_ACQUIRESWIZZLINGRANGE</a>
</dt>
<dt>
<a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a>
</dt>
<dt>
<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createallocation.md">DxgkDdiCreateAllocation</a>
</dt>
<dt>
<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_queryadapterinfo.md">DxgkDdiQueryAdapterInfo</a>
</dt>
<dt>
<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_releaseswizzlingrange.md">DxgkDdiReleaseSwizzlingRange</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_lockcb.md">pfnLockCb</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_ACQUIRESWIZZLINGRANGE callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

