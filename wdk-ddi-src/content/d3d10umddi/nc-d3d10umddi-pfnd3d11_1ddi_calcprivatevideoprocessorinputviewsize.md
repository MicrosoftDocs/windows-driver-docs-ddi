---
UID: NC:d3d10umddi.PFND3D11_1DDI_CALCPRIVATEVIDEOPROCESSORINPUTVIEWSIZE
title: PFND3D11_1DDI_CALCPRIVATEVIDEOPROCESSORINPUTVIEWSIZE
author: windows-driver-content
description: Returns the number of bytes that the driver requires to store private data for the video processor input view state.
old-location: display\calcprivatevideoprocessorinputviewsize.htm
ms.assetid: 3cdf467c-41f5-4a44-b10a-41aeb76ca815
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: CalcPrivateVideoProcessorInputViewSize, CalcPrivateVideoProcessorInputViewSize callback function [Display Devices], PFND3D11_1DDI_CALCPRIVATEVIDEOPROCESSORINPUTVIEWSIZE, PFND3D11_1DDI_CALCPRIVATEVIDEOPROCESSORINPUTVIEWSIZE callback, d3d10umddi/CalcPrivateVideoProcessorInputViewSize, display.calcprivatevideoprocessorinputviewsize
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	CalcPrivateVideoProcessorInputViewSize
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D11_1DDI_CALCPRIVATEVIDEOPROCESSORINPUTVIEWSIZE callback function


## -description


Returns the number of bytes that the driver requires to store private data for the video processor input view state.


## -parameters




### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param *

*pView* [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh406318">D3D11_1DDIARG_CREATEVIDEOPROCESSORINPUTVIEW</a> structure that describes the video processor input view.


## -returns



The required number of bytes for the video processor input view state.




## -remarks



The runtime will validate the members of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh406318">D3D11_1DDIARG_CREATEVIDEOPROCESSORINPUTVIEW</a> structure before it calls this function. In particular, the runtime verifies that the specified view is supported as a video processor input format.

This function is not expected to fail.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh406318">D3D11_1DDIARG_CREATEVIDEOPROCESSORINPUTVIEW</a>
 

 

