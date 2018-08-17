---
UID: NC:d3d10umddi.PFND3DWDDM2_0DDI_VIDEODECODERENABLEDOWNSAMPLING
title: PFND3DWDDM2_0DDI_VIDEODECODERENABLEDOWNSAMPLING
author: windows-driver-content
description: Indicates that decoder down-sampling will be used and that the driver should allocate the appropriate reference frames. Optional for Windows Display Driver Model (WDDM) 2.0 or later drivers.
old-location: display\videodecoderenabledownsampling.htm
ms.assetid: 0817C977-1113-4953-B60C-A69185443335
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: PFND3DWDDM2_0DDI_VIDEODECODERENABLEDOWNSAMPLING, PFND3DWDDM2_0DDI_VIDEODECODERENABLEDOWNSAMPLING callback, d3d10umddi/pfnVideoDecoderEnableDownsampling, display.videodecoderenabledownsampling, pfnVideoDecoderEnableDownsampling, pfnVideoDecoderEnableDownsampling callback function [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
-	pfnVideoDecoderEnableDownsampling
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3DWDDM2_0DDI_VIDEODECODERENABLEDOWNSAMPLING callback function


## -description


Indicates that decoder down-sampling will be used and that the driver should allocate the appropriate reference frames.  Optional for Windows Display Driver Model (WDDM) 2.0 or later drivers.


## -parameters




### -param hDevice [in]

 A handle to the display device (graphics context). The Direct3D runtime passed the user-mode driver this handle as the <b>hDevice</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff542931">D3DDDIARG_CREATEDEVICE</a> structure at device creation.


### -param hDecoder [in]

A handle to the decoder object.


### -param InputColorSpace [in]

A <a href="https://msdn.microsoft.com/library/windows/hardware/dn906320">D3DDDI_COLOR_SPACE_TYPE</a> value that indicates the color space information of the reference frame data.


### -param *pOutputDesc [in]

Indicates the resolution and the format of the output/display frames.  This is the destination resolution and format of the down-sample operation.



<div class="alert"><b>Note</b>  The decode profile member (<b>Guid</b>) of <b>pOutputDesc</b> can be ignored.</div>
<div> </div>

### -param OutputColorSpace [in]

A <a href="https://msdn.microsoft.com/library/windows/hardware/dn906320">D3DDDI_COLOR_SPACE_TYPE</a> value that indicates the color space information of the output/display frames.


### -param ReferenceFrameCount [in]

Indicates the number of reference frame used.


## -returns



If this callback function succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -remarks



This function can only be called once, prior to the first <a href="https://msdn.microsoft.com/library/windows/hardware/hh451697">VideoDecoderBeginFrame</a> call.





## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff542931">D3DDDIARG_CREATEDEVICE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn906320">D3DDDI_COLOR_SPACE_TYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451697">VideoDecoderBeginFrame</a>
 

 

