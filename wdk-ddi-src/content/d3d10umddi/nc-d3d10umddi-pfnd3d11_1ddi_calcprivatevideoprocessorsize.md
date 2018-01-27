---
UID: NC:d3d10umddi.PFND3D11_1DDI_CALCPRIVATEVIDEOPROCESSORSIZE
title: PFND3D11_1DDI_CALCPRIVATEVIDEOPROCESSORSIZE
author: windows-driver-content
description: Returns the number of bytes that the driver requires to store private data for the video processor state.
old-location: display\calcprivatevideoprocessorsize.htm
old-project: display
ms.assetid: a30d98b2-3d39-456a-8363-44ccc71e58ff
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.calcprivatevideoprocessorsize, CalcPrivateVideoProcessorSize callback function [Display Devices], CalcPrivateVideoProcessorSize, PFND3D11_1DDI_CALCPRIVATEVIDEOPROCESSORSIZE, PFND3D11_1DDI_CALCPRIVATEVIDEOPROCESSORSIZE, d3d10umddi/CalcPrivateVideoProcessorSize
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
-	CalcPrivateVideoProcessorSize
product: Windows
targetos: Windows
req.typenames: *PSETRESULT_INFO, SETRESULT_INFO
---

# PFND3D11_1DDI_CALCPRIVATEVIDEOPROCESSORSIZE callback


## -description


Returns the number of bytes that the driver requires to store private data for the video processor state.


## -prototype


````
PFND3D11_1DDI_CALCPRIVATEVIDEOPROCESSORSIZE CalcPrivateVideoProcessorSize;

SIZE_T APIENTRY* CalcPrivateVideoProcessorSize(
  _In_       D3D10DDI_HDEVICE                   hDevice,
  _In_ const D3D11_1DDIARG_CREATEVIDEOPROCESSOR *pVideoProcessor
)
{ ... }
````


## -parameters




### -param D3D10DDI_HDEVICE



### -param *






#### - pVideoProcessor [in]

A pointer to a <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddiarg_createvideoprocessor.md">D3D11_1DDIARG_CREATEVIDEOPROCESSOR</a> structure that describes the video processor. 


#### - hDevice [in]

A handle to the display device (graphics context).




## -returns


The required number of bytes for the video processor state.



## -remarks


This function is not expected to fail.



## -see-also

<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddiarg_createvideoprocessoroutputview.md">D3D11_1DDIARG_CREATEVIDEOPROCESSOROUTPUTVIEW</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D11_1DDI_CALCPRIVATEVIDEOPROCESSORSIZE callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

