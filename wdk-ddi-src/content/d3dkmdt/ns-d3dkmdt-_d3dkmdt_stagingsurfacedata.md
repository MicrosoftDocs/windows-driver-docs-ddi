---
UID: NS:d3dkmdt._D3DKMDT_STAGINGSURFACEDATA
title: _D3DKMDT_STAGINGSURFACEDATA (d3dkmdt.h)
description: The D3DKMDT_STAGINGSURFACEDATA structure describes the lockable staging surface that data is transferred into from an application's back buffer.
old-location: display\d3dkmdt_stagingsurfacedata.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["D3DKMDT_STAGINGSURFACEDATA structure"]
ms.keywords: D3DKMDT_STAGINGSURFACEDATA, D3DKMDT_STAGINGSURFACEDATA structure [Display Devices], DmStructs_94b90abc-85db-4439-a20b-9edeb1a69733.xml, _D3DKMDT_STAGINGSURFACEDATA, d3dkmdt/D3DKMDT_STAGINGSURFACEDATA, display.d3dkmdt_stagingsurfacedata
req.header: d3dkmdt.h
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
req.typenames: D3DKMDT_STAGINGSURFACEDATA
f1_keywords:
 - _D3DKMDT_STAGINGSURFACEDATA
 - d3dkmdt/_D3DKMDT_STAGINGSURFACEDATA
 - D3DKMDT_STAGINGSURFACEDATA
 - d3dkmdt/D3DKMDT_STAGINGSURFACEDATA
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmdt.h
api_name:
 - D3DKMDT_STAGINGSURFACEDATA
---

# _D3DKMDT_STAGINGSURFACEDATA structure


## -description

The D3DKMDT_STAGINGSURFACEDATA structure describes the lockable staging surface that data is transferred into from an application's back buffer.

## -struct-fields

### -field Width

[in] The width of the staging buffer, in pixels.

### -field Height

[in] The height of the staging buffer, in pixels.

### -field Pitch

[out] The width of the staging buffer, in bytes. The driver must return the pitch value because the staging buffer is lockable.

## -remarks

The D3DKMDT_STAGINGSURFACEDATA structure is passed by the Microsoft DirectX graphics kernel subsystem in a call to the display miniport driver's <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_getstandardallocationdriverdata">DxgkDdiGetStandardAllocationDriverData</a> function to generate a description of a lockable staging surface. The graphics subsystem calls the display miniport driver's <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_present">DxgkDdiPresent</a> function to issue bit-block transfer (bitblt) requests to transfer data from an application's back buffer into the staging surface. The staging surface is then locked and read by the CPU. 

A staging surface is potentially created for the present operation when a direct bit-block transfer to the primary surface is not possible (for example, in multiple-monitor or sprites cases). 

This staging surface is always created as an 8-bits-per-color RGB pixel format (which is specified by the D3DDDIFMT_X8R8G8B8 value from the <a href="/windows-hardware/drivers/ddi/d3dukmdt/ne-d3dukmdt-_d3dddiformat">D3DDDIFORMAT</a> enumeration). Because the dimensions of the staging surface always match the dimensions of the back buffer, no stretch or shrink operation is required for the present operation to the staging surface.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dukmdt/ne-d3dukmdt-_d3dddiformat">D3DDDIFORMAT</a>



<a href="/windows-hardware/drivers/ddi/d3dkmdt/ne-d3dkmdt-_d3dkmdt_standardallocation_type">D3DKMDT_STANDARDALLOCATION_TYPE</a>



<a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_createallocation">DXGKARG_CREATEALLOCATION</a>



<a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_getstandardallocationdriverdata">DXGKARG_GETSTANDARDALLOCATIONDRIVERDATA</a>



<a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_createallocation">DxgkDdiCreateAllocation</a>



<a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_getstandardallocationdriverdata">DxgkDdiGetStandardAllocationDriverData</a>



<a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_present">DxgkDdiPresent</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_present">Present</a>
