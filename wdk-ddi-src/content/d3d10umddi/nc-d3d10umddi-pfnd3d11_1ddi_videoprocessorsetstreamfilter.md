---
UID: NC:d3d10umddi.PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMFILTER
title: PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMFILTER
author: windows-driver-content
description: Enables or disables an image filter for an input stream on the video processor.
old-location: display\videoprocessorsetstreamfilter.htm
old-project: display
ms.assetid: e44e5e4a-20e1-4327-b64c-5806d1bb2ece
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMFILTER, d3d10umddi/pfnVideoProcessorSetStreamFilter, display.videoprocessorsetstreamfilter, pfnVideoProcessorSetStreamFilter, pfnVideoProcessorSetStreamFilter callback function [Display Devices]
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
-	pfnVideoProcessorSetStreamFilter
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMFILTER callback


## -description


Enables or disables an image filter for an input stream on the video processor.




## -prototype


````
PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMFILTER pfnVideoProcessorSetStreamFilter;

VOID APIENTRY* pfnVideoProcessorSetStreamFilter(
  _In_ D3D10DDI_HDEVICE                  hDevice,
  _In_ D3D11_1DDI_HVIDEOPROCESSOR        hVideoProcessor,
  _In_ UINT                              StreamIndex,
  _In_ D3D11_1DDI_VIDEO_PROCESSOR_FILTER Filter,
  _In_ BOOL                              Enable,
  _In_ int                               Level
)
{ ... }
````


## -parameters




### -param D3D10DDI_HDEVICE


### -param D3D11_1DDI_HVIDEOPROCESSOR


### -param UINT


### -param D3D11_1DDI_VIDEO_PROCESSOR_FILTER


### -param BOOL


### -param int








#### - Enable [in]

If <b>TRUE</b>, the filter is enabled on the video processor.


#### - Filter [in]

The filter, specified as a <a href="..\d3d10umddi\ne-d3d10umddi-d3d11_1ddi_video_processor_filter.md">D3D11_1DDI_VIDEO_PROCESSOR_FILTER</a> value.




#### - Level [in]

The filter level. The meaning of this value is defined by the independent hardware vendor (IHV).

<div class="alert"><b>Note</b>  If the <i>Enable</i> parameter is FALSE, this parameter is ignored.

</div>
<div> </div>

#### - StreamIndex [in]

The zero-based index of the input stream.


#### - hDevice [in]

A handle to the display device (graphics context).




#### - hVideoProcessor [in]

A handle to the video processor object that was created through a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessor.md">CreateVideoProcessor</a> function. 




## -returns



This callback function does not return a value.




## -see-also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessor.md">CreateVideoProcessor</a>



<a href="..\d3d10umddi\ne-d3d10umddi-d3d11_1ddi_video_processor_filter.md">D3D11_1DDI_VIDEO_PROCESSOR_FILTER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMFILTER callback function%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

