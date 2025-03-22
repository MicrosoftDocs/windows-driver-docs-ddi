---
UID: NS:d3dkmddi._DXGK_MEMORYRANGE
title: DXGK_MEMORYRANGE (d3dkmddi.h)
description: Learn more about the _DXGK_MEMORYRANGE structure.
ms.date: 03/28/2024
keywords: ["DXGK_MEMORYRANGE structure"]
req.header: d3dkmddi.h
req.construct-type: structure
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
req.typenames: DXGK_MEMORYRANGE
f1_keywords:
 - _DXGK_MEMORYRANGE
 - d3dkmddi/_DXGK_MEMORYRANGE
 - DXGK_MEMORYRANGE
 - d3dkmddi/DXGK_MEMORYRANGE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGK_MEMORYRANGE
 - DXGK_MEMORYRANGE
---

# DXGK_MEMORYRANGE structure (d3dkmddi.h)



## -description

A **DXGK_MEMORYRANGE** structure describes a range of memory.

## -struct-fields

### -field SegmentOffset

The offset from the start of the segment in bytes. The value must be aligned to the segment page boundary.

### -field SizeInBytes

The number of bytes in the range. The value must be a multiple of the segment page size.

## -remarks

One way that **DXGK_MEMORYRANGE** is used is with [**DxgkDdiQueryAdapterInfo**](nc-d3dkmddi-dxgkddi_queryadapterinfo.md) and [**DXGK_QUERYSEGMENTMEMORYSTATE**](ns-d3dkmddi-_dxgk_querysegmentmemorystate.md) to query bad GPU memory ranges. The query is done during adapter object initialization. The driver is called only if [**DXGK_SEGMENTDESCRIPTOR4**](ns-d3dkmddi-_dxgk_segmentdescriptor4.md)::**NumInvalidMemoryRanges** isn't zero for a segment.

## -see-also

[**DXGK_QUERYSEGMENTMEMORYSTATE**](ns-d3dkmddi-_dxgk_querysegmentmemorystate.md)

[**DXGK_SEGMENTDESCRIPTOR4**](ns-d3dkmddi-_dxgk_segmentdescriptor4.md)

[**DXGKARG_CREATEMEMORYBASIS**](ns-d3dkmddi-dxgkarg_creatememorybasis.md)

[**DxgkDdiCreateMemoryBasis**](nc-d3dkmddi-dxgkddi_creatememorybasis.md)

[**DxgkDdiQueryAdapterInfo**](nc-d3dkmddi-dxgkddi_queryadapterinfo.md)
