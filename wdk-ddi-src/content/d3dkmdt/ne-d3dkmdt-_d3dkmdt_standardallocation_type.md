---
UID: NE:d3dkmdt._D3DKMDT_STANDARDALLOCATION_TYPE
title: _D3DKMDT_STANDARDALLOCATION_TYPE (d3dkmdt.h)
description: The D3DKMDT_STANDARDALLOCATION_TYPE enumeration type contains values that identify particular types of surfaces.
old-location: display\d3dkmdt_standardallocation_type.htm
tech.root: display
ms.assetid: b86029c5-9d59-4cd0-81bd-cafb8db2fdfd
ms.date: 05/10/2018
keywords: ["_D3DKMDT_STANDARDALLOCATION_TYPE enumeration"]
ms.keywords: D3DKMDT_STANDARDALLOCATION_GDISURFACE, D3DKMDT_STANDARDALLOCATION_SHADOWSURFACE, D3DKMDT_STANDARDALLOCATION_SHAREDPRIMARYSURFACE, D3DKMDT_STANDARDALLOCATION_STAGINGSURFACE, D3DKMDT_STANDARDALLOCATION_TYPE, D3DKMDT_STANDARDALLOCATION_TYPE enumeration [Display Devices], DmEnums_d1c8e6c1-098d-4c01-9d26-7506ea59f34f.xml, _D3DKMDT_STANDARDALLOCATION_TYPE, d3dkmdt/D3DKMDT_STANDARDALLOCATION_GDISURFACE, d3dkmdt/D3DKMDT_STANDARDALLOCATION_SHADOWSURFACE, d3dkmdt/D3DKMDT_STANDARDALLOCATION_SHAREDPRIMARYSURFACE, d3dkmdt/D3DKMDT_STANDARDALLOCATION_STAGINGSURFACE, d3dkmdt/D3DKMDT_STANDARDALLOCATION_TYPE, display.d3dkmdt_standardallocation_type
f1_keywords:
 - "d3dkmdt/D3DKMDT_STANDARDALLOCATION_TYPE"
 - "D3DKMDT_STANDARDALLOCATION_TYPE"
req.header: d3dkmdt.h
req.include-header: D3dkmdt.h
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
- D3DKMDT_STANDARDALLOCATION_TYPE
targetos: Windows
req.typenames: D3DKMDT_STANDARDALLOCATION_TYPE
---

# _D3DKMDT_STANDARDALLOCATION_TYPE enumeration


## -description


The D3DKMDT_STANDARDALLOCATION_TYPE enumeration type contains values that identify particular types of surfaces.


## -enum-fields




### -field D3DKMDT_STANDARDALLOCATION_SHAREDPRIMARYSURFACE

Indicates that the surface is a shared primary surface, which is opened by multiple applications that all require direct central processing unit (CPU) access to it.


### -field D3DKMDT_STANDARDALLOCATION_SHADOWSURFACE

Indicates that the surface is a shadow surface.


### -field D3DKMDT_STANDARDALLOCATION_STAGINGSURFACE

Indicates that the surface is a staging surface.


### -field D3DKMDT_STANDARDALLOCATION_GDISURFACE

Indicates that the surface is used for GDI hardware acceleration and Desktop Windows Manager (DWM) redirection.

This constant value is available beginning with Windows 7.


### -field D3DKMDT_STANDARDALLOCATION_VGPU




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_d3dkmdt_shadowsurfacedata">D3DKMDT_SHADOWSURFACEDATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_d3dkmdt_sharedprimarysurfacedata">D3DKMDT_SHAREDPRIMARYSURFACEDATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_d3dkmdt_stagingsurfacedata">D3DKMDT_STAGINGSURFACEDATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_createallocation">DXGKARG_CREATEALLOCATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_createallocation">DxgkDdiCreateAllocation</a>
 

 

