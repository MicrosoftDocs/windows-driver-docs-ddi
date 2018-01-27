---
UID: NC:d3d10umddi.PFND3D11_1DDI_DESTROYVIDEOPROCESSOR
title: PFND3D11_1DDI_DESTROYVIDEOPROCESSOR
author: windows-driver-content
description: Releases resources for the video processor object that were created through a call to the CreateVideoProcessor function.
old-location: display\destroyvideoprocessor1.htm
old-project: display
ms.assetid: a04776ba-bc80-498e-b25d-511ecb03fb63
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.destroyvideoprocessor1, pfnDestroyVideoProcessor callback function [Display Devices], pfnDestroyVideoProcessor, PFND3D11_1DDI_DESTROYVIDEOPROCESSOR, PFND3D11_1DDI_DESTROYVIDEOPROCESSOR, d3d10umddi/pfnDestroyVideoProcessor, display.pfndestroyvideoprocessor1
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
-	pfnDestroyVideoProcessor
product: Windows
targetos: Windows
req.typenames: *PSETRESULT_INFO, SETRESULT_INFO
---

# PFND3D11_1DDI_DESTROYVIDEOPROCESSOR callback


## -description


Releases resources for the video processor object that were created through a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessor.md">CreateVideoProcessor</a> function.



## -prototype


````
PFND3D11_1DDI_DESTROYVIDEOPROCESSOR pfnDestroyVideoProcessor;

VOID APIENTRY* pfnDestroyVideoProcessor(
  _In_ D3D10DDI_HDEVICE           hDevice,
  _In_ D3D11_1DDI_HVIDEOPROCESSOR hProcessor
)
{ ... }
````


## -parameters




### -param D3D10DDI_HDEVICE



### -param D3D11_1DDI_HVIDEOPROCESSOR






#### - hDevice [in]

A handle to the display device (graphics context).




#### - hProcessor [in]

A handle to the driver's private data for the video processor object. This handle was created by the Direct3D runtime and passed to the driver in the call to <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessor.md">CreateVideoProcessor</a>.


## -returns


This callback function does not return a value.



## -see-also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessor.md">CreateVideoProcessor</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D11_1DDI_DESTROYVIDEOPROCESSOR callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

