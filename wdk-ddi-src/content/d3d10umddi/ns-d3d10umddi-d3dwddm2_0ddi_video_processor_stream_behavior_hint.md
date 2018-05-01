---
UID: NS:d3d10umddi.D3DWDDM2_0DDI_VIDEO_PROCESSOR_STREAM_BEHAVIOR_HINT
title: D3DWDDM2_0DDI_VIDEO_PROCESSOR_STREAM_BEHAVIOR_HINT
author: windows-driver-content
description: D3DWDDM2_0DDI_VIDEO_PROCESSOR_STREAM_BEHAVIOR_HINT is used to describe behavior hints for the stream.
old-location: display\d3dwddm2_0ddi_video_processor_stream_behavior_hint.htm
old-project: display
ms.assetid: 82B8F3F2-62E5-475B-AAE0-F6DF2B2B9814
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: D3DWDDM2_0DDI_VIDEO_PROCESSOR_STREAM_BEHAVIOR_HINT, D3DWDDM2_0DDI_VIDEO_PROCESSOR_STREAM_BEHAVIOR_HINT structure [Display Devices], d3d10umddi/D3DWDDM2_0DDI_VIDEO_PROCESSOR_STREAM_BEHAVIOR_HINT, display.d3dwddm2_0ddi_video_processor_stream_behavior_hint
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
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
-	HeaderDef
api_location:
-	D3d10umddi.h
api_name:
-	D3DWDDM2_0DDI_VIDEO_PROCESSOR_STREAM_BEHAVIOR_HINT
product: Windows
targetos: Windows
req.typenames: D3DWDDM2_0DDI_VIDEO_PROCESSOR_STREAM_BEHAVIOR_HINT
---

# D3DWDDM2_0DDI_VIDEO_PROCESSOR_STREAM_BEHAVIOR_HINT structure


## -description


<b>D3DWDDM2_0DDI_VIDEO_PROCESSOR_STREAM_BEHAVIOR_HINT</b> is used to describe behavior hints for the stream.


## -struct-fields




### -field Enable

Specifies whether this input stream is enabled. If <b>TRUE</b>,  <a href="https://msdn.microsoft.com/library/windows/hardware/dn906379">VideoProcessorGetBehaviorHints</a> uses this stream to compute the behavior hints. Otherwise, this stream is not used.  


### -field Width

Specifies the width of the input stream.


### -field Height

Specifies the height of the input stream.


### -field Format

Indicates the input format for the specific stream.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn906379">VideoProcessorGetBehaviorHints</a>
 

 

