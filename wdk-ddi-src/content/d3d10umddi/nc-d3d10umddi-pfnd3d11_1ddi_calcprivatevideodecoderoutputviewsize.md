---
UID: NC:d3d10umddi.PFND3D11_1DDI_CALCPRIVATEVIDEODECODEROUTPUTVIEWSIZE
title: PFND3D11_1DDI_CALCPRIVATEVIDEODECODEROUTPUTVIEWSIZE
author: windows-driver-content
description: Returns the number of bytes that the driver requires to store private data for the video decoder view state.
old-location: display\calcprivatevideodecoderoutputviewsize.htm
tech.root: display
ms.assetid: d8daa501-13cf-4fba-ab98-b1a2d0325ce1
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: CalcPrivateVideoDecoderOutputViewSize, CalcPrivateVideoDecoderOutputViewSize callback function [Display Devices], PFND3D11_1DDI_CALCPRIVATEVIDEODECODEROUTPUTVIEWSIZE, PFND3D11_1DDI_CALCPRIVATEVIDEODECODEROUTPUTVIEWSIZE callback, d3d10umddi/CalcPrivateVideoDecoderOutputViewSize, display.calcprivatevideodecoderoutputviewsize
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
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3D11_1DDI_CALCPRIVATEVIDEODECODEROUTPUTVIEWSIZE callback function


## -description


Returns the number of bytes that the driver requires to store private data for the video decoder view state.


## -parameters




### -param Arg1


### -param *








#### - hDevice [in]

A handle to the display device (graphics context).




#### - pView [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh406312">D3D11_1DDIARG_CREATEVIDEODECODEROUTPUTVIEW</a> structure that describes the video decoder view.


## -returns



The required number of bytes for the video decoder view state.




## -remarks



The runtime will validate the members of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh406312">D3D11_1DDIARG_CREATEVIDEODECODEROUTPUTVIEW</a> structure before it calls this function.

This function is not expected to fail.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh406312">D3D11_1DDIARG_CREATEVIDEODECODEROUTPUTVIEW</a>
 

 

