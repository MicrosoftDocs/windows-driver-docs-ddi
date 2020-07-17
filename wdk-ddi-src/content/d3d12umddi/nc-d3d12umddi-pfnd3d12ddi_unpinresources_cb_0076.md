---
UID: NC:d3d12umddi.PFND3D12DDI_UNPINRESOURCES_CB_0076
title: PFND3D12DDI_UNPINRESOURCES_CB_0076 (d3d12umddi.h)
description: Unpins a resource that has been pinned with PFND3D12DDI_PINRESOURCES_CB_0076.
ms.assetid: 8942d3d3-1a46-4e1c-b11d-3365e2e4fd4a
ms.date: 03/24/2020
keywords: ["PFND3D12DDI_UNPINRESOURCES_CB_0076 callback function"]
req.header: d3d12umddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
tech.root: display
ms.custom:
f1_keywords:
 - "d3d12umddi/PFND3D12DDI_UNPINRESOURCES_CB_0076"
 - "PFND3D12DDI_UNPINRESOURCES_CB_0076"
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_UNPINRESOURCES_CB_0076
product:
 - Windows
dev_langs:
 - c++
---

# PFND3D12DDI_UNPINRESOURCES_CB_0076 callback function

## -description

Unpins a resource that has been pinned with [**PFND3D12DDI_PINRESOURCES_CB_0076**](nc-d3d12umddi-pfnd3d12ddi_pinresources_cb_0076.md).

## -parameters

### -param hRTDevice

Handle that identifies the display device.

### -param Arg

A [**D3D12DDICB_UNPIN_RESOURCES_0076**](ns-d3d12umddi-d3d12ddicb_unpin_resources_0076.md) structure that provides the list of resources to unpin.

## -returns

Returns HRESULT.

## -prototype

```cpp
//Declaration

PFND3D12DDI_UNPINRESOURCES_CB_0076 Pfnd3d12ddiUnpinResources;

// Definition

HRESULT Pfnd3d12ddiUnpinResources
(
    D3D12DDI_HRTDEVICE hRTDevice,
    CONST D3D12DDICB_UNPIN_RESOURCES_0076*
)
{...}
```

## -remarks

## -see-also

[**D3D12DDICB_UNPIN_RESOURCES_0076**](ns-d3d12umddi-d3d12ddicb_unpin_resources_0076.md)

[**PFND3D12DDI_PINRESOURCES_CB_0076**](nc-d3d12umddi-pfnd3d12ddi_pinresources_cb_0076.md)
