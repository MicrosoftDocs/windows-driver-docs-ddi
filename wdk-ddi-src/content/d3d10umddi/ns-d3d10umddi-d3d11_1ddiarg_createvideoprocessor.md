---
UID: NS:d3d10umddi.D3D11_1DDIARG_CREATEVIDEOPROCESSOR
title: D3D11_1DDIARG_CREATEVIDEOPROCESSOR (d3d10umddi.h)
description: Specifies the attributes of a video processor object.
old-location: display\d3d11_1ddiarg_createvideoprocessor.htm
ms.assetid: 957cfebe-4cd9-4a35-822e-ebde4cd9e84c
ms.date: 05/10/2018
ms.keywords: D3D11_1DDIARG_CREATEVIDEOPROCESSOR, D3D11_1DDIARG_CREATEVIDEOPROCESSOR structure [Display Devices], d3d10umddi/D3D11_1DDIARG_CREATEVIDEOPROCESSOR, display.d3d11_1ddiarg_createvideoprocessor
ms.topic: struct
f1_keywords:
 - "d3d10umddi/D3D11_1DDIARG_CREATEVIDEOPROCESSOR"
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
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
- HeaderDef
api_location:
- D3d10umddi.h
api_name:
- D3D11_1DDIARG_CREATEVIDEOPROCESSOR
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D11_1DDIARG_CREATEVIDEOPROCESSOR
---

# D3D11_1DDIARG_CREATEVIDEOPROCESSOR structure


## -description


Specifies the attributes of a video processor object.


## -struct-fields




### -field hVideoProcessorEnum

A handle to a video processor enumeration object that was created through a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessorenum">CreateVideoProcessorEnum</a> function. 


### -field RateConversionCapsIndex

Specifies the frame-rate conversion capabilities for the video processor. The value is a zero-based index that corresponds to the <i>RateConversionIndex</i> parameter of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_getvideoprocessorrateconversioncaps">GetVideoProcessorRateConversionCaps</a> method. 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessorenum">CreateVideoProcessorEnum</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_getvideoprocessorrateconversioncaps">GetVideoProcessorRateConversionCaps</a>
 

 

