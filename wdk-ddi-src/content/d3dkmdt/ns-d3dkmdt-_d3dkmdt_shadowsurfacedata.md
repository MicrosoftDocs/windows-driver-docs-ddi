---
UID: NS:d3dkmdt._D3DKMDT_SHADOWSURFACEDATA
title: _D3DKMDT_SHADOWSURFACEDATA (d3dkmdt.h)
description: The D3DKMDT_SHADOWSURFACEDATA structure describes a lockable shadow surface, which matches the primary surface in format and resolution for a given display mode.
old-location: display\d3dkmdt_shadowsurfacedata.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["D3DKMDT_SHADOWSURFACEDATA structure"]
ms.keywords: D3DKMDT_SHADOWSURFACEDATA, D3DKMDT_SHADOWSURFACEDATA structure [Display Devices], DmStructs_645dbefc-137b-47c5-aa4b-de9037d71182.xml, _D3DKMDT_SHADOWSURFACEDATA, d3dkmdt/D3DKMDT_SHADOWSURFACEDATA, display.d3dkmdt_shadowsurfacedata
req.header: d3dkmdt.h
req.include-header:
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
req.typenames: D3DKMDT_SHADOWSURFACEDATA
f1_keywords:
 - _D3DKMDT_SHADOWSURFACEDATA
 - d3dkmdt/_D3DKMDT_SHADOWSURFACEDATA
 - D3DKMDT_SHADOWSURFACEDATA
 - d3dkmdt/D3DKMDT_SHADOWSURFACEDATA
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmdt.h
api_name:
 - D3DKMDT_SHADOWSURFACEDATA
---

# _D3DKMDT_SHADOWSURFACEDATA structure


## -description

The D3DKMDT_SHADOWSURFACEDATA structure describes a lockable shadow surface, which matches the primary surface in format and resolution for a given display mode.

## -struct-fields

### -field Width

[in] The width of the surface, in pixels. The driver returns the width value.

### -field Height

[in] The height of the surface, in pixels. The driver returns the height value.

### -field Format

[in] A <a href="/windows-hardware/drivers/ddi/d3dukmdt/ne-d3dukmdt-_d3dddiformat">D3DDDIFORMAT</a>-typed value that indicates the pixel format of the surface. The driver returns the format value.

### -field Pitch

[out] The width of the surface, in bytes. The driver must return the pitch value because the shadow surface is lockable.

## -remarks

The D3DKMDT_SHADOWSURFACEDATA structure is passed by the Microsoft DirectX graphics kernel subsystem in a call to the display miniport driver's <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_getstandardallocationdriverdata">DxgkDdiGetStandardAllocationDriverData</a> function to generate a description of a lockable shadow surface. The DirectX graphics kernel subsystem uses the description in a call to the display miniport driver's <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_createallocation">DxgkDdiCreateAllocation</a> function to create the lockable shadow surface.

The CPU draws into the locked shadow surface, unlocks the shadow surface, and then issues bit-block transfer (bitblt) requests through the <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_present">DxgkDdiPresent</a> function from the shadow surface to the matched shared primary surface. Bit-block transfer requests are also issued to transfer data from a shared primary surface into the shadow surface. 

A color conversion, stretch, or shrink operation is not required when copying data from or to a shadow surface because the source and destination formats and dimensions of shadow and shared primary surfaces always match.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dukmdt/ne-d3dukmdt-_d3dddiformat">D3DDDIFORMAT</a>



<a href="/windows-hardware/drivers/ddi/d3dkmdt/ne-d3dkmdt-_d3dkmdt_standardallocation_type">D3DKMDT_STANDARDALLOCATION_TYPE</a>



<a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_getstandardallocationdriverdata">DXGKARG_GETSTANDARDALLOCATIONDRIVERDATA</a>



<a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_createallocation">DxgkDdiCreateAllocation</a>



<a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_getstandardallocationdriverdata">DxgkDdiGetStandardAllocationDriverData</a>



<a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_present">DxgkDdiPresent</a>
