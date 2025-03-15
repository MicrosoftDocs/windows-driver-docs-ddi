---
UID: NE:d3dkmdt._D3DKMDT_STANDARDALLOCATION_TYPE
title: D3DKMDT_STANDARDALLOCATION_TYPE (d3dkmdt.h)
description: Learn more about the D3DKMDT_STANDARDALLOCATION_TYPE enumeration.
tech.root: display
ms.date: 11/08/2024
keywords: ["D3DKMDT_STANDARDALLOCATION_TYPE enumeration"]
req.header: d3dkmdt.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows Vista
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
req.typenames: D3DKMDT_STANDARDALLOCATION_TYPE
f1_keywords:
 - _D3DKMDT_STANDARDALLOCATION_TYPE
 - d3dkmdt/_D3DKMDT_STANDARDALLOCATION_TYPE
 - D3DKMDT_STANDARDALLOCATION_TYPE
 - d3dkmdt/D3DKMDT_STANDARDALLOCATION_TYPE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmdt.h
api_name:
 - _D3DKMDT_STANDARDALLOCATION_TYPE
 - D3DKMDT_STANDARDALLOCATION_TYPE
---

# D3DKMDT_STANDARDALLOCATION_TYPE enumeration

## -description

The **D3DKMDT_STANDARDALLOCATION_TYPE** enumeration contains values that identify particular types of surfaces.

## -enum-fields

### -field D3DKMDT_STANDARDALLOCATION_SHAREDPRIMARYSURFACE:1

Indicates that the surface is a shared primary surface, which is opened by multiple applications that all require direct central processing unit (CPU) access to it.

### -field D3DKMDT_STANDARDALLOCATION_SHADOWSURFACE:2

Indicates that the surface is a shadow surface.

### -field D3DKMDT_STANDARDALLOCATION_STAGINGSURFACE:3

Indicates that the surface is a staging surface.

### -field D3DKMDT_STANDARDALLOCATION_GDISURFACE:4

Indicates that the surface is used for GDI hardware acceleration and Desktop Windows Manager (DWM) redirection.

This constant value is available beginning with Windows 7.

### -field D3DKMDT_STANDARDALLOCATION_VGPU:5

Indicates that the surface is an allocation for a virtual graphics processing unit (GPU). Available starting in WDDM 2.1.

### -field D3DKMDT_STANDARDALLOCATION_FENCESTORAGE:6

Indicates that the surface is an allocation for a fence.

## -see-also

[**D3DKMDT_SHADOWSURFACEDATA**](ns-d3dkmdt-_d3dkmdt_shadowsurfacedata.md)

[**D3DKMDT_SHAREDPRIMARYSURFACEDATA**](ns-d3dkmdt-_d3dkmdt_sharedprimarysurfacedata.md)

[**D3DKMDT_STAGINGSURFACEDATA**](ns-d3dkmdt-_d3dkmdt_stagingsurfacedata.md)

[**DXGKARG_CREATEALLOCATION**](../d3dkmddi/ns-d3dkmddi-_dxgkarg_createallocation.md)

[**DxgkDdiCreateAllocation**](../d3dkmddi/nc-d3dkmddi-dxgkddi_createallocation.md)
