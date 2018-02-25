---
UID: NC:d3d10umddi.PFND3D11_1DDI_CALCPRIVATEVIDEOPROCESSORINPUTVIEWSIZE
title: PFND3D11_1DDI_CALCPRIVATEVIDEOPROCESSORINPUTVIEWSIZE
author: windows-driver-content
description: Returns the number of bytes that the driver requires to store private data for the video processor input view state.
old-location: display\calcprivatevideoprocessorinputviewsize.htm
old-project: display
ms.assetid: 3cdf467c-41f5-4a44-b10a-41aeb76ca815
ms.author: windowsdriverdev
ms.date: 2/22/2018
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	D3d10umddi.h
apiname:
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



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D11_1DDI_CALCPRIVATEVIDEOPROCESSORINPUTVIEWSIZE callback function%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

