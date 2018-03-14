---
UID: NC:d3d10umddi.PFND3D11_1DDI_CALCPRIVATEVIDEOPROCESSORINPUTVIEWSIZE
title: PFND3D11_1DDI_CALCPRIVATEVIDEOPROCESSORINPUTVIEWSIZE
author: windows-driver-content
description: Returns the number of bytes that the driver requires to store private data for the video processor input view state.
old-location: display\calcprivatevideoprocessorinputviewsize.htm
old-project: display
ms.assetid: 3cdf467c-41f5-4a44-b10a-41aeb76ca815
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: CalcPrivateVideoProcessorInputViewSize, CalcPrivateVideoProcessorInputViewSize callback function [Display Devices], PFND3D11_1DDI_CALCPRIVATEVIDEOPROCESSORINPUTVIEWSIZE, d3d10umddi/CalcPrivateVideoProcessorInputViewSize, display.calcprivatevideoprocessorinputviewsize
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
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3D11_1DDI_CALCPRIVATEVIDEOPROCESSORINPUTVIEWSIZE callback


## -description


Returns the number of bytes that the driver requires to store private data for the video processor input view state.


## -prototype


````
PFND3D11_1DDI_CALCPRIVATEVIDEOPROCESSORINPUTVIEWSIZE CalcPrivateVideoProcessorInputViewSize;

SIZE_T APIENTRY* CalcPrivateVideoProcessorInputViewSize(
  _In_       D3D10DDI_HDEVICE                            hDevice,
  _In_ const D3D11_1DDIARG_CREATEVIDEOPROCESSORINPUTVIEW *pView
)
{ ... }
````


## -parameters




### -param D3D10DDI_HDEVICE


### -param *








#### - hDevice [in]

A handle to the display device (graphics context).




#### - pView [in]

A pointer to a <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddiarg_createvideoprocessorinputview.md">D3D11_1DDIARG_CREATEVIDEOPROCESSORINPUTVIEW</a> structure that describes the video processor input view.


## -returns



The required number of bytes for the video processor input view state.




## -remarks



The runtime will validate the members of the <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddiarg_createvideoprocessorinputview.md">D3D11_1DDIARG_CREATEVIDEOPROCESSORINPUTVIEW</a> structure before it calls this function. In particular, the runtime verifies that the specified view is supported as a video processor input format.

This function is not expected to fail.




## -see-also

<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddiarg_createvideoprocessorinputview.md">D3D11_1DDIARG_CREATEVIDEOPROCESSORINPUTVIEW</a>



 

 


