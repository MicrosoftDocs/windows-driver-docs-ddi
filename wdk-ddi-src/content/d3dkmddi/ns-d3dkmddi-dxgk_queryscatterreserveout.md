---
UID: NS:d3dkmddi._DXGK_QUERYSCATTERRESERVEOUT
tech.root: display
title: DXGK_QUERYSCATTERRESERVEOUT
ms.date: 03/28/2024
targetos: Windows
description: Learn more about the DXGK_QUERYSCATTERRESERVEOUT structure.
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
req.typenames: DXGK_QUERYSCATTERRESERVEOUT
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
 - _DXGK_QUERYSCATTERRESERVEOUT
 - DXGK_QUERYSCATTERRESERVEOUT
f1_keywords:
 - _DXGK_QUERYSCATTERRESERVEOUT
 - d3dkmddi/_DXGK_QUERYSCATTERRESERVEOUT
 - DXGK_QUERYSCATTERRESERVEOUT
 - d3dkmddi/DXGK_QUERYSCATTERRESERVEOUT
dev_langs:
 - c++
helpviewer_keywords:
 - _DXGK_QUERYSCATTERRESERVEOUT
---

# DXGK_QUERYSCATTERRESERVEOUT structure (d3dkmddi.h)

## -description

The **DXGK_QUERYSCATTERRESERVEOUT** structure contains the output parameters (**pOutputData**) for a [**DxgkDdiQueryAdaptedInfo**](nc-d3dkmddi-dxgkddi_queryadapterinfo.md) call with a **Type** of **DXGKQAITYPE_SCATTER_RESERVE**.

## -struct-fields

### -field SetVGPUResourcesPageSize

The page size of the 2nd phase of GPU-VA translation available on the hardware, in bytes. The driver must specify a page size that aligns with the reserve physical assignments (partition VRAM sizes and offsets are multiples of this page size).

## -remarks

For more information, see [Live migration on GPU-P devices](/windows-hardware/drivers/display/live-migration-on-gpup-devices).

## -see-also

[**DXGKARG_QUERYADAPTERINFO**](ns-d3dkmddi-_dxgkarg_queryadapterinfo.md)

[**DXGK_QUERYADAPTERINFOTYPE**](ne-d3dkmddi-_dxgk_queryadapterinfotype.md)

[**DxgkDdiQueryAdapterInfo**](nc-d3dkmddi-dxgkddi_queryadapterinfo.md)
