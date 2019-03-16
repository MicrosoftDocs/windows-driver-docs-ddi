---
UID: NC:d3d10umddi.PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMSOURCERECT
title: PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMSOURCERECT (d3d10umddi.h)
description: Sets the source rectangle for an input stream on the video processor.
old-location: display\videoprocessorsetstreamsourcerect.htm
ms.assetid: 78d62117-260a-46ab-9daa-ee9dcfc7fc1f
ms.date: 05/10/2018
ms.keywords: PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMSOURCERECT, PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMSOURCERECT callback, d3d10umddi/pfnVideoProcessorSetStreamSourceRect, display.videoprocessorsetstreamsourcerect, pfnVideoProcessorSetStreamSourceRect, pfnVideoProcessorSetStreamSourceRect callback function [Display Devices]
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- D3d10umddi.h
api_name:
- pfnVideoProcessorSetStreamSourceRect
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMSOURCERECT callback function


## -description


Sets the source rectangle for an input stream on the video processor.




## -parameters




### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*hVideoProcessor* [in]

A handle to the video processor object that was created through a call to the <a href="https://msdn.microsoft.com/741045a2-0a91-490a-907d-5f4900a4a0ae">CreateVideoProcessor</a> function.

### -param Arg3

*StreamIndex* [in]

The zero-based index of the input stream.

### -param Arg4

*Enable* [in]

If <b>TRUE</b>, the specified source rectangle must be applied to the input stream.



If <b>FALSE</b>, no source rectangle is applied to the input stream.


### -param *

*pSourceRect* [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a> structure that specifies the source rectangle.

<div class="alert"><b>Note</b>  If the <i>Enable</i> parameter is FALSE, this parameter is ignored.
</div>
<div> </div>

## -returns



This callback function does not return a value.




## -remarks



The source rectangle is the portion of the input surface from which the video processor performs a bit-block transfer (bitblt) to the destination surface. The source rectangle is given in pixel coordinates, relative to the input surface.



If the <b>VideoProcessorSetStreamSourceRect</b> function is never called, or if the <i>Enable</i> parameter is FALSE, the video processor reads from the entire input surface.






## -see-also




<a href="https://msdn.microsoft.com/741045a2-0a91-490a-907d-5f4900a4a0ae">CreateVideoProcessor</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a>
 

 

