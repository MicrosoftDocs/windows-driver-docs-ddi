---
UID: NS:d3d12umddi.D3D12DDI_3DPIPELINESUPPORT1_DATA_0081
tech.root: display
title: D3D12DDI_3DPIPELINESUPPORT1_DATA_0081
ms.date: 05/13/2021
targetos: Windows
description: D3D12DDI_3DPIPELINESUPPORT1_DATA_0081 is used to indicate the highest feature level of 3D pipeline support in the Direct3D runtime and the driver.
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: d3d12umddi.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.typenames: D3D12DDI_3DPIPELINESUPPORT1_DATA_0081
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_3DPIPELINESUPPORT1_DATA_0081
f1_keywords:
 - D3D12DDI_3DPIPELINESUPPORT1_DATA_0081
 - d3d12umddi/D3D12DDI_3DPIPELINESUPPORT1_DATA_0081
dev_langs:
 - c++
---

## -description

**D3D12DDI_3DPIPELINESUPPORT1_DATA_0081** is used to indicate the highest feature level of 3D pipeline support in the Direct3D runtime and the driver.

## -struct-fields

### -field HighestRuntimeSupportedFeatureLevel

[in] A [**D3D12DDI_3DPIPELINELEVEL**](ne-d3d12umddi-d3d12ddi_3dpipelinelevel.md) value that indicates the runtime's highest supported 3D pipeline feature level.

### -field MaximumDriverSupportedFeatureLevel

[out] A [**D3D12DDI_3DPIPELINELEVEL**](ne-d3d12umddi-d3d12ddi_3dpipelinelevel.md) value that indicates the driver's maximum supported 3D pipeline feature level. **MaximumDriverSupportedFeatureLevel** must be less than or equal to **HighestRuntimeSupportedFeatureLevel**.

## -remarks

**D3D12DDI_3DPIPELINESUPPORT1_DATA_0081** is the structure passed to [**PFND3DDDI_GETCAPS**](../d3dumddi/nc-d3dumddi-pfnd3dddi_getcaps.md) when the cap type is **D3D12DDICAPS_TYPE_0081_3DPIPELINESUPPORT1**.

## -see-also

[**D3D12DDI_3DPIPELINELEVEL**](ne-d3d12umddi-d3d12ddi_3dpipelinelevel.md)

[**D3D12DDIARG_GETCAPS**](../d3dumddi/ns-d3dumddi-_d3dddiarg_getcaps.md)

[**D3DDDICAPS_TYPE**](ne-d3d12umddi-d3d12ddicaps_type.md)

[**PFND3DDDI_GETCAPS**](../d3dumddi/nc-d3dumddi-pfnd3dddi_getcaps.md)
