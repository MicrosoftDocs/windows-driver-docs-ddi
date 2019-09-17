---
UID: NC:d3d10umddi.PFND3D11_1DDI_CALCPRIVATEVIDEOPROCESSORENUMSIZE
title: PFND3D11_1DDI_CALCPRIVATEVIDEOPROCESSORENUMSIZE (d3d10umddi.h)
description: Returns the number of bytes that the driver requires to store private data for the video processor enumeration state.
old-location: display\calcprivatevideoprocessorenumsize.htm
ms.assetid: d468c892-6635-40a5-ad52-cbcc86555419
ms.date: 05/10/2018
ms.keywords: CalcPrivateVideoProcessorEnumSize, CalcPrivateVideoProcessorEnumSize callback function [Display Devices], PFND3D11_1DDI_CALCPRIVATEVIDEOPROCESSORENUMSIZE, PFND3D11_1DDI_CALCPRIVATEVIDEOPROCESSORENUMSIZE callback, d3d10umddi/CalcPrivateVideoProcessorEnumSize, display.calcprivatevideoprocessorenumsize
ms.topic: callback
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
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - "d3d10umddi/CalcPrivateVideoProcessorEnumSize"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3d10umddi.h
api_name:
 - CalcPrivateVideoProcessorEnumSize
product:
 - Windows
---

# PFND3D11_1DDI_CALCPRIVATEVIDEOPROCESSORENUMSIZE callback function

## -description

Returns the number of bytes that the driver requires to store private data for the video processor enumeration state.

## -parameters

### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*pProcessorEnum* [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3d11_1ddiarg_createvideoprocessorenum">D3D11_1DDIARG_CREATEVIDEOPROCESSORENUM</a> structure that describes the video processor enumeration object that was created through the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessorenum">CreateVideoProcessorEnum</a> function.

## -returns

The required number of bytes for the video processor enumeration state.

## -remarks

This function is not expected to fail.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessorenum">CreateVideoProcessorEnum</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3d11_1ddiarg_createvideoprocessorenum">D3D11_1DDIARG_CREATEVIDEOPROCESSORENUM</a>

