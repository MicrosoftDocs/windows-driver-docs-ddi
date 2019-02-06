---
UID: NC:d3d10umddi.PFND3D11_1DDI_CALCPRIVATEVIDEOPROCESSORSIZE
title: PFND3D11_1DDI_CALCPRIVATEVIDEOPROCESSORSIZE (d3d10umddi.h)
description: Returns the number of bytes that the driver requires to store private data for the video processor state.
old-location: display\calcprivatevideoprocessorsize.htm
ms.assetid: a30d98b2-3d39-456a-8363-44ccc71e58ff
ms.date: 05/10/2018
ms.keywords: CalcPrivateVideoProcessorSize, CalcPrivateVideoProcessorSize callback function [Display Devices], PFND3D11_1DDI_CALCPRIVATEVIDEOPROCESSORSIZE, PFND3D11_1DDI_CALCPRIVATEVIDEOPROCESSORSIZE callback, d3d10umddi/CalcPrivateVideoProcessorSize, display.calcprivatevideoprocessorsize
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	D3d10umddi.h
api_name:
-	CalcPrivateVideoProcessorSize
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D11_1DDI_CALCPRIVATEVIDEOPROCESSORSIZE callback function


## -description


Returns the number of bytes that the driver requires to store private data for the video processor state.


## -parameters




### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param *

*pVideoProcessor* [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh406314">D3D11_1DDIARG_CREATEVIDEOPROCESSOR</a> structure that describes the video processor. 


## -returns



The required number of bytes for the video processor state.




## -remarks



This function is not expected to fail.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh406320">D3D11_1DDIARG_CREATEVIDEOPROCESSOROUTPUTVIEW</a>
 

 

