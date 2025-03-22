---
UID: NE:d3dkmddi._DXGKARG_QUERYDIRTYBITDATAFLAGS
tech.root: display
title: DXGKARG_QUERYDIRTYBITDATAFLAGS
ms.date: 03/28/2024
targetos: Windows
description: Learn more about the DXGKARG_QUERYDIRTYBITDATAFLAGS enumeration.
prerelease: false
req.construct-type: enumeration
req.ddi-compliance: 
req.header: d3dkmddi.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: Windows 11, version 24H2 (WDDM 3.2) 
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
typedef_isUnnamed: false
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGKARG_QUERYDIRTYBITDATAFLAGS
 - DXGKARG_QUERYDIRTYBITDATAFLAGS
f1_keywords:
 - _DXGKARG_QUERYDIRTYBITDATAFLAGS
 - d3dkmddi/_DXGKARG_QUERYDIRTYBITDATAFLAGS
 - DXGKARG_QUERYDIRTYBITDATAFLAGS
 - d3dkmddi/DXGKARG_QUERYDIRTYBITDATAFLAGS
dev_langs:
 - c++
helpviewer_keywords:
 - _DXGKARG_QUERYDIRTYBITDATAFLAGS
---

# DXGKARG_QUERYDIRTYBITDATAFLAGS enumeration (d3dkmddi.h)

## -description

The **DXGKARG_QUERYDIRTYBITDATAFLAGS** enumeration specifies flags for a call to [**DxgkDdiQueryDirtyBitData**](nc-d3dkmddi-dxgkddi_querydirtybitdata.md).

## -enum-fields

### -field DXGKARG_QUERYDIRTYBITDATAFLAGS_CLEARDATA:1

Indicates that the driver should atomically clear the bitplane data during the request. Otherwise, the driver should return a copy of the data without clearing it.

## -remarks

For more information, see [Dirty bit tracking](/windows-hardware/drivers/display/dirty-bit-tracking).

## -see-also

[**DXGKARG_QUERYDIRTYBITDATA**](ns-d3dkmddi-dxgkarg_querydirtybitdata.md)

[**DxgkDdiQueryDirtyBitData**](nc-d3dkmddi-dxgkddi_querydirtybitdata.md)
