---
UID: NS:d3dkmdt._D3DKMDT_SHAREDPRIMARYSURFACEDATA
title: _D3DKMDT_SHAREDPRIMARYSURFACEDATA (d3dkmdt.h)
description: The D3DKMDT_SHAREDPRIMARYSURFACEDATA structure describes a shared primary surface.
old-location: display\d3dkmdt_sharedprimarysurfacedata.htm
tech.root: display
ms.assetid: edf59add-0155-4619-9c7c-fdb63b954f85
ms.date: 05/10/2018
keywords: ["_D3DKMDT_SHAREDPRIMARYSURFACEDATA structure"]
ms.keywords: D3DKMDT_SHAREDPRIMARYSURFACEDATA, D3DKMDT_SHAREDPRIMARYSURFACEDATA structure [Display Devices], DmStructs_5296d822-1a79-459e-809c-2d7381a964b8.xml, _D3DKMDT_SHAREDPRIMARYSURFACEDATA, d3dkmdt/D3DKMDT_SHAREDPRIMARYSURFACEDATA, display.d3dkmdt_sharedprimarysurfacedata
f1_keywords:
 - "d3dkmdt/D3DKMDT_SHAREDPRIMARYSURFACEDATA"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3dkmdt.h
api_name:
- D3DKMDT_SHAREDPRIMARYSURFACEDATA
product:
- Windows
targetos: Windows
req.typenames: D3DKMDT_SHAREDPRIMARYSURFACEDATA
---

# _D3DKMDT_SHAREDPRIMARYSURFACEDATA structure


## -description


The D3DKMDT_SHAREDPRIMARYSURFACEDATA structure describes a shared primary surface.


## -struct-fields




### -field Width

[in] The width of the surface, in pixels. The driver returns the width value.


### -field Height

[in] The height of the surface, in pixels. The driver returns the height value.


### -field Format

[in] A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ne-d3dukmdt-_d3dddiformat">D3DDDIFORMAT</a>-typed value that indicates the pixel format of the surface. The driver returns the format value.


### -field RefreshRate

[in] A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-_d3dddi_rational">D3DDDI_RATIONAL</a> structure that indicates the refresh rate that the shared primary surface was created with.


### -field VidPnSourceId

[in] The zero-based identification number of the video present source in a path of a video present network (VidPN) topology that the surface is located on. 


## -remarks



Multiple processes can lock a shared primary surface. The video memory manager pins the standard allocation for the shared primary surface in video memory so the digital-to-analog converter (DAC) is guaranteed to always scan-out the appropriate data.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ne-d3dukmdt-_d3dddiformat">D3DDDIFORMAT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-_d3dddi_rational">D3DDDI_RATIONAL</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ne-d3dkmdt-_d3dkmdt_standardallocation_type">D3DKMDT_STANDARDALLOCATION_TYPE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_getstandardallocationdriverdata">DXGKARG_GETSTANDARDALLOCATIONDRIVERDATA</a>
 

 

