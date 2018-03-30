---
UID: NC:d3d10umddi.PFND3D11_1DDI_GETVIDEODECODERBUFFERTYPECOUNT
title: PFND3D11_1DDI_GETVIDEODECODERBUFFERTYPECOUNT
author: windows-driver-content
description: Queries the number of buffer types that the display miniport driver requires to perform a specified decode operation.
old-location: display\getvideodecoderbuffertypecount.htm
old-project: display
ms.assetid: 3528ac03-55cf-4e02-ae42-69b736684147
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: PFND3D11_1DDI_GETVIDEODECODERBUFFERTYPECOUNT, d3d10umddi/pfnGetVideoDecoderBufferTypeCount, display.getvideodecoderbuffertypecount, pfnGetVideoDecoderBufferTypeCount, pfnGetVideoDecoderBufferTypeCount callback function [Display Devices]
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
-	pfnGetVideoDecoderBufferTypeCount
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3D11_1DDI_GETVIDEODECODERBUFFERTYPECOUNT callback


## -description


Queries the number of buffer types that the display miniport driver requires to perform a specified decode operation.


## -parameters




### -param Arg1


### -param *








#### - hDevice [in]

A handle to the display device (graphics context).




#### - pBufferTypeCount [out]

A pointer to a UINT value that specifies the maximum number of buffer types that the driver supports for the specified video decoder operation.


#### - pDecodeDesc [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh450951">D3D11_1DDI_VIDEO_DECODER_DESC</a> structure that specifies the video decoder operation.


## -returns



This callback function does not return a value.




## -remarks



The Microsoft Direct3D runtime verifies that the <i>pDecodeDesc</i>  parameter data is valid before it calls the <b>GetVideoDecoderBufferTypeCount</b> function.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh450951">D3D11_1DDI_VIDEO_DECODER_DESC</a>
 

 

