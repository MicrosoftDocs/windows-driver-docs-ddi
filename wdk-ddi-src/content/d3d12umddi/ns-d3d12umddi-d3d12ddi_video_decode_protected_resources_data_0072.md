---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_DECODE_PROTECTED_RESOURCES_DATA_0072
title: D3D12DDI_VIDEO_DECODE_PROTECTED_RESOURCES_DATA_0072
ms.date: 03/24/2020
ms.topic: language-reference
targetos: Windows
ms.assetid: d155a473-5e59-4290-8cc1-4d2c1adfd4de
tech.root: display
description: Data structure used to check for video decode protected resource support capabilities on a given node index.
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
req.typenames: D3D12DDI_VIDEO_DECODE_PROTECTED_RESOURCES_DATA_0072
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_VIDEO_DECODE_PROTECTED_RESOURCES_DATA_0072
f1_keywords:
 - d3d12umddi//D3D12DDI_VIDEO_DECODE_PROTECTED_RESOURCES_DATA_0072
 - D3D12DDI_VIDEO_DECODE_PROTECTED_RESOURCES_DATA_0072
dev_langs:
 - c++
---

## -description

Data structure used to check for video decode protected resource support capabilities on a given node index.

## -struct-fields

### -field NodeIndex

[in] In multi-adapter operation, this value indicates which physical adapter of the device this operation applies to.

### -field Configuration

[in] A [**D3D12DDI_VIDEO_DECODE_CONFIGURATION_0020**](ns-d3d12umddi-d3d12ddi_video_decode_configuration_0020.md) structure containing video decode configuration information.

### -field SupportFlags

[out] A [**D3D12DDI_VIDEO_PROTECTED_RESOURCE_SUPPORT_FLAGS_0072**](ne-d3d12umddi-d3d12ddi_video_protected_resource_support_flags_0072.md) value in which to return the video decode protected resource support level.

## -remarks

This structure is the data used when querying [**D3D12DDICAPS_TYPE_VIDEO_0072_DECODE_PROTECTED_RESOURCES**]((ne-d3d12umddi-d3d12ddicaps_type_video_0020.md)) via [**PFND3D12DDI_VIDEO_GETCAPS**](nc-d3d12umddi-pfnd3d12ddi_video_getcaps.md).

See the [D3D Video Protected Resource Support Specification](https://microsoft.github.io/DirectX-Specs/d3d/D3D12_Video_ProtectedResourceSupport.html) for more information.

## -see-also

[**D3D12DDI_VIDEO_DECODE_CONFIGURATION_0020**](ns-d3d12umddi-d3d12ddi_video_decode_configuration_0020.md)

[**D3D12DDI_VIDEO_PROTECTED_RESOURCE_SUPPORT_FLAGS_0072**](ne-d3d12umddi-d3d12ddi_video_protected_resource_support_flags_0072.md)

[**D3D12DDICAPS_TYPE_VIDEO_0020**](ne-d3d12umddi-d3d12ddicaps_type_video_0020.md)

[**PFND3D12DDI_VIDEO_GETCAPS**](nc-d3d12umddi-pfnd3d12ddi_video_getcaps.md)
