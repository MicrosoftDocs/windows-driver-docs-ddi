---
UID: NS:d3dkmddi._DXGKARG_QUERYDIRTYBITDATA
tech.root: display
title: DXGKARG_QUERYDIRTYBITDATA
ms.date: 03/28/2024
targetos: Windows
description: Learn more about the DXGKARG_QUERYDIRTYBITDATA structure.
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
req.typenames: DXGKARG_QUERYDIRTYBITDATA
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
 - _DXGKARG_QUERYDIRTYBITDATA
 - DXGKARG_QUERYDIRTYBITDATA
f1_keywords:
 - _DXGKARG_QUERYDIRTYBITDATA
 - d3dkmddi/_DXGKARG_QUERYDIRTYBITDATA
 - DXGKARG_QUERYDIRTYBITDATA
 - d3dkmddi/DXGKARG_QUERYDIRTYBITDATA
dev_langs:
 - c++
helpviewer_keywords:
 - _DXGKARG_QUERYDIRTYBITDATA
---

# DXGKARG_QUERYDIRTYBITDATA structure (d3dkmddi.h)

## -description

**DXGKARG_QUERYDIRTYBITDATA** is an input/output parameter for [**DxgkDdiQueryDirtyBitData**](nc-d3dkmddi-dxgkddi_querydirtybitdata.md) to use to query dirty bitplane data.

## -struct-fields

### -field MemoryBasis

[in] Handle to the collection of ranges of physical memory pages to query the modified status of. This handle was previously created by a call to [**DxgkDdiCreateMemoryBasis**](nc-d3dkmddi-dxgkddi_creatememorybasis.md).

### -field SubrangeIndex

[in] If a subrange is indicated (see SubrangeSize below), then this data represents which range in the memory basis to query from.

### -field SubrangeOffset

[in] If **SubrangeSize** isn't 0, then **SubrangeOffset** represents an optional offset into the subrange chosen from which to query the current dirty bitplane. This value is an offset in bytes and is always a multiple of the bitplane page size.

### -field SubrangeSize

[in] Specifies the range of the memory basis to query. When **SubrangeSize** is 0, the driver should query the entire memory basis. When a non-zero size is specified, the driver should query a single range of the memory basis, where **SubrangeIndex** and **SubrangeOffset** provide the starting index of the physical interval to query. **SubrangeSize** is in bytes and is always a multiple of the bitplane page size.

### -field Buffer

[out] A buffer in which to write the resulting bitplane data.

### -field BufferSize

[out] The size of the bit plane buffer, in bytes. The size is guaranteed to be large enough to fit one bit per page within the specified subrange, which is at least ```Size/DXGK_DIRTY_BIT_TRACKING_SEGMENT_CAPS::PageSize/8``` (rounded up) bytes. If a single subrange is queried, **BufferSize** represents **SubrangeSize**, whereas if the entire memory basis is referenced, **BufferSize** is the sum of all **SizeInBytes** of the ranges in the basis.

### -field Flags

[in] One or more [**DXGKARG_QUERYDIRTYBITDATAFLAGS**](ne-d3dkmddi-dxgkarg_querydirtybitdataflags.md) values specifying additional behavior for the call.

## -remarks

For more information, see [Dirty bit tracking](/windows-hardware/drivers/display/dirty-bit-tracking).

## -see-also

[**DXGKARG_QUERYDIRTYBITDATAFLAGS**](ne-d3dkmddi-dxgkarg_querydirtybitdataflags.md)

[**DxgkDdiCreateMemoryBasis**](nc-d3dkmddi-dxgkddi_creatememorybasis.md)

[**DxgkDdiQueryDirtyBitData**](nc-d3dkmddi-dxgkddi_querydirtybitdata.md)
