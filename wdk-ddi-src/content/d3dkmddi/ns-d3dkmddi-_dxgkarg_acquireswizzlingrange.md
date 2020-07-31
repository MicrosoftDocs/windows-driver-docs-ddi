---
UID: NS:d3dkmddi._DXGKARG_ACQUIRESWIZZLINGRANGE
title: _DXGKARG_ACQUIRESWIZZLINGRANGE (d3dkmddi.h)
description: The DXGKARG_ACQUIRESWIZZLINGRANGE structure describes parameters for making an allocation accessible through a CPU aperture.
old-location: display\dxgkarg_acquireswizzlingrange.htm
ms.assetid: 865f4d08-f2b3-4922-956f-2c49aa4e68b0
ms.date: 05/10/2018
keywords: ["_DXGKARG_ACQUIRESWIZZLINGRANGE structure"]
ms.keywords: "*INOUT_PDXGKARG_ACQUIRESWIZZLINGRANGE, DXGKARG_ACQUIRESWIZZLINGRANGE, DXGKARG_ACQUIRESWIZZLINGRANGE structure [Display Devices], DmStructs_761fb707-877a-455c-b5cd-0c2e2b050aea.xml, _DXGKARG_ACQUIRESWIZZLINGRANGE, d3dkmddi/DXGKARG_ACQUIRESWIZZLINGRANGE, display.dxgkarg_acquireswizzlingrange"
f1_keywords:
 - "d3dkmddi/DXGKARG_ACQUIRESWIZZLINGRANGE"
 - "DXGKARG_ACQUIRESWIZZLINGRANGE"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3dkmddi.h
api_name:
- DXGKARG_ACQUIRESWIZZLINGRANGE
targetos: Windows
tech.root: display
req.typenames: DXGKARG_ACQUIRESWIZZLINGRANGE
---

# _DXGKARG_ACQUIRESWIZZLINGRANGE structure


## -description


The DXGKARG_ACQUIRESWIZZLINGRANGE structure describes parameters for making an allocation accessible through a CPU aperture.


## -struct-fields




### -field hAllocation

[in] A handle to the allocation that the display miniport driver assigned and that is returned through its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_createallocation">DxgkDdiCreateAllocation</a> function.


### -field PrivateDriverData

[in] A UINT value of private data that the user-mode display driver sends when it calls the Microsoft Direct3D runtime's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_lockcb">pfnLockCb</a> function. The private data should be an index that lets the display miniport driver determine the accessible part of the allocation (for example, the MIP level). This member should not contain a pointer.


### -field RangeId

[in] The zero-based identifier of the swizzling range that the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_acquireswizzlingrange">DxgkDdiAcquireSwizzlingRange</a> function programs.


### -field SegmentId

[in] The identifier of a segment in which the allocation is currently paged.


### -field RangeSize

[in] The size, in bytes, of the range to acquire. This range size is identical to the size of the allocation that <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_acquireswizzlingrange">DxgkDdiAcquireSwizzlingRange</a> acquires a range for. The driver can modify the value in <b>RangeSize</b> when the <b>UseAlternateVA</b> bit-field flag is specified in the <b>Flags</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-_d3dddicb_lockflags">D3DDDICB_LOCKFLAGS</a> structure in a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_lockcb">pfnLockCb</a> function. If the <b>UseAlternateVA</b> flag is not specified, the driver cannot change <b>RangeSize</b>.


### -field CPUTranslatedAddress

[in/out] The base physical address where the CPU should map the allocation. The display miniport driver must set this information when a call to its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_acquireswizzlingrange">DxgkDdiAcquireSwizzlingRange</a> function succeeds. 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-_d3dddicb_lockflags">D3DDDICB_LOCKFLAGS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_acquireswizzlingrange">DxgkDdiAcquireSwizzlingRange</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_createallocation">DxgkDdiCreateAllocation</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_lockcb">pfnLockCb</a>
 

 

