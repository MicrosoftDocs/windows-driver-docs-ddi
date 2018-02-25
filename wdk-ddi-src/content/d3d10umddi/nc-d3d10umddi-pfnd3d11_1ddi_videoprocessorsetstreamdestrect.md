---
UID: NC:d3d10umddi.PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMDESTRECT
title: PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMDESTRECT
author: windows-driver-content
description: Sets the destination rectangle for an input stream on the video processor.
old-location: display\videoprocessorsetstreamdestrect.htm
old-project: display
ms.assetid: 84AD6C4F-A674-4CCC-B2E9-378E3E55EEF3
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMDESTRECT, d3d10umddi/pfnVideoProcessorSetStreamDestRect, display.videoprocessorsetstreamdestrect, pfnVideoProcessorSetStreamDestRect, pfnVideoProcessorSetStreamDestRect callback function [Display Devices]
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
-	pfnVideoProcessorSetStreamDestRect
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMDESTRECT callback


## -description


Sets the destination rectangle for an input stream on the video processor.


## -prototype


````
PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMDESTRECT pfnVideoProcessorSetStreamDestRect;

VOID APIENTRY* pfnVideoProcessorSetStreamDestRect(
  _In_       D3D10DDI_HDEVICE           hDevice,
  _In_       D3D11_1DDI_HVIDEOPROCESSOR hVideoProcessor,
  _In_       UINT                       StreamIndex,
  _In_       BOOL                       Enable,
  _In_ const RECT                       *pDestRect
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

A handle to the video processor object that was created through a call to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_dxvahd_createvideoprocessor.md">CreateVideoProcessor</a> function. 


#### - StreamIndex [in]

The zero-based index of the input stream.


#### - Enable [in]

If <b>TRUE</b>, the destination rectangle specified by the <i>pDestRect</i> parameter should be used by the video processor.




#### - pDestRect [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a> structure that specifies the destination rectangle.

<div class="alert"><b>Note</b>  If the <i>Enable</i> parameter is <b>FALSE</b>, this parameter is ignored.</div>
<div> </div>

## -returns



This callback function does not return a value.




## -remarks



The destination rectangle is the portion of the output surface that receives the bit-block transfer (bitblt) for the specified input stream. The destination rectangle is given in pixel coordinates, relative to the output surface.

The default destination rectangle is an empty rectangle (0, 0, 0, 0). If the <i>VideoProcessorSetStreamDestRect</i> function is never called, or if the <i>Enable</i> parameter is <b>FALSE</b>, no data is written from the specified input stream.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_dxvahd_createvideoprocessor.md">CreateVideoProcessor</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMDESTRECT callback function%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

