---
UID: NS:d3dkmddi._DXGK_DEVICEINFO
title: _DXGK_DEVICEINFO (d3dkmddi.h)
description: The DXGK_DEVICEINFO structure describes parameters that the Microsoft DirectX graphics kernel subsystem requires from the display miniport driver.
old-location: display\dxgk_deviceinfo.htm
ms.date: 05/10/2018
keywords: ["DXGK_DEVICEINFO structure"]
ms.keywords: DXGK_DEVICEINFO, DXGK_DEVICEINFO structure [Display Devices], DmStructs_9e654caa-e4d0-4f2f-bb1a-07bee305f8f6.xml, _DXGK_DEVICEINFO, d3dkmddi/DXGK_DEVICEINFO, display.dxgk_deviceinfo
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
req.irql: 
targetos: Windows
tech.root: display
req.typenames: DXGK_DEVICEINFO
f1_keywords:
 - _DXGK_DEVICEINFO
 - d3dkmddi/_DXGK_DEVICEINFO
 - DXGK_DEVICEINFO
 - d3dkmddi/DXGK_DEVICEINFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGK_DEVICEINFO
 - DXGK_DEVICEINFO
---

# _DXGK_DEVICEINFO structure


## -description

The DXGK_DEVICEINFO structure describes parameters that the Microsoft DirectX graphics kernel subsystem requires from the display miniport driver.

## -struct-fields

### -field DmaBufferSize

[out] The size, in bytes, of the buffer of hardware commands that is sent through direct memory access (DMA) to the hardware.

The DMA buffer can grow and shrink after the device is created; however, the DMA buffer can never shrink smaller than the starting size that <b>DmaBufferSize</b> specifies.

### -field DmaBufferSegmentSet

[out] The identifiers of the segments where the DMA buffers should be made accessible to the graphics processing unit (GPU).

### -field DmaBufferPrivateDataSize

[out] The size, in bytes, of the driver-resident private data structure that is associated with each DMA buffer. Memory for this private data structure is allocated from nonpaged pool. If the driver specifies zero in <b>DmaBufferPrivateDataSize</b>, no memory is allocated for the private data structure.

The private data structure that is associated with a DMA buffer is initialized to zero when the DMA buffer is created. During the lifetime of the DMA buffer, the video memory manager never accesses the private data structure that is associated with the DMA buffer.

### -field AllocationListSize

[out] The starting number of elements in an array of allocations (that is, an array of <a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_allocationlist">DXGK_ALLOCATIONLIST</a> structures). This number is the starting number of allocations that the driver requests to be in the <b>pAllocationList</b> members of <a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_present">DXGKARG_PRESENT</a> and <a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_render">DXGKARG_RENDER</a> structures in calls to the driver's <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_present">DxgkDdiPresent</a> and <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_render">DxgkDdiRender</a> functions. 

The allocation list can grow and shrink after the device is created; however, the allocation list can never shrink smaller than the starting size that <b>AllocationListSize</b> specifies.

### -field PatchLocationListSize

[out] The starting number of elements in an array of patch locations (that is, an array of <a href="/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-_d3dddi_patchlocationlist">D3DDDI_PATCHLOCATIONLIST</a> structures) for the device in user mode and kernel mode. This number is the starting number of patch locations that the driver requests to be in the <b>pPatchLocationListIn</b> members of <a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_render">DXGKARG_RENDER</a> structures in calls to its <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_render">DxgkDdiRender</a> function. 

The patch-location list can grow and shrink after the device is created; however, the patch-location list can never shrink smaller than the starting size that <b>PatchLocationListSize</b> specifies.

### -field Flags

[out] A <a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_deviceinfoflags">DXGK_DEVICEINFOFLAGS</a> structure that identifies, in bit-field flags, information about the device.

## -remarks

The display miniport driver specifies values for the <b>DmaBufferSize</b> and <b>AllocationListSize</b> members to guarantee the following:

<ul>
<li>
The DirectX graphics subsystem can use only one DMA buffer to display (by using the display miniport driver's <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_present">DxgkDdiPresent</a> function) at least one <a href="/windows/win32/api/windef/ns-windef-rect">RECT</a> structure for all scenarios.

</li>
<li>
The sizes of DMA and allocation-list buffers are large enough to hold at least one command that cannot be split across multiple buffers.

</li>
<li>
The sizes of DMA and allocation-list buffers are large enough to avoid setup and DMA overhead. 

</li>
</ul>
The display miniport driver can specify only aperture segments in the <b>DmaBufferSegmentSet</b> member; if the driver specifies a memory segment, a device-creation failure occurs. 

If the driver sets <b>DmaBufferSegmentSet</b> to 0, the video memory manager allocates contiguous paged-locked memory, which is mapped write-combined memory, for the DMA buffers. Therefore, the GPU must access DMA buffers by using PCI cycles on systems where AGP transfers that occur outside the AGP aperture are not permitted.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-_d3dddi_patchlocationlist">D3DDDI_PATCHLOCATIONLIST</a>



<a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_present">DXGKARG_PRESENT</a>



<a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_render">DXGKARG_RENDER</a>



<a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_allocationlist">DXGK_ALLOCATIONLIST</a>



<a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_deviceinfoflags">DXGK_DEVICEINFOFLAGS</a>



<a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_createdevice">DxgkDdiCreateDevice</a>



<a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_present">DxgkDdiPresent</a>



<a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_render">DxgkDdiRender</a>

