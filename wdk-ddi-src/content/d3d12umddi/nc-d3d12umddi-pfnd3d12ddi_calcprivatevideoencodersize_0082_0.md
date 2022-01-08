---
UID: NC:d3d12umddi.PFND3D12DDI_CALCPRIVATEVIDEOENCODERSIZE_0082_0
tech.root: display
title: PFND3D12DDI_CALCPRIVATEVIDEOENCODERSIZE_0082_0 callback function (d3d12umddi.h)
ms.date: 02/02/2022
targetos: Windows
description: Learn more about PFND3D12DDI_CALCPRIVATEVIDEOENCODERSIZE_0082_0
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
req.target-min-winverclnt: Windows 11
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
 - PFND3D12DDI_CALCPRIVATEVIDEOENCODERSIZE_0082_0
f1_keywords:
 - PFND3D12DDI_CALCPRIVATEVIDEOENCODERSIZE_0082_0
 - d3d12umddi/PFND3D12DDI_CALCPRIVATEVIDEOENCODERSIZE_0082_0
dev_langs:
 - c++
---

## -description

The **PFND3D12DDI_CALCPRIVATEVIDEOENCODERSIZE_0082_0** callback function calculates the number of bytes needed to store the driver's object that represents the video encoder.

## -parameters

### -param hDrvDevice

Handle for the D3D12 device.

### -param pCreationArgs

Pointer to a [**D3D12DDIARG_CREATE_VIDEO_ENCODER_0082_0**](ns-d3d12umddi-d3d12ddiarg_create_video_encoder_0082_0.md) structure that contains the video encoder creation parameters.

## -returns

Returns the size of the video encoder driver object, in bytes.

## -remarks

On return, the D3D12 runtime will allocate the memory needed to store the driver's object and then call [**PFND3D12DDI_CREATEVIDEOENCODER_0082_0**](nc-d3d12umddi-pfnd3d12ddi_createvideoencoder_0082_0.md) to create the actual object.

See [D3D12 video encoding](/windows-hardware/drivers/display/video-encoding-d3d12.md) for more information.

## -see-also

[**D3D12DDIARG_CREATE_VIDEO_ENCODER_0082_0**](ns-d3d12umddi-d3d12ddiarg_create_video_encoder_0082_0.md)

[**PFND3D12DDI_CREATEVIDEOENCODER_0082_0**](nc-d3d12umddi-pfnd3d12ddi_createvideoencoder_0082_0.md)
