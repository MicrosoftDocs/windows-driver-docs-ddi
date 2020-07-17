---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_EXTENSION_COMMAND_CAPS_DATA_0063
title: D3D12DDI_VIDEO_EXTENSION_COMMAND_CAPS_DATA_0063
author: windows-driver-content
description: D3D12DDI_VIDEO_EXTENSION_COMMAND_CAPS_DATA is the data struct used in the query for video extension command capabilities.
tech.root: display
ms.assetid: 1959ae63-e4d7-4615-97c5-872b41e8839e
ms.author: windowsdriverdev
ms.date: 04/04/2019
keywords: ["D3D12DDI_VIDEO_EXTENSION_COMMAND_CAPS_DATA_0063 structure"]
f1_keywords:
 - "d3d12umddi/D3D12DDI_VIDEO_EXTENSION_COMMAND_CAPS_DATA_0063"
 - "D3D12DDI_VIDEO_EXTENSION_COMMAND_CAPS_DATA_0063"
ms.keywords: D3D12DDI_VIDEO_EXTENSION_COMMAND_CAPS_DATA_0063, D3D12DDI_VIDEO_EXTENSION_COMMAND_CAPS_DATA_0063, 
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
req.typenames: D3D12DDI_VIDEO_EXTENSION_COMMAND_CAPS_DATA_0063
topic_type: 
 - apiref
api_type: 
 - HeaderDef
api_location: 
 - d3d12umddi.h
api_name: 
 - D3D12DDI_VIDEO_EXTENSION_COMMAND_CAPS_DATA_0063
product:
- Windows
targetos: Windows
dev_langs:
 - c++
ms.custom: UMD DDI Min Version D3D12DDI_SUPPORTED_0043, 19H1
---

# D3D12DDI_VIDEO_EXTENSION_COMMAND_CAPS_DATA_0063 structure

## -description

D3D12DDI_VIDEO_EXTENSION_COMMAND_CAPS_DATA is the data structure used in the query for video extension command capabilities. Input and output structures are defined by the particular video command extension. These structures may only be used for querying capabilities and only support print on demand (POD) data types.

## -struct-fields

### -field NodeIndex

[in] For single GPU operation, set this to zero. If there are multiple GPU nodes, set a bit to identify the node (the device's physical adapter) to which the command queue applies. Each bit in the mask corresponds to a single node. Only 1 bit may be set.

### -field CommandId

[in] The unique identifier for the video extension command.

### -field pInputData

[in] Input data for the capability query allocated by the caller with a size of **InputDataSizeInBytes**. This struct is enumerable as the **D3D12DDI_VIDEO_EXTENSION_COMMAND_PARAMETER_STAGE_0063_CAPS_INPUT** parameter stage of the [D3D12DDI_VIDEO_EXTENSION_COMMAND_PARAMETER_STAGE_0063](ne-d3d12umddi-d3d12ddi_video_extension_command_parameter_stage_0063.md) enumeration.

### -field InputDataSizeInBytes

[in] The byte size of the input data allocation.

### -field pOutputData

[out] Output data for the capability query allocated by the caller with a size of OutputDataSizeInBytes. This struct is enumerable as the **D3D12DDI_VIDEO_EXTENSION_COMMAND_PARAMETER_STAGE_0063_CAPS_OUTPUT** parameter stage of the [D3D12DDI_VIDEO_EXTENSION_COMMAND_PARAMETER_STAGE_0063](ne-d3d12umddi-d3d12ddi_video_extension_command_parameter_stage_0063.md) enumeration.

### -field OutputDataSizeInBytes
 
[out] The byte size of the output data allocation.

## -remarks

## -see-also
