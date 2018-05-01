---
UID: NC:d3d10umddi.PFND3D11_1DDI_VIDEOPROCESSORSETOUTPUTTARGETRECT
title: PFND3D11_1DDI_VIDEOPROCESSORSETOUTPUTTARGETRECT
author: windows-driver-content
description: Sets the target rectangle for the video processor.
old-location: display\videoprocessorsetoutputtargetrect.htm
old-project: display
ms.assetid: ac1ba2e0-a289-4dee-b739-d3c1ad0970e1
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: PFND3D11_1DDI_VIDEOPROCESSORSETOUTPUTTARGETRECT, PFND3D11_1DDI_VIDEOPROCESSORSETOUTPUTTARGETRECT callback, d3d10umddi/pfnVideoProcessorSetOutputTargetRect, display.videoprocessorsetoutputtargetrect, pfnVideoProcessorSetOutputTargetRect, pfnVideoProcessorSetOutputTargetRect callback function [Display Devices]
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
-	pfnVideoProcessorSetOutputTargetRect
product: Windows
targetos: Windows
req.typenames: 
---

# PFND3D11_1DDI_VIDEOPROCESSORSETOUTPUTTARGETRECT callback function


## -description


Sets the target rectangle for the video processor.




## -parameters




### -param Arg1


### -param Arg2


### -param Arg3


### -param *








#### - Enable [in]

If <b>TRUE</b>, the target rectangle specified by the <i>pOutputRect</i> parameter should be used by the video processor.


#### - hDevice [in]

A handle to the display device (graphics context).




#### - hVideoProcessor [in]

A handle to the video processor object that was created through a call to the <a href="https://msdn.microsoft.com/741045a2-0a91-490a-907d-5f4900a4a0ae">CreateVideoProcessor</a> function. 




#### - pOutputRect [in]

A  pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a> structure that specifies the target rectangle. 

<div class="alert"><b>Note</b>  If the <i>Enable</i> parameter is FALSE, this parameter is ignored.

</div>
<div> </div>

## -returns



This callback function does not return a value.




## -remarks



The target rectangle is the area within the destination surface where the output will be drawn. The target rectangle is given in pixel coordinates, relative to the destination surface.



If this function is never called, or if the <i>Enable</i> parameter is FALSE, the video processor writes to the entire destination surface.






## -see-also




<a href="https://msdn.microsoft.com/741045a2-0a91-490a-907d-5f4900a4a0ae">CreateVideoProcessor</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a>
 

 

