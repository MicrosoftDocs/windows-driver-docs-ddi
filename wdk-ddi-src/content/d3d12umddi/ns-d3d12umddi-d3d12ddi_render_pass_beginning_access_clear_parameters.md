---
UID: NS:d3d12umddi.D3D12DDI_RENDER_PASS_BEGINNING_ACCESS_CLEAR_PARAMETERS
title: D3D12DDI_RENDER_PASS_BEGINNING_ACCESS_CLEAR_PARAMETERS (d3d12umddi.h)
description: Parameters needed to specify whether the application has a dependency on the resource being cleared, to a specific color.
ms.assetid: c8a75393-027c-4db8-a20d-d8671c4d22e8
ms.date: 10/19/2018
keywords: ["D3D12DDI_RENDER_PASS_BEGINNING_ACCESS_CLEAR_PARAMETERS structure"]
f1_keywords:
 - "d3d12umddi/D3D12DDI_RENDER_PASS_BEGINNING_ACCESS_CLEAR_PARAMETERS"
 - "D3D12DDI_RENDER_PASS_BEGINNING_ACCESS_CLEAR_PARAMETERS"
ms.keywords: D3D12DDI_RENDER_PASS_BEGINNING_ACCESS_CLEAR_PARAMETERS, D3D12DDI_RENDER_PASS_BEGINNING_ACCESS_CLEAR_PARAMETERS, 
req.header: d3d12umddi.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: D3D12DDI_RENDER_PASS_BEGINNING_ACCESS_CLEAR_PARAMETERS
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- d3d12umddi.h
api_name: 
- D3D12DDI_RENDER_PASS_BEGINNING_ACCESS_CLEAR_PARAMETERS
product:
- Windows
targetos: Windows
tech.root: display
dev_langs:
 - c++
ms.custom: RS5
---

# D3D12DDI_RENDER_PASS_BEGINNING_ACCESS_CLEAR_PARAMETERS structure

## -description

Parameters needed to specify whether the application has a dependency on the resource being cleared, to a specific color.

## -struct-fields

### -field ClearValue
 
Pointer to a [D3D12DDI_CLEAR_VALUES](ns-d3d12umddi-d3d12ddi_clear_values.md) structure that holds the parameters need to begin a Render Pass.

## -remarks

## -see-also
