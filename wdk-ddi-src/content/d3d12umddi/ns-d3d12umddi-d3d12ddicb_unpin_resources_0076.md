---
UID: NS:d3d12umddi.D3D12DDICB_UNPIN_RESOURCES_0076
title: D3D12DDICB_UNPIN_RESOURCES_0076
ms.date: 03/24/2020
ms.topic: language-reference
ms.assetid: 2603827f-949d-442e-9ebf-728878c525af
tech.root: display
targetos: Windows
description: Argument structure for PFND3D12DDI_UNPINRESOURCES_CB_0076 that provides the list of resources to unpin.
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
req.target-min-winversvr: 
req.target-type: 
req.typenames: D3D12DDICB_UNPIN_RESOURCES_0076
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDICB_UNPIN_RESOURCES_0076
f1_keywords:
 - D3D12DDICB_UNPIN_RESOURCES_0076
 - d3d12umddi/D3D12DDICB_UNPIN_RESOURCES_0076
dev_langs:
 - c++
---

## -description

Argument structure for [**PFND3D12DDI_UNPINRESOURCES_CB_0076**](nc-d3d12umddi-pfnd3d12ddi_unpinresources_cb_0076.md) that provides the list of resources to unpin.

## -struct-fields

### -field NumResources

Size of the **hResources** handle array.

### -field hResources

The list of D3D12DDI_HRTRESOURCE resources to unpin.

## -remarks

## -see-also

[**PFND3D12DDI_UNPINRESOURCES_CB_0076**](nc-d3d12umddi-pfnd3d12ddi_unpinresources_cb_0076.md)

