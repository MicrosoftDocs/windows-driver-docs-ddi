---
UID: NC:d3d10umddi.PFND3DWDDM2_0DDI_VIDEOPROCESSORSETSTREAMMIRROR
title: PFND3DWDDM2_0DDI_VIDEOPROCESSORSETSTREAMMIRROR
author: windows-driver-content
description: Indicates whether the stream should be flipped vertically or horizontally. Optional for Windows Display Driver Model (WDDM) 2.0, or later, drivers.
old-location: display\videoprocessorsetstreammirror.htm
old-project: display
ms.assetid: 945BD212-7B48-41FD-B11F-FB03DB073BD4
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.videoprocessorsetstreammirror, pfnVideoProcessorSetStreamMirror callback function [Display Devices], pfnVideoProcessorSetStreamMirror, PFND3DWDDM2_0DDI_VIDEOPROCESSORSETSTREAMMIRROR, PFND3DWDDM2_0DDI_VIDEOPROCESSORSETSTREAMMIRROR, d3d10umddi/pfnVideoProcessorSetStreamMirror
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	D3d10umddi.h
apiname:
-	pfnVideoProcessorSetStreamMirror
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3DWDDM2_0DDI_VIDEOPROCESSORSETSTREAMMIRROR callback


## -description


Indicates whether the stream should be flipped vertically or horizontally. Optional for Windows Display Driver Model (WDDM) 2.0, or later, drivers.


## -prototype


````
PFND3DWDDM2_0DDI_VIDEOPROCESSORSETSTREAMMIRROR pfnVideoProcessorSetStreamMirror;

VOID APIENTRY* pfnVideoProcessorSetStreamMirror(
  _In_ D3D10DDI_HDEVICE           hDevice,
  _In_ D3D11_1DDI_HVIDEOPROCESSOR hVideoProcessor,
  _In_ UINT                       StreamIndex,
  _In_ BOOL                       Enable,
  _In_ BOOL                       FlipHorizontal,
  _In_ BOOL                       FlipVertical
)
{ ... }
````


## -parameters




### -param hDevice [in]

 A handle to the display device (graphics context). The Direct3D runtime passed the user-mode driver this handle as the <b>hDevice</b> member of the <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_createdevice.md">D3DDDIARG_CREATEDEVICE</a> structure at device creation.


### -param hVideoProcessor [in]

Handle to the video processor object.


### -param StreamIndex [in]

Indicates the input stream.


### -param Enable [in]

Indicates whether mirroring support is enabled or disabled.


### -param FlipHorizontal [in]

Indicates whether the input stream should be flipped horizontally.


<div class="alert"><b>Note</b>  This should be ignored when <b>Enable</b> is <b>FALSE</b>.</div><div> </div>

### -param FlipVertical [in]

Indicates whether the input stream should be flipped vertically.


<div class="alert"><b>Note</b>  This should be ignored when <b>Enable</b> is <b>FALSE</b>.
</div><div> </div>

## -returns


This callback function does not return a value.



## -remarks


Operations are conceptually applied in the following order:



## -see-also

<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_createdevice.md">D3DDDIARG_CREATEDEVICE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DWDDM2_0DDI_VIDEOPROCESSORSETSTREAMMIRROR callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

