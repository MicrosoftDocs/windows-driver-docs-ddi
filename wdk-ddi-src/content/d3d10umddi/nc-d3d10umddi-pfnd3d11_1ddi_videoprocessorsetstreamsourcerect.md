---
UID: NC:d3d10umddi.PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMSOURCERECT
title: PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMSOURCERECT
author: windows-driver-content
description: Sets the source rectangle for an input stream on the video processor.
old-location: display\videoprocessorsetstreamsourcerect.htm
old-project: display
ms.assetid: 78d62117-260a-46ab-9daa-ee9dcfc7fc1f
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMSOURCERECT, d3d10umddi/pfnVideoProcessorSetStreamSourceRect, display.videoprocessorsetstreamsourcerect, pfnVideoProcessorSetStreamSourceRect, pfnVideoProcessorSetStreamSourceRect callback function [Display Devices]
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
-	pfnVideoProcessorSetStreamSourceRect
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMSOURCERECT callback


## -description


Sets the source rectangle for an input stream on the video processor.




## -prototype


````
PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMSOURCERECT pfnVideoProcessorSetStreamSourceRect;

VOID APIENTRY* pfnVideoProcessorSetStreamSourceRect(
  _In_       D3D10DDI_HDEVICE           hDevice,
  _In_       D3D11_1DDI_HVIDEOPROCESSOR hVideoProcessor,
  _In_       UINT                       StreamIndex,
  _In_       BOOL                       Enable,
  _In_ const RECT                       *pSourceRect
)
{ ... }
````


## -parameters




### -param D3D10DDI_HDEVICE


### -param D3D11_1DDI_HVIDEOPROCESSOR


### -param UINT


### -param BOOL


### -param *








#### - hDevice [in]

A handle to the display device (graphics context).




#### - hVideoProcessor [in]

A handle to the video processor object that was created through a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessor.md">CreateVideoProcessor</a> function. 




#### - StreamIndex [in]

The zero-based index of the input stream.


#### - Enable [in]

If <b>TRUE</b>, the specified source rectangle must be applied to the input stream.



If <b>FALSE</b>, no source rectangle is applied to the input stream.




#### - pSourceRect [in]

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

<a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessor.md">CreateVideoProcessor</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMSOURCERECT callback function%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

