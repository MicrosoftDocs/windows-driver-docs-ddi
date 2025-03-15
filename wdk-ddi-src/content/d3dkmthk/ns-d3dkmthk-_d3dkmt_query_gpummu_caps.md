---
UID: NS:d3dkmthk._D3DKMT_QUERY_GPUMMU_CAPS
title: D3DKMT_QUERY_GPUMMU_CAPS (d3dkmthk.h)
description: Learn more about the D3DKMT_QUERY_GPUMMU_CAPS structure.
ms.date: 02/06/2025
req.header: d3dkmthk.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10 (WDDM 2.0)
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: D3DKMT_QUERY_GPUMMU_CAPS
targetos: Windows
ms.custom: RS5
tech.root: display
f1_keywords:
 - _D3DKMT_QUERY_GPUMMU_CAPS
 - d3dkmthk/_D3DKMT_QUERY_GPUMMU_CAPS
 - D3DKMT_QUERY_GPUMMU_CAPS
 - d3dkmthk/D3DKMT_QUERY_GPUMMU_CAPS
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmthk.h
api_name:
 - _D3DKMT_QUERY_GPUMMU_CAPS
 - D3DKMT_QUERY_GPUMMU_CAPS
dev_langs:
 - c++
---

# D3DKMT_QUERY_GPUMMU_CAPS structure

## -description

The **D3DKMT_QUERY_GPUMMU_CAPS** structure describes the capabilities of the GPU MMU (memory management unit).

## -struct-fields

### -field PhysicalAdapterIndex

[in] The physical adapter index in the LDA (linked display adapter) chain.

### -field Caps

[out] A [**D3DKMT_GPUMMU_CAPS**](ns-d3dkmthk-_d3dkmt_gpummu_caps.md) structure that describes the capabilities of the GPU MMU.

## -see-also

[**D3DKMTQueryAdapterInfo**](nf-d3dkmthk-d3dkmtqueryadapterinfo.md)
