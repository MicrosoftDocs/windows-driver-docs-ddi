---
UID: NC:d3d10umddi.PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMROTATION
title: PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMROTATION (d3d10umddi.h)
description: Enables or disables rotation on an input stream of the video processor.
old-location: display\videoprocessorsetstreamrotation.htm
ms.assetid: 9b7d91e0-4913-404c-b7d7-eb63e9919919
ms.date: 05/10/2018
ms.keywords: PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMROTATION, PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMROTATION callback, d3d10umddi/pfnVideoProcessorSetStreamRotation, display.videoprocessorsetstreamrotation, pfnVideoProcessorSetStreamRotation, pfnVideoProcessorSetStreamRotation callback function [Display Devices]
ms.topic: callback
f1_keywords:
 - "d3d10umddi/pfnVideoProcessorSetStreamRotation"
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
- UserDefined
api_location:
- D3d10umddi.h
api_name:
- pfnVideoProcessorSetStreamRotation
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMROTATION callback function


## -description


Enables or disables rotation on an input stream of the video processor.


## -parameters




### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*hVideoProcessor* [in]

A handle to the video processor object that was created through a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessor">CreateVideoProcessor</a> function.

### -param Arg3

*StreamIndex* [in]

The zero-based index of the input stream.

### -param Arg4

Rotation [in]

The clockwise degrees of rotation as specified by a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ne-d3d10umddi-d3d11_1ddi_video_processor_rotation">D3D11_1DDI_VIDEO_PROCESSOR_ROTATION</a> enumeration value.

### -param Arg5

Enable [in]

If <b>TRUE</b>, rotation is enabled on the input stream. Otherwise, rotation is disabled on the input stream.






## -remarks



The stream source rectangle will be specified in the pre-rotation coordinates (typically landscape) and the stream destination rectangle will be specified in the post-rotation coordinates (typically portrait).   

The application must update the stream destination rectangle correctly when using a rotation value other than 0 or 180 degrees.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessor">CreateVideoProcessor</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ne-d3d10umddi-d3d11_1ddi_video_processor_rotation">D3D11_1DDI_VIDEO_PROCESSOR_ROTATION</a>
 

 

