---
UID: NC:d3dkmddi.DXGKDDI_ACQUIRESWIZZLINGRANGE
title: DXGKDDI_ACQUIRESWIZZLINGRANGE
description: The DxgkDdiAcquireSwizzlingRange function makes an allocation accessible through the central processing unit (CPU) aperture for the given segment.
old-location: display\dxgkddiacquireswizzlingrange.htm
ms.assetid: f861e055-70db-4e0a-9c62-87e2d41f92ae
ms.date: 05/10/2018
ms.keywords: DXGKDDI_ACQUIRESWIZZLINGRANGE, DXGKDDI_ACQUIRESWIZZLINGRANGE callback, DmFunctions_6dd5b0ee-666c-45bf-ae39-05e37d74c137.xml, DxgkDdiAcquireSwizzlingRange, DxgkDdiAcquireSwizzlingRange callback function [Display Devices], d3dkmddi/DxgkDdiAcquireSwizzlingRange, display.dxgkddiacquireswizzlingrange
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Desktop
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3dkmddi.h
api_name:
-	DxgkDdiAcquireSwizzlingRange
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# DXGKDDI_ACQUIRESWIZZLINGRANGE callback function


## -description


The <i>DxgkDdiAcquireSwizzlingRange</i> function makes an allocation accessible through the central processing unit (CPU) aperture for the given segment.


## -parameters




### -param hAdapter [in]

[in] A handle to a context block that is associated with a display adapter. The display miniport driver previously provided this handle to the Microsoft DirectX graphics kernel subsystem in the <i>MiniportDeviceContext</i> output parameter of the <a href="https://msdn.microsoft.com/5fd4046f-54c3-4dfc-8d51-0d9ebcde0bea">DxgkDdiAddDevice</a> function.


### -param pAcquireSwizzlingRange [in, out]

[in/out] A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff557539">DXGKARG_ACQUIRESWIZZLINGRANGE</a> structure that contains information for making an allocation accessible through the CPU aperture.


## -returns



<i>DxgkDdiAcquireSwizzlingRange</i> returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|*DxgkDdiAcquireSwizzlingRange* successfully made the allocation accessible.|
|STATUS_GRAPHICS_UNSWIZZLING_APERTURE_UNSUPPORTED|*DxgkDdiAcquireSwizzlingRange* could not program the swizzling range for the allocation. The video memory manager fails to acquire the swizzling range without making further attempts.|
|STATUS_GRAPHICS_UNSWIZZLING_APERTURE_UNAVAILABLE|*DxgkDdiAcquireSwizzlingRange* could not program the swizzling range for the allocation because another swizzling range is currently using the graphics processing unit (GPU) resources that are required. The video memory manager attempts to release a range that is currently in use and then attempts to set up the swizzling range again.|
 




## -remarks



The <i>DxgkDdiAcquireSwizzlingRange</i> function is called after the user-mode display driver requests a virtual address that references the bits of an allocation (that is, after the user-mode display driver calls the <a href="https://msdn.microsoft.com/69022797-432a-410b-8cbf-e1ef7111e7ea">pfnLockCb</a> function with the <b>AcquireAperture</b> bit-field flag set in the <b>Flags</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544205">D3DDDICB_LOCK</a> structure and while the allocation is currently located in a CPU-accessible memory segment). If the <b>AcquireAperture</b> bit-field flag is not set in the call to <b>pfnLockCb</b>, <i>DxgkDdiAcquireSwizzlingRange</i> is not called, and the allocation must be in a format that the user-mode display driver or an application can process. 

When <i>DxgkDdiAcquireSwizzlingRange</i> is called, the display miniport driver must make the specified allocation (that is, the <b>hAllocation</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff557539">DXGKARG_ACQUIRESWIZZLINGRANGE</a> structure that the <i>pAcquireSwizzlingRange</i> parameter points to) accessible through the CPU aperture for the specified segment (that is, the <b>SegmentId</b> member of DXGKARG_ACQUIRESWIZZLINGRANGE). The allocation must appear exactly as it appears in computer memory after an unswizzling eviction. 

Not all of the requests by the user-mode display driver are accessible to the display miniport driver. Swizzling ranges that the video memory manager acquired are cached based on the allocation that they are associated with and the specified private data. On the first request by the user-mode display driver to access an allocation, the display miniport driver's <i>DxgkDdiAcquireSwizzlingRange</i> function is called to make the allocation accessible. On subsequent requests with matching private data, the previously setup mapping is used to access the allocation. 

The video memory manager calls the display miniport driver's <a href="https://msdn.microsoft.com/6c583a48-baa4-429f-b2fc-5f86859617cc">DxgkDdiReleaseSwizzlingRange</a> function to release a swizzling range  when an allocation is evicted or destroyed, or when another allocation requires an aperture. An allocation can be associated with any number of swizzling ranges (for example, one aperture per MIP level). 

The number of swizzling ranges that an adapter supports is exposed by the driver in the <b>NumberOfSwizzlingRanges</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff561062">DXGK_DRIVERCAPS</a> structure when the driver's <a href="https://msdn.microsoft.com/f2f4c54c-7413-48e5-a165-d71f35642b6c">DxgkDdiQueryAdapterInfo</a> function is called. All ranges are equal (that is, any range can unswizzle or untile any type of swizzling or tiling). The video memory manager arbitrates the available swizzling ranges among all of the applications that require them.

The driver must use memory-mapped I/O (MMIO) to set up a swizzling range. These swizzling-range accesses must not interfere with the execution of the GPU (that is, the GPU must not be idle when <i>DxgkDdiAcquireSwizzlingRange</i> is called). 

All calls to <i>DxgkDdiAcquireSwizzlingRange</i> are serialized among themselves but not with any other DDI function. 

If the GPU supports swizzling ranges that redirect CPU accesses to non-CPU-accessible memory segments or system memory, the user-mode display driver can set the combination of <b>AcquireAperture</b> and <b>UseAlternateVA</b> bit-field flags in the <b>Flags</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544205">D3DDDICB_LOCK</a> structure in a call to the <a href="https://msdn.microsoft.com/69022797-432a-410b-8cbf-e1ef7111e7ea">pfnLockCb</a> function to lock the allocation. In this situation, the video memory manager calls the display miniport driver's <i>DxgkDdiAcquireSwizzlingRange</i> function to acquire a swizzling range for the allocation even though the allocation is located in a non-CPU-accessible memory segment or an aperture segment. Swizzling ranges are associated with some GPU resources (for example, PCI aperture ranges) that the driver manages and are not accessible to or accounted for by the video memory manager. 

A call to <i>DxgkDdiAcquireSwizzlingRange</i> to acquire a swizzling range might fail because a driver-managed resource ran out. Although the swizzling range itself is free, it might not be usable because of the missing resource. The driver can indicate that a swizzling range is unavailable to the video memory manager by returning STATUS_GRAPHICS_UNSWIZZLING_APERTURE_UNAVAILABLE from <i>DxgkDdiAcquireSwizzlingRange</i>. The video memory manager next attempts to release a swizzling range that is currently in use and then calls the driver's <i>DxgkDdiAcquireSwizzlingRange</i> function again to set up the new swizzling range. If all of the swizzling ranges are released and the driver still fails with STATUS_GRAPHICS_UNSWIZZLING_APERTURE_UNAVAILABLE, the video memory manager fails to acquire a swizzling range for the allocation.

<i>DxgkDdiAcquireSwizzlingRange</i> should be made pageable.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544205">D3DDDICB_LOCK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557539">DXGKARG_ACQUIRESWIZZLINGRANGE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561062">DXGK_DRIVERCAPS</a>



<a href="https://msdn.microsoft.com/5fd4046f-54c3-4dfc-8d51-0d9ebcde0bea">DxgkDdiAddDevice</a>



<a href="https://msdn.microsoft.com/a28287d6-4dfa-4db4-92df-bbcd9379a5b2">DxgkDdiCreateAllocation</a>



<a href="https://msdn.microsoft.com/f2f4c54c-7413-48e5-a165-d71f35642b6c">DxgkDdiQueryAdapterInfo</a>



<a href="https://msdn.microsoft.com/6c583a48-baa4-429f-b2fc-5f86859617cc">DxgkDdiReleaseSwizzlingRange</a>



<a href="https://msdn.microsoft.com/69022797-432a-410b-8cbf-e1ef7111e7ea">pfnLockCb</a>
 

 

