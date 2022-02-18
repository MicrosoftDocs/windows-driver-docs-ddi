---
UID: NS:d3d12umddi.D3D12DDI_DEVICE_FUNCS_VIDEO_0082_0
tech.root: display
title: D3D12DDI_DEVICE_FUNCS_VIDEO_0082_0
ms.date: 02/16/2022
targetos: Windows
description: Learn more about the D3D12DDI_DEVICE_FUNCS_VIDEO_0082_0 structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: d3d12umddi.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11 (WDDM 3.0)
req.target-min-winversvr: 
req.target-type: 
req.typenames: D3D12DDI_DEVICE_FUNCS_VIDEO_0082_0
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_DEVICE_FUNCS_VIDEO_0082_0
f1_keywords:
 - D3D12DDI_DEVICE_FUNCS_VIDEO_0082_0
 - d3d12umddi/D3D12DDI_DEVICE_FUNCS_VIDEO_0082_0
dev_langs:
 - c++
---

## -description

The **D3D12DDI_DEVICE_FUNCS_VIDEO_0082_0** structure contains device driver functions for core features in video, used in D3D12DDI_FEATURE_VERSION_VIDEO_0083_0.

## -struct-fields

### -field pfnGetCaps

Pointer to a [**PFND3D12DDI_VIDEO_GETCAPS**](nc-d3d12umddi-pfnd3d12ddi_video_getcaps.md) callback function.

### -field pfnCalcPrivateVideoDecoderSize

Pointer to a [**PFND3D12DDI_CALCPRIVATEVIDEODECODERSIZE_0072**](nc-d3d12umddi-pfnd3d12ddi_calcprivatevideodecodersize_0072.md) callback function.

### -field pfnCreateVideoDecoder

Pointer to a [**PFND3D12DDI_CREATEVIDEODECODER_0072**](nc-d3d12umddi-pfnd3d12ddi_createvideodecoder_0072.md) callback function.

### -field pfnDestroyVideoDecoder

Pointer to a [**PFND3D12DDI_DESTROYVIDEODECODER_0021**](nc-d3d12umddi-pfnd3d12ddi_destroyvideodecoder_0021.md) callback function.

### -field pfnCalcPrivateVideoDecoderHeapSize

Pointer to a [**PFND3D12DDI_CALCPRIVATEVIDEODECODERHEAPSIZE_0072**](nc-d3d12umddi-pfnd3d12ddi_calcprivatevideodecoderheapsize_0072.md) callback function.

### -field pfnCreateVideoDecoderHeap

Pointer to a [**PFND3D12DDI_CREATEVIDEODECODERHEAP_0072**](nc-d3d12umddi-pfnd3d12ddi_createvideodecoderheap_0072.md) callback function.

### -field pfnDestroyVideoDecoderHeap

Pointer to a [**PFND3D12DDI_DESTROYVIDEODECODERHEAP_0032**](nc-d3d12umddi-pfnd3d12ddi_destroyvideodecoderheap_0032.md) callback function.

### -field pfnCalcPrivateVideoProcessorSize

Pointer to a [**PFND3D12DDI_CALCPRIVATEVIDEOPROCESSORSIZE_0072**](nc-d3d12umddi-pfnd3d12ddi_calcprivatevideoprocessorsize_0072.md) callback function.

### -field pfnCreateVideoProcessor

Pointer to a [**PFND3D12DDI_CREATEVIDEOPROCESSOR_0072**](nc-d3d12umddi-pfnd3d12ddi_createvideoprocessor_0072.md) callback function.

### -field pfnDestroyVideoProcessor

Pointer to a [**PFND3D12DDI_DESTROYVIDEOPROCESSOR_0021**](nc-d3d12umddi-pfnd3d12ddi_destroyvideoprocessor_0021.md) callback function.

### -field pfnCalcPrivateVideoMotionEstimatorSize

Pointer to a [**PFND3D12DDI_CALCPRIVATEVIDEOMOTIONESTIMATORSIZE_0060**](nc-d3d12umddi-pfnd3d12ddi_calcprivatevideomotionestimatorsize_0060.md) callback function.

### -field pfnCreateVideoMotionEstimator

Pointer to a [**PFND3D12DDI_CREATEVIDEOMOTIONESTIMATOR_0060**](nc-d3d12umddi-pfnd3d12ddi_createvideomotionestimator_0060.md) callback function.

### -field pfnDestroyVideoMotionEstimator

Pointer to a [**PFND3D12DDI_DESTROYVIDEOMOTIONESTIMATOR_0053**](nc-d3d12umddi-pfnd3d12ddi_destroyvideomotionestimator_0053.md) callback function.

### -field pfnCalcPrivateVideoMotionVectorHeapSize

Pointer to a [**PFND3D12DDI_CALCPRIVATEVIDEOMOTIONVECTORHEAPSIZE_0060**](nc-d3d12umddi-pfnd3d12ddi_calcprivatevideomotionvectorheapsize_0060.md) callback function.

### -field pfnCreateVideoMotionVectorHeap

Pointer to a [**PFND3D12DDI_CREATEVIDEOMOTIONVECTORHEAP_0060**](nc-d3d12umddi-pfnd3d12ddi_createvideomotionvectorheap_0060.md) callback function.

### -field pfnDestroyVideoMotionVectorHeap

Pointer to a [**PFND3D12DDI_DESTROYVIDEOMOTIONVECTORHEAP_0053**](nc-d3d12umddi-pfnd3d12ddi_destroyvideomotionvectorheap_0053.md) callback function.

### -field pfnCalcPrivateVideoExtensionCommandSize

Pointer to a [**PFND3D12DDI_CALCPRIVATEVIDEOEXTENSIONCOMMANDSIZE_0061**](nc-d3d12umddi-pfnd3d12ddi_calcprivatevideoextensioncommandsize_0061.md) callback function.

### -field pfnCreateVideoExtensionCommand

Pointer to a [**PFND3D12DDI_CREATEVIDEOEXTENSIONCOMMAND_0063**](nc-d3d12umddi-pfnd3d12ddi_createvideoextensioncommand_0063.md) callback function.

### -field pfnDestroyVideoExtensionCommand

Pointer to a [**PFND3D12DDI_DESTROYVIDEOEXTENSIONCOMMAND_0063**](nc-d3d12umddi-pfnd3d12ddi_destroyvideoextensioncommand_0063.md) callback function.

### -field pfnExecuteDeviceVideoExtensionCommand

Pointer to a [**PFND3D12DDI_EXECUTEDEVICEVIDEOEXTENSIONCOMMAND_0076**]() callback function.

### -field pfnCalcPrivateVideoEncoderSize

Pointer to a [**PFND3D12DDI_CALCPRIVATEVIDEOENCODERSIZE_0082_0**](nc-d3d12umddi-pfnd3d12ddi_calcprivatevideoencodersize_0082_0.md) callback function.

### -field pfnCreateVideoEncoder

Pointer to a [**PFND3D12DDI_CREATEVIDEOENCODER_0082_0**](nc-d3d12umddi-pfnd3d12ddi_createvideoencoder_0082_0.md) callback function.

### -field pfnDestroyVideoEncoder

Pointer to a [**PFND3D12DDI_DESTROYVIDEOENCODER_0080**](nc-d3d12umddi-pfnd3d12ddi_destroyvideoencoder_0080.md) callback function.

### -field pfnCalcPrivateVideoEncoderHeapSize

Pointer to a [**PFND3D12DDI_CALCPRIVATEVIDEOENCODERHEAPSIZE_0080_2**](nc-d3d12umddi-pfnd3d12ddi_calcprivatevideoencoderheapsize_0080_2.md) callback function.

### -field pfnCreateVideoEncoderHeap

Pointer to a [**PFND3D12DDI_CREATEVIDEOENCODERHEAP_0080_2**](nc-d3d12umddi-pfnd3d12ddi_createvideoencoderheap_0080_2.md) callback function.

### -field pfnDestroyVideoEncoderHeap

Pointer to a [**PFND3D12DDI_DESTROYVIDEOENCODERHEAP_0080**](nc-d3d12umddi-pfnd3d12ddi_destroyvideoencoderheap_0080.md) callback function.

## -remarks

A client driver's [**PFND3D12DDI_FILLDDITTABLE**](nc-d3d12umddi-pfnd3d12ddi_fillddittable.md) callback function retrieves the **D3D12DDI_DEVICE_FUNCS_VIDEO_0082_0** structure.

## -see-also

[**PFND3D12DDI_FILLDDITTABLE**](nc-d3d12umddi-pfnd3d12ddi_fillddittable.md)
