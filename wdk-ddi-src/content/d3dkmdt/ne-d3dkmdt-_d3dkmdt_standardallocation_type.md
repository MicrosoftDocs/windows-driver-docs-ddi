---
UID: NE:d3dkmdt._D3DKMDT_STANDARDALLOCATION_TYPE
title: "_D3DKMDT_STANDARDALLOCATION_TYPE"
author: windows-driver-content
description: The D3DKMDT_STANDARDALLOCATION_TYPE enumeration type contains values that identify particular types of surfaces.
old-location: display\d3dkmdt_standardallocation_type.htm
old-project: display
ms.assetid: b86029c5-9d59-4cd0-81bd-cafb8db2fdfd
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DKMDT_STANDARDALLOCATION_GDISURFACE, D3DKMDT_STANDARDALLOCATION_SHADOWSURFACE, D3DKMDT_STANDARDALLOCATION_SHAREDPRIMARYSURFACE, D3DKMDT_STANDARDALLOCATION_STAGINGSURFACE, D3DKMDT_STANDARDALLOCATION_TYPE, D3DKMDT_STANDARDALLOCATION_TYPE enumeration [Display Devices], DmEnums_d1c8e6c1-098d-4c01-9d26-7506ea59f34f.xml, _D3DKMDT_STANDARDALLOCATION_TYPE, d3dkmdt/D3DKMDT_STANDARDALLOCATION_GDISURFACE, d3dkmdt/D3DKMDT_STANDARDALLOCATION_SHADOWSURFACE, d3dkmdt/D3DKMDT_STANDARDALLOCATION_SHAREDPRIMARYSURFACE, d3dkmdt/D3DKMDT_STANDARDALLOCATION_STAGINGSURFACE, d3dkmdt/D3DKMDT_STANDARDALLOCATION_TYPE, display.d3dkmdt_standardallocation_type
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dkmdt.h
api_name:
-	D3DKMDT_STANDARDALLOCATION_TYPE
product: Windows
targetos: Windows
req.typenames: D3DKMDT_STANDARDALLOCATION_TYPE
---

# _D3DKMDT_STANDARDALLOCATION_TYPE enumeration


## -description


The D3DKMDT_STANDARDALLOCATION_TYPE enumeration type contains values that identify particular types of surfaces.


## -syntax


````
typedef enum _D3DKMDT_STANDARDALLOCATION_TYPE { 
  D3DKMDT_STANDARDALLOCATION_SHAREDPRIMARYSURFACE  = 1,
  D3DKMDT_STANDARDALLOCATION_SHADOWSURFACE         = 2,
  D3DKMDT_STANDARDALLOCATION_STAGINGSURFACE        = 3,
  D3DKMDT_STANDARDALLOCATION_GDISURFACE            = 4
} D3DKMDT_STANDARDALLOCATION_TYPE;
````


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

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createallocation.md">DxgkDdiCreateAllocation</a>



<a href="..\d3dkmdt\ns-d3dkmdt-_d3dkmdt_stagingsurfacedata.md">D3DKMDT_STAGINGSURFACEDATA</a>



<a href="..\d3dkmdt\ns-d3dkmdt-_d3dkmdt_shadowsurfacedata.md">D3DKMDT_SHADOWSURFACEDATA</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_createallocation.md">DXGKARG_CREATEALLOCATION</a>



<a href="..\d3dkmdt\ns-d3dkmdt-_d3dkmdt_sharedprimarysurfacedata.md">D3DKMDT_SHAREDPRIMARYSURFACEDATA</a>



 

 


