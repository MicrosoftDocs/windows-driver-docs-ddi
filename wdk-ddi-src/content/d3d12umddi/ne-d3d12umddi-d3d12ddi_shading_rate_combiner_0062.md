---
UID: NE:d3d12umddi.D3D12DDI_SHADING_RATE_COMBINER_0062
title: D3D12DDI_SHADING_RATE_COMBINER_0062
author: windows-driver-content
description: Indicates the type of combiner used to combine two shading rates A and B, where A is the pipeline/render state (per draw) shading rate, and B is one of the following types of shading rates.
tech.root: display
ms.assetid: d1613af5-477e-42cf-a804-f830b82ce2bf
ms.author: windowsdriverdev
ms.date: 04/04/2019
ms.topic: enum
ms.keywords: D3D12DDI_SHADING_RATE_COMBINER_0062, D3D12DDI_SHADING_RATE_COMBINER_0062,
req.header: d3d12umddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1903
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.max-support: 
req.typenames: D3D12DDI_SHADING_RATE_COMBINER_0062
targetos: Windows
ms.custom: D3D12 Release 6, Build rev 2., 19H1
f1_keywords:
 - "d3d12umddi/D3D12DDI_SHADING_RATE_COMBINER_0062"
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_SHADING_RATE_COMBINER_0062
product:
 - Windows
dev_langs:
 - c++
---

# D3D12DDI_SHADING_RATE_COMBINER_0062 enumeration

## -description

Indicates the type of combiner used to combine two shading rates A and B, where A is the pipeline/render state (per draw) shading rate, and B is one of the following types of shading rates:

* a provoking vertex shading rate (from a vertex shader)
* a per primitive shading rate (from a geometry shader)
* an image based shading rate

## -enum-fields

### -field D3D12DDI_SHADING_RATE_COMBINER_0062_PASSTHROUGH

The default combiner, where the result is A. The pipeline/render state (per draw) shading rate is used.

### -field D3D12DDI_SHADING_RATE_COMBINER_0062_OVERRIDE

The shading rate of type B is used as the shading rate.

### -field D3D12DDI_SHADING_RATE_COMBINER_0062_MIN

The combined shading rate is the minimum of A and B. This shading rate is the higher quality.

### -field D3D12DDI_SHADING_RATE_COMBINER_0062_MAX

The combined shading rate is the maximum of A and B. This shading rate is the lower quality.

### -field D3D12DDI_SHADING_RATE_COMBINER_0062_SUM

Apply the cost of B relative to A. The combined rate is equal to min(*maxRate*, A.xy + B.xy), where *maxRate* is the largest permitted dimension of coarse pixel on the device.

## -remarks

When specifying a shader rate by vertex attribute:

* If a geometry shader is used, the shading rate can be specified through the vertex attribute.

* If a geometry shader is not used, the shading rate is specified by the provoking vertex.

## -see-also

