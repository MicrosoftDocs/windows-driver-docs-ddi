---
UID: NS:d3dkmdt._D3DKMDT_VIRTUALGPUSURFACEDATA
tech.root: display
title: D3DKMDT_VIRTUALGPUSURFACEDATA
ms.date: 11/17/2023
targetos: Windows
description: Learn more about the D3DKMDT_VIRTUALGPUSURFACEDATA structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: d3dkmdt.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: D3DKMDT_VIRTUALGPUSURFACEDATA
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmdt.h
api_name:
 - _D3DKMDT_VIRTUALGPUSURFACEDATA
 - D3DKMDT_VIRTUALGPUSURFACEDATA
f1_keywords:
 - _D3DKMDT_VIRTUALGPUSURFACEDATA
 - d3dkmdt/_D3DKMDT_VIRTUALGPUSURFACEDATA
 - D3DKMDT_VIRTUALGPUSURFACEDATA
 - d3dkmdt/D3DKMDT_VIRTUALGPUSURFACEDATA
dev_langs:
 - c++
helpviewer_keywords:
 - _D3DKMDT_VIRTUALGPUSURFACEDATA
---

## -description

The **D3DKMDT_VIRTUALGPUSURFACEDATA** structure describes a surface allocated for a virtual GPU (vGPU).

## -struct-fields

### -field Size

Size in bytes of the surface.

### -field Alignment

The alignment requirement of the surface, in bytes.

### -field DriverSegmentId

The identifier of the driver segment that contains the surface.

### -field PrivateDriverData

The private driver data associated with the surface.

## -remarks

## -see-also

[**DXGKARG_GETSTANDARDALLOCATIONDRIVERDATA**](../d3dkmddi/ns-d3dkmddi-_dxgkarg_getstandardallocationdriverdata.md)

[**DxgkDdiGetStandardAllocationDriverData**](../d3dkmddi/nc-d3dkmddi-dxgkddi_getstandardallocationdriverdata.md)
