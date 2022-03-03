---
UID: NC:d3d12umddi.PFND3D12DDI_CREATEVIDEOENCODER_0082_0
tech.root: display
title: PFND3D12DDI_CREATEVIDEOENCODER_0082_0
ms.date: 02/16/2022
targetos: Windows
description: Learn more about the PFND3D12DDI_CREATEVIDEOENCODER_0082_0 callback function.
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
 - PFND3D12DDI_CREATEVIDEOENCODER_0082_0
f1_keywords:
 - PFND3D12DDI_CREATEVIDEOENCODER_0082_0
 - d3d12umddi/PFND3D12DDI_CREATEVIDEOENCODER_0082_0
dev_langs:
 - c++
---

## -description

A client driver's **PFND3D12DDI_CREATEVIDEOENCODER_0082_0** callback function creates a video encoder object.

## -parameters

### -param hDrvDevice [in]

Handle to the D3D12 device.

### -param pCreationArgs [in]

Pointer to a [**D3D12DDIARG_CREATE_VIDEO_ENCODER_0080_2**](ns-d3d12umddi-d3d12ddiarg_create_video_encoder_0082_0.md) structure with arguments to create this video encoder object.

### -param hDrvVideoEncoder [in/out]

Handle to the created video encoder object. The D3D12 runtime has allocated space for the driver to place its object based on the result of a prior call to [**PFND3D12DDI_CALCPRIVATEVIDEOENCODERSIZE_0082_0**](nc-d3d12umddi-pfnd3d12ddi_calcprivatevideoencodersize_0082_0.md).

## -returns

Returns an [**HRESULT**](/windows-hardware/drivers/debugger/hresult-values) value.

## -remarks

See [D3D12 video encoding](/windows-hardware/drivers/display/video-encoding-d3d12.md) for general information.

## -see-also

[**D3D12DDI_DEVICE_FUNCS_VIDEO_0082_0**](ns-d3d12umddi-d3d12ddi_device_funcs_video_0082_0.md)

[**D3D12DDIARG_CREATE_VIDEO_ENCODER_0080_2**](ns-d3d12umddi-d3d12ddiarg_create_video_encoder_0082_0.md)

[**PFND3D12DDI_CALCPRIVATEVIDEOENCODERSIZE_0082_0**](nc-d3d12umddi-pfnd3d12ddi_calcprivatevideoencodersize_0082_0.md)

[**PFND3D12DDI_CREATEVIDEOENCODERHEAP_0080_2**](nc-d3d12umddi-pfnd3d12ddi_createvideoencoderheap_0080_2.md)
