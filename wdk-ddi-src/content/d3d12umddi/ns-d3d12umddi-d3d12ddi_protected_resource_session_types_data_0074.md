---
UID: NS:d3d12umddi.D3D12DDI_PROTECTED_RESOURCE_SESSION_TYPES_DATA_0074
title: D3D12DDI_PROTECTED_RESOURCE_SESSION_TYPES_DATA_0074
ms.date: 03/24/2020
ms.topic: language-reference
targetos: Windows
ms.assetid: b580333e-c0f9-4611-85a7-d0c8063c4352
tech.root: display
description: Protected resource session types data.
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: d3d12umddi.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr: 
req.target-type: 
req.typenames: D3D12DDI_PROTECTED_RESOURCE_SESSION_TYPES_DATA_0074
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_PROTECTED_RESOURCE_SESSION_TYPES_DATA_0074
f1_keywords:
 - d3d12umddi//D3D12DDI_PROTECTED_RESOURCE_SESSION_TYPES_DATA_0074
 - D3D12DDI_PROTECTED_RESOURCE_SESSION_TYPES_DATA_0074
dev_langs:
 - c++
---

## -description

Protected resource session types data.

## -struct-fields

### -field NodeIndex

[in] In multi-adapter operation, **NodeIndex** indicates which physical adapter of the device this operation applies to.

### -field Count

[in] Size of the **pTypes** array. This value must match the count returned through the D3D12_FEATURE_PROTECTED_RESOURCE_SESSION_TYPE_COUNT check.

### -field pTypes

[out] On return, this array is populated with the supported protected resource session types.

## -remarks

See the [Protected Resources Specification](https://microsoft.github.io/DirectX-Specs/d3d/ProtectedResources.html) for more information.

## -see-also
