---
UID: NS:d3d12umddi.D3D12DDI_PIN_RESOURCES_CALLBACKS_0076
title: D3D12DDI_PIN_RESOURCES_CALLBACKS_0076
ms.date: 03/24/2020
ms.topic: language-reference
tech.root: display
targetos: Windows
description: Argument structure for PFND3D12DDI_PINRESOURCES_CB_0076 that provides the list of resources to pin.
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
req.typenames: D3D12DDI_PIN_RESOURCES_CALLBACKS_0076
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_PIN_RESOURCES_CALLBACKS_0076
f1_keywords:
 - D3D12DDI_PIN_RESOURCES_CALLBACKS_0076
 - d3d12umddi/D3D12DDI_PIN_RESOURCES_CALLBACKS_0076
dev_langs:
 - c++
---

## -description

Structure containing callback functions that pin and unpin resources.

## -struct-fields

### -field pfnPinResourcesCb

A [**PFND3D12DDI_PINRESOURCES_CB_0076**](nc-d3d12umddi-pfnd3d12ddi_pinresources_cb_0076.md) callback.

### -field pfnUnpinResourcesCb

A [**PFND3D12DDI_UNPINRESOURCES_CB_0076**](nc-d3d12umddi-pfnd3d12ddi_unpinresources_cb_0076.md) callback.

## -remarks

Drivers that advertise the optional [D3D12DDI_FEATURE_0076_PIN_RESOURCES](ne-d3d12umddi-d3d12ddi_feature_0020.md) extended feature receive a [**PFND3D12DDI_SET_EXTENDED_FEATURE_CALLBACKS_0021**](nc-d3d12umddi-pfnd3d12ddi_set_extended_feature_callbacks_0021.md) call with a DDI table type of D3D12DDI_TABLE_TYPE_0076_PIN_RESOURCES_CALLBACKS and this structure filled out with the callback pointers that the driver can use to perform these functions.

## -see-also

[D3D12DDI_FEATURE_0076_PIN_RESOURCES](ne-d3d12umddi-d3d12ddi_feature_0020.md)

[**PFND3D12DDI_PINRESOURCES_CB_0076**](nc-d3d12umddi-pfnd3d12ddi_pinresources_cb_0076.md)

[**PFND3D12DDI_SET_EXTENDED_FEATURE_CALLBACKS_0021**](nc-d3d12umddi-pfnd3d12ddi_set_extended_feature_callbacks_0021.md)

[**PFND3D12DDI_UNPINRESOURCES_CB_0076**](nc-d3d12umddi-pfnd3d12ddi_unpinresources_cb_0076.md)

