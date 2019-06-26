---
UID: NC:d3d10umddi.PFND3DWDDM2_0DDI_VIDEOPROCESSORSETSTREAMMIRROR
title: PFND3DWDDM2_0DDI_VIDEOPROCESSORSETSTREAMMIRROR (d3d10umddi.h)
description: Indicates whether the stream should be flipped vertically or horizontally. Optional for Windows Display Driver Model (WDDM) 2.0, or later, drivers.
old-location: display\videoprocessorsetstreammirror.htm
ms.assetid: 945BD212-7B48-41FD-B11F-FB03DB073BD4
ms.date: 05/10/2018
ms.keywords: PFND3DWDDM2_0DDI_VIDEOPROCESSORSETSTREAMMIRROR, PFND3DWDDM2_0DDI_VIDEOPROCESSORSETSTREAMMIRROR callback, d3d10umddi/pfnVideoProcessorSetStreamMirror, display.videoprocessorsetstreammirror, pfnVideoProcessorSetStreamMirror, pfnVideoProcessorSetStreamMirror callback function [Display Devices]
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- D3d10umddi.h
api_name:
- pfnVideoProcessorSetStreamMirror
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3DWDDM2_0DDI_VIDEOPROCESSORSETSTREAMMIRROR callback function


## -description


Indicates whether the stream should be flipped vertically or horizontally. Optional for Windows Display Driver Model (WDDM) 2.0, or later, drivers.


## -parameters




### -param hDevice [in]

A handle to the display device (graphics context). The Direct3D runtime passed the user-mode driver this handle as the <b>hDevice</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_d3dddiarg_createdevice">D3DDDIARG_CREATEDEVICE</a> structure at device creation.


### -param hVideoProcessor [in]

Handle to the video processor object.


### -param StreamIndex [in]

Indicates the input stream.


### -param Enable [in]

Indicates whether mirroring support is enabled or disabled.


### -param FlipHorizontal [in]

Indicates whether the input stream should be flipped horizontally.



<div class="alert"><b>Note</b>  This should be ignored when <b>Enable</b> is <b>FALSE</b>.</div>
<div> </div>

### -param FlipVertical [in]

Indicates whether the input stream should be flipped vertically.



<div class="alert"><b>Note</b>  This should be ignored when <b>Enable</b> is <b>FALSE</b>.
</div>
<div> </div>

## -returns



This callback function does not return a value.




## -remarks



Operations are conceptually applied in the following order:




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_d3dddiarg_createdevice">D3DDDIARG_CREATEDEVICE</a>
 

 

