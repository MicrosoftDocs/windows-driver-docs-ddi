---
UID: NC:d3d10umddi.PFND3D11_1DDI_GETVIDEODECODERCONFIG
title: PFND3D11_1DDI_GETVIDEODECODERCONFIG
author: windows-driver-content
description: Queries the video decoder configuration for a specified video operation.
old-location: display\getvideodecoderconfig.htm
tech.root: display
ms.assetid: e13cb42b-258e-4fa6-8dc0-8983b118af3c
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: PFND3D11_1DDI_GETVIDEODECODERCONFIG, PFND3D11_1DDI_GETVIDEODECODERCONFIG callback, d3d10umddi/pfnGetVideoDecoderConfig, display.getvideodecoderconfig, pfnGetVideoDecoderConfig, pfnGetVideoDecoderConfig callback function [Display Devices]
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
-	pfnGetVideoDecoderConfig
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3D11_1DDI_GETVIDEODECODERCONFIG callback function


## -description


Queries the video decoder configuration for a specified video operation.


## -parameters




### -param Arg1


### -param *








### -param Arg2


#### - Index [in]

The zero-based index of the video decoder configuration that is used for the specified operation. The display miniport driver specifies the maximum number of video decoder configurations that are required for the operation through a call to its <a href="https://msdn.microsoft.com/library/windows/hardware/hh451668">GetVideoDecoderConfigCount</a> function.


#### - hDevice [in]

A handle to the display device (graphics context).




#### - pConfig [out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh450947">D3D11_1DDI_VIDEO_DECODER_CONFIG</a> structure that describes the video decoder configuration.


#### - pDecodeDesc [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh450951">D3D11_1DDI_VIDEO_DECODER_DESC</a> structure that specifies the video decoder operation.


## -returns



This callback function does not return a value.




## -remarks



The Microsoft Direct3D runtime verifies that the <i>pDecodeDesc</i> and <i>Index</i> parameter data is valid before it calls the <b>GetVideoDecoderConfig</b> function.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh450947">D3D11_1DDI_VIDEO_DECODER_CONFIG</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh450951">D3D11_1DDI_VIDEO_DECODER_DESC</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451668">GetVideoDecoderConfigCount</a>
 

 

