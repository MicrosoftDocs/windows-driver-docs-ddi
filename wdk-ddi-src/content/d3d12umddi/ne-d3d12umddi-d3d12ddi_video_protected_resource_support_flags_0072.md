---
UID: NE:d3d12umddi.D3D12DDI_VIDEO_PROTECTED_RESOURCE_SUPPORT_FLAGS_0072
title: D3D12DDI_VIDEO_PROTECTED_RESOURCE_SUPPORT_FLAGS_0072
ms.date: 03/24/2020
ms.topic: language-reference
targetos: Windows
ms.assetid: 9c8a22f0-7515-420c-8699-419a3fb11f1d
tech.root: display
description: The protected resource support flags for D3D video operations.
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
 - D3D12DDI_VIDEO_PROTECTED_RESOURCE_SUPPORT_FLAGS_0072
f1_keywords:
 - d3d12umddi//D3D12DDI_VIDEO_PROTECTED_RESOURCE_SUPPORT_FLAGS_0072
 - D3D12DDI_VIDEO_PROTECTED_RESOURCE_SUPPORT_FLAGS_0072
dev_langs:
 - c++
---

## -description

The protected resource support flags for D3D video operations.

## -enum-fields

### -field D3D12DDI_VIDEO_PROTECTED_RESOURCE_SUPPORT_FLAG_0072_NONE

The driver does not support using protected resources with the specified feature.

### -field D3D12DDI_VIDEO_PROTECTED_RESOURCE_SUPPORT_FLAG_0072_SUPPORTED

The driver supports using protected resources with the specified feature.

## -remarks

See the [D3D Video Protected Resources Support Specification](https://microsoft.github.io/DirectX-Specs/d3d/D3D12_Video_ProtectedResourceSupport.html) for more information.

## -see-also

[**D3D12DDI_VIDEO_DECODE_PROTECTED_RESOURCES_DATA_0072**](ns-d3d12umddi-d3d12ddi_video_decode_protected_resources_data_0072.md)

[**D3D12DDI_VIDEO_MOTION_ESTIMATOR_PROTECTED_RESOURCES_DATA_0072**](ns-d3d12umddi-d3d12ddi_video_motion_estimator_protected_resources_data_0072.md)

[**D3D12DDI_VIDEO_PROCESS_PROTECTED_RESOURCES_DATA_0072**](ns-d3d12umddi-d3d12ddi_video_process_protected_resources_data_0072.md)
