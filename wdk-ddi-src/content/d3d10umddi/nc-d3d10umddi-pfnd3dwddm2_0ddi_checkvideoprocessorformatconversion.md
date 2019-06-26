---
UID: NC:d3d10umddi.PFND3DWDDM2_0DDI_CHECKVIDEOPROCESSORFORMATCONVERSION
title: PFND3DWDDM2_0DDI_CHECKVIDEOPROCESSORFORMATCONVERSION (d3d10umddi.h)
description: Indicates whether the driver supports a specific format/color-space conversion combination. This function must be implemented by Windows Display Driver Model (WDDM) 2.0 or later drivers.
old-location: display\checkvideoprocessorformatconversion.htm
ms.assetid: 70A741CC-9D1B-4ECC-BB3A-6ACF6893691A
ms.date: 05/10/2018
ms.keywords: CheckVideoProcessorFormatConversion, CheckVideoProcessorFormatConversion callback function [Display Devices], PFND3DWDDM2_0DDI_CHECKVIDEOPROCESSORFORMATCONVERSION, PFND3DWDDM2_0DDI_CHECKVIDEOPROCESSORFORMATCONVERSION callback, d3d10umddi/CheckVideoProcessorFormatConversion, display.checkvideoprocessorformatconversion
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
- CheckVideoProcessorFormatConversion
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3DWDDM2_0DDI_CHECKVIDEOPROCESSORFORMATCONVERSION callback function


## -description


Indicates whether the driver supports a specific format/color-space conversion combination. This function must be implemented by Windows Display Driver Model (WDDM) 2.0 or later drivers.


## -parameters




### -param hDevice [in]

A handle to the display device (graphics context). The Direct3D runtime passed the user-mode driver this handle as the <b>hDevice</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_d3dddiarg_createdevice">D3DDDIARG_CREATEDEVICE</a> structure at device creation.


### -param hProcessorEnum [in]

A handle to a video processor enumeration object that was created through a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessorenum">CreateVideoProcessorEnum</a> function.


### -param *pConversion [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3dwddm2_0ddi_check_video_processor_format_conversion">D3DWDDM2_0DDI_CHECK_VIDEO_PROCESSOR_FORMAT_CONVERSION</a> structure that contains the input and output format/color-space combination.


## -returns



This callback function does not return a value.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessorenum">CreateVideoProcessorEnum</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_d3dddiarg_createdevice">D3DDDIARG_CREATEDEVICE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3dwddm2_0ddi_check_video_processor_format_conversion">D3DWDDM2_0DDI_CHECK_VIDEO_PROCESSOR_FORMAT_CONVERSION</a>
 

 

