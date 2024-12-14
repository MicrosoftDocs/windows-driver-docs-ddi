---
UID: NS:d3dkmddi._D3DKMDT_FENCESTORAGESURFACEDATA
tech.root: display
title: D3DKMDT_FENCESTORAGESURFACEDATA
ms.date: 11/08/2024
targetos: Windows
description: Learn more about the D3DKMDT_FENCESTORAGESURFACEDATA structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: d3dkmddi.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 24H2 (WDDM 3.2)
req.target-min-winversvr: 
req.target-type: 
req.typenames: D3DKMDT_FENCESTORAGESURFACEDATA
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _D3DKMDT_FENCESTORAGESURFACEDATA
 - D3DKMDT_FENCESTORAGESURFACEDATA
f1_keywords:
 - _D3DKMDT_FENCESTORAGESURFACEDATA
 - d3dkmddi/_D3DKMDT_FENCESTORAGESURFACEDATA
 - D3DKMDT_FENCESTORAGESURFACEDATA
 - d3dkmddi/D3DKMDT_FENCESTORAGESURFACEDATA
dev_langs:
 - c++
helpviewer_keywords:
 - _D3DKMDT_FENCESTORAGESURFACEDATA
---

## -description

The **D3DKMDT_FENCESTORAGESURFACEDATA** structure describes the memory segments where the fence storage should be placed.

## -struct-fields

### -field PhysicalAdapterIndex

[in] The physical adapter index in an LDA configuration where the fence storage will be resident.

### -field FenceStorageValueType

[in] A [**DXGKARG_FENCESTORAGEVALUETYPE**](../d3dkmdt/ne-d3dkmdt-dxgkarg_fencestoragevaluetype.md) value that specifies the type of the native fence value.

### -field FenceStorageType

[in] A [**D3DDDI_NATIVEFENCE_TYPE**](../d3dukmdt/ne-d3dukmdt-d3dddi_nativefence_type.md) value that specifies the type of the native fence.

### -field PrivateDriverDataSize

[in] The size, in bytes, of the private driver data that **pPrivateDriverData** points to.

### -field pPrivateDriverData

[in] A pointer to the private driver data. Reserved for future use.

### -field Flags

[in] A [**DXGKARG_FENCESTORAGEFLAGS**](ns-d3dkmddi-dxgkarg_fencestorageflags.md) value that specifies the flags for the fence storage.

### -field Reserved

[in] Reserved for future use.

### -field AllocationInfo

[out] A [**DXGK_ALLOCATIONINFO**](ns-d3dkmddi-_dxgk_allocationinfo.md)
 structure in which the driver should return allocation properties.

## -remarks

When the OS calls the kernel-mode driver's [**DxgkDdiGetStandardAllocation**](nc-d3dkmddi-dxgkddi_getstandardallocationdriverdata.md) function with a standard allocation type of [**D3DKMDT_STANDARDALLOCATION_FENCESTORAGE**](../d3dkmdt/ne-d3dkmdt-_d3dkmdt_standardallocation_type.md), the driver must return the memory segments where the fence storage should be placed in **D3DKMDT_FENCESTORAGESURFACEDATA**.

Based on the input fields, the driver needs to fill the following allocation information in [**AllocationInfo**](ns-d3dkmddi-_dxgk_allocationinfo.md):

* **SupportedWriteSegmentSet**
* **EvictionSegmentSet**
* **PreferredSegment**

The driver should ignore the pointer to private data. The driver shouldn't not check that the pointer is NULL and shouldn't request private data by setting its size.

Monitored values of native fences must be placed in a CPU visible memory segment, because they are updated using CPU pointers.

After the creation of a native fence object that has the [**D3DDDI_NATIVEFENCE_TYPE_INTRA_GPU**](../d3dukmdt/ne-d3dukmdt-d3dddi_nativefence_type.md) type, the user-mode driver must always set the initial value by submitting a DMA packet using a GPU virtual address. Current values are packed in a 4K memory page, which can be in a non-CPU visible local memory segment. So, the OS doesn't have a way to set the initial value.

Shared allocations are always placed in system memory.

For more information, see [Native GPU fence objects](/windows-hardware/drivers/display/native-gpu-fence-objects).

## -see-also

[**D3DDDI_NATIVEFENCE_TYPE**](../d3dukmdt/ne-d3dukmdt-d3dddi_nativefence_type.md)

[**D3DKMDT_STANDARDALLOCATION_TYPE**](../d3dkmdt/ne-d3dkmdt-_d3dkmdt_standardallocation_type.md)

[**DXGK_ALLOCATIONINFO**](ns-d3dkmddi-_dxgk_allocationinfo.md)

[**DXGKARG_FENCESTORAGEFLAGS**](ns-d3dkmddi-dxgkarg_fencestorageflags.md)

[**DXGKARG_FENCESTORAGEVALUETYPE**](../d3dkmdt/ne-d3dkmdt-dxgkarg_fencestoragevaluetype.md)

[**DXGKARG_GETSTANDARDALLOCATIONDRIVERDATA**](ns-d3dkmddi-_dxgkarg_getstandardallocationdriverdata.md)

[**DxgkDdiGetStandardAllocation**](nc-d3dkmddi-dxgkddi_getstandardallocationdriverdata.md)
