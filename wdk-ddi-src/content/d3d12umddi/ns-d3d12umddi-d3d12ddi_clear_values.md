---
UID: NS:d3d12umddi.D3D12DDI_CLEAR_VALUES
title: D3D12DDI_CLEAR_VALUES
author: windows-driver-content
description: The D3D12DDI_CLEAR_VALUES structure contains values used to optimize clear operations for a particular resource.
ms.assetid: 25db923b-e26c-44ef-adef-a619df1ac0ef
ms.author: windowsdriverdev
ms.date: 
ms.topic: struct
ms.prod: windows-hardware
ms.technology: windows-devices
ms.keywords: D3D12DDI_CLEAR_VALUES, D3D12DDI_CLEAR_VALUES, 
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
req.typenames: D3D12DDI_CLEAR_VALUES
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	d3d12umddi.h
api_name: 
-	D3D12DDI_CLEAR_VALUES
product:
-	Windows
targetos: Windows
tech.root: display
---

# D3D12DDI_CLEAR_VALUES structure

## -description

The D3D12DDI_CLEAR_VALUES structure contains values used to optimize clear operations for a particular resource.

## -struct-fields

### -field Format

Specifies one member of the [DXGI_FORMAT](https://docs.microsoft.com/windows/desktop/api/dxgiformat/ne-dxgiformat-dxgi_format) enumeration.

The format of the commonly cleared color follows the same validation rules as a view/descriptor creation. In general, the format of the clear color can be any format in the same type-less group that the resource format belongs to.

This Format must match the format of the view used during the clear operation. It indicates whether the Color or the DepthStencil member is valid and how to convert the values for usage with the resource.

### -field Color

The color value that the driver should clear.

### -field DepthStencil
 
Pointer to a [D3D12DDI_DEPTH_STENCIL_VALUES](ns-d3d12umddi-d3d12ddi_depth_stencil_values.md) structure that contains the depth and stencil buffer the driver should clear.

## -remarks

## -see-also