---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_ENCODER_AV1_CODEC_CONFIGURATION_0095
tech.root: display
title: D3D12DDI_VIDEO_ENCODER_AV1_CODEC_CONFIGURATION_0095
ms.date: 05/14/2024
targetos: Windows
description: Learn more about the D3D12DDI_VIDEO_ENCODER_AV1_CODEC_CONFIGURATION_0095 structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: d3d12umddi.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 24H2 (WDDM 3.2)
req.target-min-winversvr: 
req.target-type: 
req.typenames: D3D12DDI_VIDEO_ENCODER_AV1_CODEC_CONFIGURATION_0095
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_VIDEO_ENCODER_AV1_CODEC_CONFIGURATION_0095
f1_keywords:
 - D3D12DDI_VIDEO_ENCODER_AV1_CODEC_CONFIGURATION_0095
 - d3d12umddi/D3D12DDI_VIDEO_ENCODER_AV1_CODEC_CONFIGURATION_0095
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDI_VIDEO_ENCODER_AV1_CODEC_CONFIGURATION_0095
---

## -description

The **D3D12DDI_VIDEO_ENCODER_AV1_CODEC_CONFIGURATION_0095** structure describes the AV1 codec configuration.

## -struct-fields

### -field FeatureFlags

A [**D3D12DDI_VIDEO_ENCODER_AV1_FEATURE_0095_FLAGS**](ne-d3d12umddi-d3d12ddi_video_encoder_av1_feature_0095_flags.md) enumeration that defines the set of enabled features. Flags can be combined based on the reported capabilities/requirements by the driver.

### -field OrderHintBitsMinus1

The number of bits used to represent the order hint value.

## -remarks

See [D3D12 AV1 video encoding](/windows-hardware/drivers/display/video-encoding-d3d12-av1) for more information.

## -see-also

[**D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_0082_0**](ns-d3d12umddi-d3d12ddi_video_encoder_codec_configuration_0082_0.md)
