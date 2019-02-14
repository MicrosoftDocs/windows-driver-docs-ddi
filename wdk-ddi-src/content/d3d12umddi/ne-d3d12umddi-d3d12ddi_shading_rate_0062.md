---
UID: NE:d3d12umddi.D3D12DDI_SHADING_RATE_0062
title: D3D12DDI_SHADING_RATE_0062
author: windows-driver-content
description: The shading rate at which the variable rate shading occurs.
tech.root: display
ms.assetid: 65780036-2a4b-4fa4-bafb-b6966689120c
ms.author: windowsdriverdev
ms.date: 04/04/2019
ms.topic: enum
ms.keywords: D3D12DDI_SHADING_RATE_0062, D3D12DDI_SHADING_RATE_0062, 
req.header: d3d12umddi.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1903
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.ddi-compliance:
req.max-support:
req.typenames: D3D12DDI_SHADING_RATE_0062
topic_type: 
 - apiref
api_type: 
 - HeaderDef
api_location: 
 - d3d12umddi.h
api_name: 
 - D3D12DDI_SHADING_RATE_0062
product:
- Windows
targetos: Windows
ms.custom: D3D12 Release 6, Build rev 2.
---

# D3D12DDI_SHADING_RATE_0062 enumeration

## -description

The shading rate at which the variable rate shading occurs.

## -enum-fields

### -field D3D12DDI_SHADING_RATE_0062_1X1

No change to the shading rate.

### -field D3D12DDI_SHADING_RATE_0062_1X2

Reduces vertical resolution 2x.

### -field D3D12DDI_SHADING_RATE_0062_2X1

Reduces horizontal resolution 2x.

### -field D3D12DDI_SHADING_RATE_0062_2X2

Reduces both axes by 2x.

### -field D3D12DDI_SHADING_RATE_0062_2X4

Reduce horizontal res 2x, vertical by 4x.

### -field D3D12DDI_SHADING_RATE_0062_4X2

Reduce horizontal res 4x, vertical by 2x.

### -field D3D12DDI_SHADING_RATE_0062_4X4 

Reduces both axes by 4x.

## -remarks

The values are organized so that shading rates are easily decomposable into two axes, where each axis’s values are compactly represented in logarithmic space.

## -see-also