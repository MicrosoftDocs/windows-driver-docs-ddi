---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_DECODE_FRAME_ARGUMENT_0020
title: D3D12DDI_VIDEO_DECODE_FRAME_ARGUMENT_0020 (d3d12umddi.h)
description: Contains the decode parameters for the frame.
old-location: display\d3d12ddi_video_decode_frame_parameter.htm
ms.assetid: 5651BDA8-256F-4041-A8BB-E3B30DB1870C
ms.date: 04/16/2018
ms.keywords: D3D12DDI_VIDEO_DECODE_FRAME_ARGUMENT_0020, D3D12DDI_VIDEO_DECODE_FRAME_ARGUMENT_0020 structure [Display Devices], d3d12umddi/D3D12DDI_VIDEO_DECODE_FRAME_ARGUMENT_0020, display.d3d12ddi_video_decode_frame_parameter
f1_keywords:
 - "d3d12umddi/D3D12DDI_VIDEO_DECODE_FRAME_ARGUMENT_0020"
req.header: d3d12umddi.h
req.include-header: D3d12umddi.h
req.target-type: Windows
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library:
req.lib:
req.dll:
req.irql:
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- D3d12umddi.h
api_name:
- D3D12DDI_VIDEO_DECODE_FRAME_ARGUMENT_0020
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D12DDI_VIDEO_DECODE_FRAME_ARGUMENT_0020
---

# D3D12DDI_VIDEO_DECODE_FRAME_ARGUMENT_0020 structure


## -description


Contains the decode parameters for the frame. Parameter definitions are specified by the codec specification for each decode profile.


## -struct-fields




### -field Type

The type of the parameter. For more information, see the [D3D12DDI_VIDEO_DECODE_PARAMETER_TYPE](ne-d3d12umddi-d3d12ddi_video_decode_parameter_type_0020.md) enumeration.


### -field pData

A pointer to the parameter data.


### -field Size

The size, in bytes, of the parameter data specified by the <i>pData</i> parameter.


## -see-also




[D3D12DDI_VIDEO_DECODE_PARAMETER_TYPE](ne-d3d12umddi-d3d12ddi_video_decode_parameter_type_0020.md)
 

 

