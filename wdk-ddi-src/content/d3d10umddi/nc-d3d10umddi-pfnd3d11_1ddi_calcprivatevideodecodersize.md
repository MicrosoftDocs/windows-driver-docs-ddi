---
UID: NC:d3d10umddi.PFND3D11_1DDI_CALCPRIVATEVIDEODECODERSIZE
title: PFND3D11_1DDI_CALCPRIVATEVIDEODECODERSIZE
author: windows-driver-content
description: Returns the number of bytes that the driver requires to store private data for the video decoder state.
old-location: display\calcprivatevideodecodersize.htm
old-project: display
ms.assetid: a878cba1-589e-4932-9d2b-1abab417660f
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: display.calcprivatevideodecodersize, CalcPrivateVideoDecoderSize callback function [Display Devices], CalcPrivateVideoDecoderSize, FND3D11_1DDI_CALCPRIVATEVIDEODECODERSIZE, FND3D11_1DDI_CALCPRIVATEVIDEODECODERSIZE, d3d10umddi/CalcPrivateVideoDecoderSize
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
-	CalcPrivateVideoDecoderSize
product: Windows
targetos: Windows
req.typenames: "*PSETRESULT_INFO, SETRESULT_INFO"
---

# PFND3D11_1DDI_CALCPRIVATEVIDEODECODERSIZE callback


## -description


Returns the number of bytes that the driver requires to store private data for the video decoder state.


## -prototype


````
FND3D11_1DDI_CALCPRIVATEVIDEODECODERSIZE CalcPrivateVideoDecoderSize;

SIZE_T APIENTRY* CalcPrivateVideoDecoderSize(
  _In_       D3D10DDI_HDEVICE                 hDevice,
  _In_ const D3D11_1DDIARG_CREATEVIDEODECODER *pDecoder
)
{ ... }
````


## -parameters




### -param D3D10DDI_HDEVICE


### -param *








#### - hDevice [in]

A handle to the display device (graphics context).




#### - pDecoder [in]

A pointer to a <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddiarg_createvideodecoder.md">D3D11_1DDIARG_CREATEVIDEODECODER</a> structure that describes the video decoder.


## -returns



The required number of bytes for the video decoder state.




## -remarks



The runtime will validate the members of the <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddiarg_createvideodecoder.md">D3D11_1DDIARG_CREATEVIDEODECODER</a> structure before it calls this function.

This function is not expected to fail.




## -see-also

<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddiarg_createvideodecoder.md">D3D11_1DDIARG_CREATEVIDEODECODER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D11_1DDI_CALCPRIVATEVIDEODECODERSIZE callback function%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

