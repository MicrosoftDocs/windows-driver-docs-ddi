---
UID: NC:d3d12umddi.PFND3D12DDI_VIDEO_ENCODE_RESOLVE_OUTPUT_METADATA_0082_0
tech.root: display
title: PFND3D12DDI_VIDEO_ENCODE_RESOLVE_OUTPUT_METADATA_0082_0
ms.date: 02/16/2022
targetos: Windows
description: Learn more about the PFND3D12DDI_VIDEO_ENCODE_RESOLVE_OUTPUT_METADATA_0082_0 callback function.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: d3d12umddi.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 11 (WDDM 3.0)
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_VIDEO_ENCODE_RESOLVE_OUTPUT_METADATA_0082_0
f1_keywords:
 - PFND3D12DDI_VIDEO_ENCODE_RESOLVE_OUTPUT_METADATA_0082_0
 - d3d12umddi/PFND3D12DDI_VIDEO_ENCODE_RESOLVE_OUTPUT_METADATA_0082_0
dev_langs:
 - c++
---

## -description

The **PFND3D12DDI_VIDEO_ENCODE_RESOLVE_OUTPUT_METADATA_0082_0** callback function records a command to resolve the output metadata of an [encoding operation](nc-d3d12umddi-pfnd3d12ddi_video_encode_frame_0082_0.md) into a readable format.

## -parameters

### -param hDrvCommandList [in]

Handle to the driver's data for the command list. The driver uses this region of memory to store internal data structures that are related to its command list.

### -param pInputArguments [in]

Pointer to a [**D3D12DDI_VIDEO_ENCODER_RESOLVE_METADATA_INPUT_ARGUMENTS_0080_2**](ns-d3d12umddi-d3d12ddi_video_encoder_resolve_metadata_input_arguments_0080_2.md) structure that contains input arguments for this callback.

### -param pOutputArguments [out]

Pointer to a [**D3D12DDI_VIDEO_ENCODER_RESOLVE_METADATA_OUTPUT_ARGUMENTS_0082_0**](ns-d3d12umddi-d3d12ddi_video_encoder_resolve_metadata_output_arguments_0082_0.md) structure in which to store output from this callback.

## -remarks

See [D3D12 video encoding](/windows-hardware/drivers/display/video-encoding-d3d12.md) for general information.

## -see-also

[**PFND3D12DDI_VIDEO_ENCODE_FRAME_0082_0**](nc-d3d12umddi-pfnd3d12ddi_video_encode_frame_0082_0.md)
