---
UID: NS:d3dkmddi._DXGKARG_CREATEMEMORYBASIS
tech.root: display
title: DXGKARG_CREATEMEMORYBASIS
ms.date: 03/28/2024
targetos: Windows
description: Learn more about the DXGKARG_CREATEMEMORYBASIS structure.
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
req.typenames: DXGKARG_CREATEMEMORYBASIS
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
 - _DXGKARG_CREATEMEMORYBASIS
 - DXGKARG_CREATEMEMORYBASIS
f1_keywords:
 - _DXGKARG_CREATEMEMORYBASIS
 - d3dkmddi/_DXGKARG_CREATEMEMORYBASIS
 - DXGKARG_CREATEMEMORYBASIS
 - d3dkmddi/DXGKARG_CREATEMEMORYBASIS
dev_langs:
 - c++
helpviewer_keywords:
 - _DXGKARG_CREATEMEMORYBASIS
---

# DXGKARG_CREATEMEMORYBASIS structure (d3dkmddi.h)

## -description

The **DXGKARG_CREATEMEMORYBASIS** structure is an input parameter for [**DxgkDdiCreateMemoryBasis**](nc-d3dkmddi-dxgkddi_creatememorybasis.md) to use to create a memory basis.

## -struct-fields

### -field SegmentId

[in] The driver's segment ID.

### -field RangeCount

[in] The number of ranges that this memory basis includes; that is, the number of ranges in **Ranges**'s array.

### -field Ranges[1]

Array of [**DXGK_MEMORYRANGE**](ns-d3dkmddi-_dxgk_memoryrange.md) structures that describe the details for each range of the basis, including **SegmentOffset** and **SizeInBytes**.

## -remarks

For more information, see [Dirty bit tracking](/windows-hardware/drivers/display/dirty-bit-tracking).

## -see-also

[**DxgkDdiCreateMemoryBasis**](nc-d3dkmddi-dxgkddi_creatememorybasis.md)
