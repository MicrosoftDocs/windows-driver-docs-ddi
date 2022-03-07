---
UID: NC:d3d12umddi.PFND3D12DDI_VIDEO_ENCODE_FRAME_0082_0
tech.root: display
title: PFND3D12DDI_VIDEO_ENCODE_FRAME_0082_0
ms.date: 02/16/2022
targetos: Windows
description: Learn more about the PFND3D12DDI_VIDEO_ENCODE_FRAME_0082_0 callback function.
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
 - PFND3D12DDI_VIDEO_ENCODE_FRAME_0082_0
f1_keywords:
 - PFND3D12DDI_VIDEO_ENCODE_FRAME_0082_0
 - d3d12umddi/PFND3D12DDI_VIDEO_ENCODE_FRAME_0082_0
dev_langs:
 - c++
---

## -description

A client driver's **PFND3D12DDI_VIDEO_ENCODE_FRAME_0082_0** callback function records an encode frame operation to the command list.

## -parameters

### -param hDrvCommandList [in]

Handle to the driver's data for the command list. The driver uses this region of memory to store internal data structures that are related to its command list.

### -param hDrvEncoder [in]

Handle to a video encoder object. The handle was returned when the video encoder object was created.

### -param hDrvVideoEncoderHeap [in]

Handle to a video encoder heap object. The handle was returned when the video encoder heap object was created.

### -param pInputStreamArguments [in]

Pointer to a [**D3D12DDI_VIDEO_ENCODER_ENCODEFRAME_INPUT_STREAM_ARGUMENTS_0082_0**](ns-d3d12umddi-d3d12ddi_video_encoder_encodeframe_input_stream_arguments_0082_0.md) structure that contains the input sequence and picture control parameters for the encode operation.

### -param pOutputStreamArguments [out]

Pointer to a [**D3D12DDI_VIDEO_ENCODER_ENCODEFRAME_OUTPUT_STREAM_ARGUMENTS_0080_2**](ns-d3d12umddi-d3d12ddi_video_encoder_encodeframe_output_stream_arguments_0080_2.md) structure in which the output of the encode operation is returned.

## -remarks

See [D3D12 video encoding](/windows-hardware/drivers/display/video-encoding-d3d12) for general information.

## -see-also

[**D3D12DDI_VIDEO_ENCODER_ENCODEFRAME_INPUT_STREAM_ARGUMENTS_0082_0**](ns-d3d12umddi-d3d12ddi_video_encoder_encodeframe_input_stream_arguments_0082_0.md)

[**D3D12DDI_VIDEO_ENCODER_ENCODEFRAME_OUTPUT_STREAM_ARGUMENTS_0080_2**](ns-d3d12umddi-d3d12ddi_video_encoder_encodeframe_output_stream_arguments_0080_2.md)

[**PFND3D12DDI_CREATE_COMMAND_LIST_0040**](nc-d3d12umddi-pfnd3d12ddi_create_command_list_0040.md)

[**PFND3D12DDI_CREATEVIDEOENCODER_0082_0**](nc-d3d12umddi-pfnd3d12ddi_createvideoencoder_0082_0.md)

[**PFND3D12DDI_CREATEVIDEOENCODERHEAP_0080_2**](nc-d3d12umddi-pfnd3d12ddi_createvideoencoderheap_0080_2.md)
