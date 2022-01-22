---
UID: NC:d3d12umddi.PFND3D12DDI_CREATEVIDEOENCODERHEAP_0080_2
tech.root: display
title: PFND3D12DDI_CREATEVIDEOENCODERHEAP_0080_2
ms.date: 02/02/2022
targetos: Windows
description: Learn more about the PFND3D12DDI_CREATEVIDEOENCODERHEAP_0080_2 callback function.
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
 - PFND3D12DDI_CREATEVIDEOENCODERHEAP_0080_2
f1_keywords:
 - PFND3D12DDI_CREATEVIDEOENCODERHEAP_0080_2
 - d3d12umddi/PFND3D12DDI_CREATEVIDEOENCODERHEAP_0080_2
dev_langs:
 - c++
helpviewer_keywords:
 - PFND3D12DDI_CREATEVIDEOENCODERHEAP_0080_2
---

## -description

A client driver's **PFND3D12DDI_CREATEVIDEOENCODERHEAP_0080_2** callback function creates a video encoder heap object.

## -parameters

### -param hDrvDevice [in]

Handle to the D3D12 device.

### -param pCreationArgs [in]

Pointer to a [**D3D12DDIARG_CREATE_VIDEO_ENCODER_HEAP_0080_2**](ns-d3d12umddi-d3d12ddiarg_create_video_encoder_heap_0080_2.md) structure with the arguments used to create a video encoder heap.

### -param hDrvVideoEncoderHeap [out]

Handle to the video encoder heap object. The D3D12 runtime has allocated space for the driver to place its object based on the result of a prior call to [**PFND3D12DDI_CALCPRIVATEVIDEOENCODERHEAPSIZE_0080_2**](nc-d3d12umddi-pfnd3d12ddi_calcprivatevideoencodersize_0082_0.md).

## -returns

Returns an [**HRESULT**](/windows-hardware/drivers/debugger/hresult-values) value.

## -remarks

See [D3D12 video encoding](/windows-hardware/drivers/display/video-encoding-d3d12.md) for more information.

## -see-also

[**D3D12DDIARG_CREATE_VIDEO_ENCODER_HEAP_0080_2**](ns-d3d12umddi-d3d12ddiarg_create_video_encoder_heap_0080_2.md)

[**PFND3D12DDI_CALCPRIVATEVIDEOENCODERHEAPSIZE_0080_2**](nc-d3d12umddi-pfnd3d12ddi_calcprivatevideoencodersize_0082_0.md)

[**PFND3D12DDI_CREATEVIDEOENCODER_0082_0**](nc-d3d12umddi-pfnd3d12ddi_createvideoencoder_0082_0.md)
