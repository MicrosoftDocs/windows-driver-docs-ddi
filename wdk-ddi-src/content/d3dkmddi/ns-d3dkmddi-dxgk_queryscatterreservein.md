---
UID: NS:d3dkmddi._DXGK_QUERYSCATTERRESERVEIN
tech.root: display
title: DXGK_QUERYSCATTERRESERVEIN
ms.date: 03/28/2024
targetos: Windows
description: Learn more about the DXGK_QUERYSCATTERRESERVEIN structure.
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
req.typenames: DXGK_QUERYSCATTERRESERVEIN
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
 - _DXGK_QUERYSCATTERRESERVEIN
 - DXGK_QUERYSCATTERRESERVEIN
f1_keywords:
 - _DXGK_QUERYSCATTERRESERVEIN
 - d3dkmddi/_DXGK_QUERYSCATTERRESERVEIN
 - DXGK_QUERYSCATTERRESERVEIN
 - d3dkmddi/DXGK_QUERYSCATTERRESERVEIN
dev_langs:
 - c++
helpviewer_keywords:
 - _DXGK_QUERYSCATTERRESERVEIN
---

# DXGK_QUERYSCATTERRESERVEIN structure (d3dkmddi.h)

## -description

The **DXGK_QUERYSCATTERRESERVEIN** structure contains the input parameters (**pInputData**) for a [**DxgkDdiQueryAdaptedInfo**](nc-d3dkmddi-dxgkddi_queryadapterinfo.md) call with a **Type** of **DXGKQAITYPE_SCATTER_RESERVE**.

## -struct-fields

### -field SegmentId

The segment ID being queried. **SegmentId** refers to local memory segments only.

## -remarks

For more information, see [Live migration on GPU-P devices](/windows-hardware/drivers/display/live-migration-on-gpup-devices).

## -see-also

[**DXGKARG_QUERYADAPTERINFO**](ns-d3dkmddi-_dxgkarg_queryadapterinfo.md)

[**DXGK_QUERYADAPTERINFOTYPE**](ne-d3dkmddi-_dxgk_queryadapterinfotype.md)

[**DxgkDdiQueryAdapterInfo**](nc-d3dkmddi-dxgkddi_queryadapterinfo.md)
