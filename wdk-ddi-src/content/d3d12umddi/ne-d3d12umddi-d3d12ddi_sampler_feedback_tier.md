---
UID: NE:d3d12umddi.D3D12DDI_SAMPLER_FEEDBACK_TIER
title: D3D12DDI_SAMPLER_FEEDBACK_TIER
ms.date: 03/24/2020
ms.topic: language-reference
tech.root: display
targetos: Windows
description: The supported sampler feedback tier.
req.construct-type: enumeration
req.ddi-compliance: 
req.header: d3d12umddi.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_SAMPLER_FEEDBACK_TIER
f1_keywords:
 - D3D12DDI_SAMPLER_FEEDBACK_TIER
 - d3d12umddi/D3D12DDI_SAMPLER_FEEDBACK_TIER
dev_langs:
 - c++
---

## -description

The supported sampler feedback tier.

## -enum-fields

### -field D3D12DDI_SAMPLER_FEEDBACK_TIER_NOT_SUPPORTED

Sampler feedback is not supported.

### -field D3D12DDI_SAMPLER_FEEDBACK_TIER_0_9

Sampler feedback is supported for samplers with texture addressing modes D3D12_TEXTURE_ADDRESS_MODE_WRAP or D3D12_TEXTURE_ADDRESS_MODE_CLAMP.

### -field D3D12DDI_SAMPLER_FEEDBACK_TIER_1_0

Sampler feedback is supported for all texture addressing modes, and feedback-writing methods are supported irrespective of the passed-in shader resource view.

## -remarks

A driver can return a supported tier in [**D3D12DDI_D3D12_OPTIONS_DATA_0073**](ns-d3d12umddi-d3d12ddi_d3d12_options_data_0073.md). See the [D3D Sampler Feedback Specification](https://microsoft.github.io/DirectX-Specs/d3d/SamplerFeedback.html) for more information.

## -see-also

[**D3D12DDI_D3D12_OPTIONS_DATA_0073**](ns-d3d12umddi-d3d12ddi_d3d12_options_data_0073.md)

