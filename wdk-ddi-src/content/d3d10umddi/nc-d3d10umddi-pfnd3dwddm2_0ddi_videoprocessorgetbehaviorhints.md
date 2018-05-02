---
UID: NC:d3d10umddi.PFND3DWDDM2_0DDI_VIDEOPROCESSORGETBEHAVIORHINTS
title: PFND3DWDDM2_0DDI_VIDEOPROCESSORGETBEHAVIORHINTS
author: windows-driver-content
description: Returns driver hints as to which video processor operations are best performed using multi-plane overlay hardware rather than VideoProcessorBlt. Optional for Windows Display Driver Model (WDDM) 2.0, or later, drivers.
old-location: display\videoprocessorgetbehaviorhints.htm
old-project: display
ms.assetid: E6CBAFEE-9587-45D5-A6CD-4CA739AF279E
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: PFND3DWDDM2_0DDI_VIDEOPROCESSORGETBEHAVIORHINTS, PFND3DWDDM2_0DDI_VIDEOPROCESSORGETBEHAVIORHINTS callback, d3d10umddi/pfnVideoProcessorGetBehaviorHints, display.videoprocessorgetbehaviorhints, pfnVideoProcessorGetBehaviorHints, pfnVideoProcessorGetBehaviorHints callback function [Display Devices]
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
-	pfnVideoProcessorGetBehaviorHints
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3DWDDM2_0DDI_VIDEOPROCESSORGETBEHAVIORHINTS callback function


## -description


Returns driver hints as to which video processor operations are best performed using multi-plane overlay hardware rather than <a href="https://msdn.microsoft.com/library/windows/hardware/hh451703">VideoProcessorBlt</a>. Optional for Windows Display Driver Model (WDDM) 2.0, or later, drivers.


## -parameters




### -param hDevice [in]

 A handle to the display device (graphics context). The Direct3D runtime passed the user-mode driver this handle as the <b>hDevice</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff542931">D3DDDIARG_CREATEDEVICE</a> structure at device creation.


### -param hVideoProcessor [in]

Handle to the video processor object.


### -param OutputWidth [in]

Indicates the width of the output surface.


### -param OutputHeight [in]

Indicates the height of the output surface.


### -param OutputFormat [in]

Indicates the output format of the video processor. 


### -param StreamCount [in]

The number of input streams to process. 


### -param *pStreams [in]

An array of structures indicating the format and status of each stream.


### -param *pBehaviorHints [out]

Receives a combination of <b>D3DWDDM2_0DDI_VIDEO_PROCESSOR_MULTIPLANE_BEHAVIOR_HINTS</b> values indicting which of the operations would best be performed using multi-plane overlay hardware rather than with <a href="https://msdn.microsoft.com/library/windows/hardware/hh451703">VideoProcessorBlt</a>. 


## -returns



If this callback function succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -remarks



This function uses the current state, set via the <b>VideoProcessorSetOutput</b> and <b>VideoProcessorSetStream</b> set of  device driver interfaces (DDIs), and returns which operations could be performed more efficiently using multiple overlay hardware. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff542931">D3DDDIARG_CREATEDEVICE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451703">VideoProcessorBlt</a>
 

 

