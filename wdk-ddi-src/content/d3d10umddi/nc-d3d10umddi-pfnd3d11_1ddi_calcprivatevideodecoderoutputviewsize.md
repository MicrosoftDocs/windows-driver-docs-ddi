---
UID: NC:d3d10umddi.PFND3D11_1DDI_CALCPRIVATEVIDEODECODEROUTPUTVIEWSIZE
title: PFND3D11_1DDI_CALCPRIVATEVIDEODECODEROUTPUTVIEWSIZE
author: windows-driver-content
description: Returns the number of bytes that the driver requires to store private data for the video decoder view state.
old-location: display\calcprivatevideodecoderoutputviewsize.htm
old-project: display
ms.assetid: d8daa501-13cf-4fba-ab98-b1a2d0325ce1
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: CalcPrivateVideoDecoderOutputViewSize, CalcPrivateVideoDecoderOutputViewSize callback function [Display Devices], PFND3D11_1DDI_CALCPRIVATEVIDEODECODEROUTPUTVIEWSIZE, d3d10umddi/CalcPrivateVideoDecoderOutputViewSize, display.calcprivatevideodecoderoutputviewsize
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
-	CalcPrivateVideoDecoderOutputViewSize
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3D11_1DDI_CALCPRIVATEVIDEODECODEROUTPUTVIEWSIZE callback


## -description


Returns the number of bytes that the driver requires to store private data for the video decoder view state.


## -prototype


````
PFND3D11_1DDI_CALCPRIVATEVIDEODECODEROUTPUTVIEWSIZE CalcPrivateVideoDecoderOutputViewSize;

SIZE_T APIENTRY* CalcPrivateVideoDecoderOutputViewSize(
  _In_       D3D10DDI_HDEVICE                           hDevice,
  _In_ const D3D11_1DDIARG_CREATEVIDEODECODEROUTPUTVIEW *pView
)
{ ... }
````


## -parameters




### -param D3D10DDI_HDEVICE


### -param *








#### - hDevice [in]

A handle to the display device (graphics context).




#### - pView [in]

A pointer to a <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddiarg_createvideodecoderoutputview.md">D3D11_1DDIARG_CREATEVIDEODECODEROUTPUTVIEW</a> structure that describes the video decoder view.


## -returns



The required number of bytes for the video decoder view state.




## -remarks



The runtime will validate the members of the <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddiarg_createvideodecoderoutputview.md">D3D11_1DDIARG_CREATEVIDEODECODEROUTPUTVIEW</a> structure before it calls this function.

This function is not expected to fail.




## -see-also

<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddiarg_createvideodecoderoutputview.md">D3D11_1DDIARG_CREATEVIDEODECODEROUTPUTVIEW</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D11_1DDI_CALCPRIVATEVIDEODECODEROUTPUTVIEWSIZE callback function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

