---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_EXTENSION_COMMAND_PARAMETERS_DATA_0063
title: D3D12DDI_VIDEO_EXTENSION_COMMAND_PARAMETERS_DATA_0063
author: windows-driver-content
description: Retrieves the array of parameter info for a parameter stage.
tech.root: display
ms.assetid: fab08542-51ea-4d17-90eb-69965f4f7023
ms.author: windowsdriverdev
ms.date: 04/04/2019
ms.topic: struct
f1_keywords:
 - "d3d12umddi/D3D12DDI_VIDEO_EXTENSION_COMMAND_PARAMETERS_DATA_0063"
ms.keywords: D3D12DDI_VIDEO_EXTENSION_COMMAND_PARAMETERS_DATA_0063, D3D12DDI_VIDEO_EXTENSION_COMMAND_PARAMETERS_DATA_0063, 
req.header: d3d12umddi.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1903
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: D3D12DDI_VIDEO_EXTENSION_COMMAND_PARAMETERS_DATA_0063
topic_type: 
 - apiref
api_type: 
 - HeaderDef
api_location: 
 - d3d12umddi.h
api_name: 
 - D3D12DDI_VIDEO_EXTENSION_COMMAND_PARAMETERS_DATA_0063
product:
- Windows
targetos: Windows
ms.custom: UMD DDI Min Version D3D12DDI_SUPPORTED_0043, 19H1
---

# D3D12DDI_VIDEO_EXTENSION_COMMAND_PARAMETERS_DATA_0063 structure

## -description

Retrieves the array of parameter info for a parameter stage.

## -struct-fields

### -field CommandId

[in] The unique identifier for the video extension command.

### -field Stage

[in]  The parameter stage to query.

### -field ParameterCount

[in] This must match the **ParameterCount** returned by the [D3D12DDICAPS_TYPE_VIDEO_ENUMERATE_EXTENSION_COMMAND_PARAMETER_COUNT](ns-d3d12umddi-d3d12ddi_video_extension_command_parameter_count_data_0063.md) query.

### -field pParameterInfos

[out] An array allocated by the runtime for the driver to fill with parameter info. **ParameterCount** indicates the number of array elements.

## -remarks

## -see-also
