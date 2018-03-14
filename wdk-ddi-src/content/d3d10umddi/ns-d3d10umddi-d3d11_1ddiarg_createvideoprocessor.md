---
UID: NS:d3d10umddi.D3D11_1DDIARG_CREATEVIDEOPROCESSOR
title: D3D11_1DDIARG_CREATEVIDEOPROCESSOR
author: windows-driver-content
description: Specifies the attributes of a video processor object.
old-location: display\d3d11_1ddiarg_createvideoprocessor.htm
old-project: display
ms.assetid: 957cfebe-4cd9-4a35-822e-ebde4cd9e84c
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3D11_1DDIARG_CREATEVIDEOPROCESSOR, D3D11_1DDIARG_CREATEVIDEOPROCESSOR structure [Display Devices], d3d10umddi/D3D11_1DDIARG_CREATEVIDEOPROCESSOR, display.d3d11_1ddiarg_createvideoprocessor
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	D3d10umddi.h
api_name:
-	D3D11_1DDIARG_CREATEVIDEOPROCESSOR
product: Windows
targetos: Windows
req.typenames: D3D11_1DDIARG_CREATEVIDEOPROCESSOR
---

# D3D11_1DDIARG_CREATEVIDEOPROCESSOR structure


## -description


Specifies the attributes of a video processor object.


## -syntax


````
typedef struct D3D11_1DDIARG_CREATEVIDEOPROCESSOR {
  D3D11_1DDI_HVIDEOPROCESSORENUM hVideoProcessorEnum;
  UINT                           RateConversionCapsIndex;
} D3D11_1DDIARG_CREATEVIDEOPROCESSOR;
````


## -struct-fields




### -field hVideoProcessorEnum

A handle to a video processor enumeration object that was created through a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessorenum.md">CreateVideoProcessorEnum</a> function. 


### -field RateConversionCapsIndex

Specifies the frame-rate conversion capabilities for the video processor. The value is a zero-based index that corresponds to the <i>RateConversionIndex</i> parameter of the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_getvideoprocessorrateconversioncaps.md">GetVideoProcessorRateConversionCaps</a> method. 


## -see-also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_getvideoprocessorrateconversioncaps.md">GetVideoProcessorRateConversionCaps</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessorenum.md">CreateVideoProcessorEnum</a>



 

 


