---
UID: NC:d3d10umddi.PFND3DWDDM2_0DDI_VIDEODECODERUPDATEDOWNSAMPLING
title: PFND3DWDDM2_0DDI_VIDEODECODERUPDATEDOWNSAMPLING
author: windows-driver-content
description: Updates the decoder down sampling parameters. Optional for Windows Display Driver Model (WDDM) 2.0, or later, drivers.
old-location: display\videodecoderupdatedownsampling.htm
old-project: display
ms.assetid: DBF0F62D-E6E5-4711-9A7A-19C88F62575D
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: PFND3DWDDM2_0DDI_VIDEODECODERUPDATEDOWNSAMPLING, d3d10umddi/pfnVideoDecoderUpdateDownsampling, display.videodecoderupdatedownsampling, pfnVideoDecoderUpdateDownsampling, pfnVideoDecoderUpdateDownsampling callback function [Display Devices]
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
-	pfnVideoDecoderUpdateDownsampling
product:
- Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3DWDDM2_0DDI_VIDEODECODERUPDATEDOWNSAMPLING callback


## -description


Updates the decoder down sampling parameters. Optional for Windows Display Driver Model (WDDM) 2.0, or later, drivers.


## -parameters




### -param hDevice [in]

 A handle to the display device (graphics context). The Direct3D runtime passed the user-mode driver this handle as the <b>hDevice</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff542931">D3DDDIARG_CREATEDEVICE</a> structure at device creation.


### -param hDecoder [in]

A handle to the video decoder object.


### -param *pOutputDesc [in]

Contains the resolution and the format of the output/display frames.  This is the destination resolution and format of the down sample operation.



<div class="alert"><b>Note</b>  The decode profile member (<b>Guid</b>) of <b>pOutputDesc</b> can be ignored.</div>
<div> </div>

### -param OutputColorSpace [in]

A <a href="https://msdn.microsoft.com/library/windows/hardware/dn906320">D3DDDI_COLOR_SPACE_TYPE</a> value that contains the color space information of the output/display frame data.


## -returns



If this callback function succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -remarks



This function can only be called after <a href="https://msdn.microsoft.com/library/windows/hardware/dn906376">VideoDecoderEnableDownsampling</a> has been called.



This function will only be called if the driver reports the <b>D3DWDDM2_0DDI_VIDEO_DECODER_CAPS_DOWN_SAMPLE_DYNAMIC</b> capability.





## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh450951">D3D11_1DDI_VIDEO_DECODER_DESC</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542931">D3DDDIARG_CREATEDEVICE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn906320">D3DDDI_COLOR_SPACE_TYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn906376">VideoDecoderEnableDownsampling</a>
 

 

