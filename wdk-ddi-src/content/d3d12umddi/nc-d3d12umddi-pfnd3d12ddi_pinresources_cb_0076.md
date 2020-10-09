---
UID: NC:d3d12umddi.PFND3D12DDI_PINRESOURCES_CB_0076
title: PFND3D12DDI_PINRESOURCES_CB_0076 (d3d12umddi.h)
description: Marks the resource as not movable and not eligible to be paged out.
ms.assetid: 1a0ae369-b524-430c-8d27-71a8dd0b9eb8
ms.date: 03/24/2020
keywords: ["PFND3D12DDI_PINRESOURCES_CB_0076 callback function"]
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
 - PFND3D12DDI_PINRESOURCES_CB_0076
 - d3d12umddi/PFND3D12DDI_PINRESOURCES_CB_0076
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_PINRESOURCES_CB_0076
product:
 - Windows
dev_langs:
 - c++
---

# PFND3D12DDI_PINRESOURCES_CB_0076 callback function

## -description

Marks the resource as not movable and not eligible to be paged out.

## -parameters

### -param hRTDevice

Handle that identifies the display device.

### -param Arg

A [**D3D12DDICB_PIN_RESOURCES_0076**](ns-d3d12umddi-d3d12ddicb_pinresources_0076.md) structure that provides the list of resources to pin.

## -returns

Returns HRESULT.

## -prototype

```cpp
//Declaration

PFND3D12DDI_PINRESOURCES_CB_0076 Pfnd3d12ddiPinResources;

// Definition

HRESULT Pfnd3d12ddiPinResources
(
    D3D12DDI_HRTDEVICE hRTDevice,
    CONST D3D12DDICB_PIN_RESOURCES_0076*
)
{...}
```

## -remarks

A resource that has been pinned can be unpinned by calling [**PFND3D12DDI_UNPINRESOURCES_CB_0076**](nc-d3d12umddi-pfnd3d12ddi_unpinresources_cb_0076.md).

## -see-also

[**D3D12DDICB_PIN_RESOURCES_0076**](ns-d3d12umddi-d3d12ddicb_pinresources_0076.md)

[**PFND3D12DDI_UNPINRESOURCES_CB_0076**](nc-d3d12umddi-pfnd3d12ddi_unpinresources_cb_0076.md)
