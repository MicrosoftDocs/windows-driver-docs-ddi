---
UID: NS:d3dkmddi._DXGKARG_GETSTANDARDALLOCATIONDRIVERDATA
title: DXGKARG_GETSTANDARDALLOCATIONDRIVERDATA (d3dkmddi.h)
description: Learn more about the DXGKARG_GETSTANDARDALLOCATIONDRIVERDATA structure.
ms.date: 11/08/2024
keywords: ["DXGKARG_GETSTANDARDALLOCATIONDRIVERDATA structure"]
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
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
tech.root: display
req.typenames: DXGKARG_GETSTANDARDALLOCATIONDRIVERDATA
f1_keywords:
 - _DXGKARG_GETSTANDARDALLOCATIONDRIVERDATA
 - d3dkmddi/_DXGKARG_GETSTANDARDALLOCATIONDRIVERDATA
 - DXGKARG_GETSTANDARDALLOCATIONDRIVERDATA
 - d3dkmddi/DXGKARG_GETSTANDARDALLOCATIONDRIVERDATA
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGKARG_GETSTANDARDALLOCATIONDRIVERDATA
 - DXGKARG_GETSTANDARDALLOCATIONDRIVERDATA
---

# DXGKARG_GETSTANDARDALLOCATIONDRIVERDATA structure

## -description

The **DXGKARG_GETSTANDARDALLOCATIONDRIVERDATA** structure describes a standard allocation type.

## -struct-fields

### -field StandardAllocationType

[in] A [**D3DKMDT_STANDARDALLOCATION_TYPE**](../d3dkmdt/ne-d3dkmdt-_d3dkmdt_standardallocation_type.md)-typed value that identifies the type of standard allocation to describe.

### -field pCreateSharedPrimarySurfaceData

[in] A pointer to a [**D3DKMDT_SHAREDPRIMARYSURFACEDATA**](../d3dkmdt/ns-d3dkmdt-_d3dkmdt_sharedprimarysurfacedata.md) structure, if **StandardAllocationType** specifies D3DKMDT_STANDARDALLOCATION_SHAREDPRIMARYSURFACE.

### -field pCreateShadowSurfaceData

[in] A pointer to a [**D3DKMDT_SHADOWSURFACEDATA**](../d3dkmdt/ns-d3dkmdt-_d3dkmdt_shadowsurfacedata.md) structure, if **StandardAllocationType** specifies D3DKMDT_STANDARDALLOCATION_SHADOWSURFACE.

### -field pCreateStagingSurfaceData

[in] A pointer to a [**D3DKMDT_STAGINGSURFACEDATA**](../d3dkmdt/ns-d3dkmdt-_d3dkmdt_stagingsurfacedata.md) structure, if **StandardAllocationType** specifies D3DKMDT_STANDARDALLOCATION_STAGINGSURFACE.

### -field pCreateGdiSurfaceData

[in] A pointer to a [**D3DKMDT_GDISURFACEDATA**](../d3dkmdt/ns-d3dkmdt-_d3dkmdt_gdisurfacedata.md) structure, only available if **StandardAllocationType** specifies D3DKMDT_STANDARDALLOCATION_GDISURFACE.

This member is available beginning with Windows 7.

### -field pCreateVirtualGpuSurfaceData

Pointer to a [**D3DKMDT_VIRTUALGPUSURFACEDATA**](../d3dkmdt/ns-d3dkmdt-d3dkmdt_virtualgpusurfacedata.md) structure if **StandardAllocationType** is **D3DKMDT_STANDARDALLOCATION_VIRTUALGPUSURFACE**. Available starting in WDDM 2.1.

### -field pCreateFenceStorageData

Pointer to a [**D3DKMDT_FENCESTORAGESURFACEDATA**](ns-d3dkmddi-d3dkmdt_fencestoragesurfacedata.md) structure if **StandardAllocationType** is **D3DKMDT_STANDARDALLOCATION_FENCESTORAGE**. Available starting in WDDM 3.2.

### -field pAllocationPrivateDriverData

[in/out] A pointer to a block of allocation private data that describes the standard allocation type; otherwise, this member is NULL. The allocation private data that the display miniport driver's (KMD's) [**DxgkDdiGetStandardAllocationDriverData**](../d3dkmddi/nc-d3dkmddi-dxgkddi_getstandardallocationdriverdata.md) function returns depends on the type that the driver requests in **StandardAllocationType**.

### -field AllocationPrivateDriverDataSize

[out] The size, in bytes, of the allocation private data that **pAllocationPrivateDriverData** points to. If the driver sets **pAllocationPrivateDriverData** to NULL, the driver should set **AllocationPrivateDriverDataSize** to the size of the buffer that the driver requires to describe the given standard allocation type.

If the driver doesn't use private data for each allocation for standard allocations types, the driver can set **AllocationPrivateDriverDataSize** to zero.

### -field pResourcePrivateDriverData

[in/out] A pointer to a block of resource private data that describes the standard allocation type; otherwise, this member is NULL. The resource private data that the display miniport driver's [**DxgkDdiGetStandardAllocationDriverData**](../d3dkmddi/nc-d3dkmddi-dxgkddi_getstandardallocationdriverdata.md) function returns depends on the type that the driver requests in **StandardAllocationType**.

### -field ResourcePrivateDriverDataSize

[out] The size, in bytes, of the resource private data that **pResourcePrivateDriverData** points to. If the driver sets **pResourcePrivateDriverData** to NULL, the driver should set **ResourcePrivateDriverDataSize** to the size of the buffer that the driver requires to describe the given standard allocation type.

If the driver does not use private data for each resource for standard allocations types, the driver can set **ResourcePrivateDriverDataSize** to zero.

### -field PhysicalAdapterIndex

[in] The physical adapter index in an LDA configuration where the storage will be resident.

## -remarks

*Standard allocation types* are allocations that must be created in kernel mode without communication from the user-mode display driver.

If the kernel-mode display miniport driver (KMD) returns NULL in the **pAllocationPrivateDriverData** and **pResourcePrivateDriverData** member, it should return the sizes of the buffers that it requires in the **AllocationPrivateDriverDataSize** and **ResourcePrivateDriverDataSize** members. However, the KMD shouldn't change the contents of the standard allocation structure in the union that **DXGKARG_GETSTANDARDALLOCATIONDRIVERDATA** contains to obtain the required sizes of the buffers.

Although KMD can set **ResourcePrivateDriverDataSize** or **AllocationPrivateDriverDataSize** to zero, it can't set both to zero.

## -see-also

[**D3DKMDT_GDISURFACEDATA**](../d3dkmdt/ns-d3dkmdt-_d3dkmdt_gdisurfacedata.md)

[**D3DKMDT_SHADOWSURFACEDATA**](../d3dkmdt/ns-d3dkmdt-_d3dkmdt_shadowsurfacedata.md)

[**D3DKMDT_SHAREDPRIMARYSURFACEDATA**](../d3dkmdt/ns-d3dkmdt-_d3dkmdt_sharedprimarysurfacedata.md)

[**D3DKMDT_STAGINGSURFACEDATA**](../d3dkmdt/ns-d3dkmdt-_d3dkmdt_stagingsurfacedata.md)

[**D3DKMDT_STANDARDALLOCATION_TYPE**](../d3dkmdt/ne-d3dkmdt-_d3dkmdt_standardallocation_type.md)

[**D3DKMDT_VIRTUALGPUSURFACEDATA**](../d3dkmdt/ns-d3dkmdt-d3dkmdt_virtualgpusurfacedata.md)

[**DxgkDdiGetStandardAllocationDriverData**](../d3dkmddi/nc-d3dkmddi-dxgkddi_getstandardallocationdriverdata.md)
