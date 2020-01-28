---
UID: NC:d3d10umddi.PFND3D11_1DDI_CALCPRIVATEVIDEOPROCESSOROUTPUTVIEWSIZE
title: PFND3D11_1DDI_CALCPRIVATEVIDEOPROCESSOROUTPUTVIEWSIZE (d3d10umddi.h)
description: Returns the number of bytes that the driver requires to store private data for the video processor output view state.
old-location: display\calcprivatevideoprocessoroutputviewsize.htm
ms.assetid: 2cf09e91-e83b-47ae-bf34-037dc01d7e80
ms.date: 05/10/2018
ms.keywords: CalcPrivateVideoProcessorOutputViewSize, CalcPrivateVideoProcessorOutputViewSize callback function [Display Devices], PFND3D11_1DDI_CALCPRIVATEVIDEOPROCESSOROUTPUTVIEWSIZE, PFND3D11_1DDI_CALCPRIVATEVIDEOPROCESSOROUTPUTVIEWSIZE callback, d3d10umddi/CalcPrivateVideoProcessorOutputViewSize, display.calcprivatevideoprocessoroutputviewsize
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
 - "d3d10umddi/CalcPrivateVideoProcessorOutputViewSize"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3d10umddi.h
api_name:
 - CalcPrivateVideoProcessorOutputViewSize
product:
 - Windows
---

# PFND3D11_1DDI_CALCPRIVATEVIDEOPROCESSOROUTPUTVIEWSIZE callback function

## -description

Returns the number of bytes that the driver requires to store private data for the video processor output view state.

## -parameters

### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*pView* [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddiarg_createvideoprocessoroutputview">D3D11_1DDIARG_CREATEVIDEOPROCESSOROUTPUTVIEW</a> structure that describes the video processor output view.

## -returns

The required number of bytes for the video processor output view state.

## -remarks

The runtime will validate the members of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddiarg_createvideoprocessoroutputview">D3D11_1DDIARG_CREATEVIDEOPROCESSOROUTPUTVIEW</a> structure before it calls this function. In particular, the runtime verifies that the specified view is supported as a video processor output format and the <b>D3D11_DDI_BIND_RENDER_TARGET</b> flag is set.

This function is not expected to fail.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddiarg_createvideoprocessoroutputview">D3D11_1DDIARG_CREATEVIDEOPROCESSOROUTPUTVIEW</a>

