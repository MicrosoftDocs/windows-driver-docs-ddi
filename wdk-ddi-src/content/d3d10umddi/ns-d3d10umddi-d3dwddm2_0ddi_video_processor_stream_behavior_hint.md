---
UID: NS:d3d10umddi.D3DWDDM2_0DDI_VIDEO_PROCESSOR_STREAM_BEHAVIOR_HINT
title: D3DWDDM2_0DDI_VIDEO_PROCESSOR_STREAM_BEHAVIOR_HINT
author: windows-driver-content
description: D3DWDDM2_0DDI_VIDEO_PROCESSOR_STREAM_BEHAVIOR_HINT is used to describe behavior hints for the stream.
old-location: display\d3dwddm2_0ddi_video_processor_stream_behavior_hint.htm
old-project: display
ms.assetid: 82B8F3F2-62E5-475B-AAE0-F6DF2B2B9814
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DWDDM2_0DDI_VIDEO_PROCESSOR_STREAM_BEHAVIOR_HINT, d3d10umddi/D3DWDDM2_0DDI_VIDEO_PROCESSOR_STREAM_BEHAVIOR_HINT, D3DWDDM2_0DDI_VIDEO_PROCESSOR_STREAM_BEHAVIOR_HINT structure [Display Devices], display.d3dwddm2_0ddi_video_processor_stream_behavior_hint
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	D3d10umddi.h
apiname:
-	D3DWDDM2_0DDI_VIDEO_PROCESSOR_STREAM_BEHAVIOR_HINT
product: Windows
targetos: Windows
req.typenames: D3DWDDM2_0DDI_VIDEO_PROCESSOR_STREAM_BEHAVIOR_HINT
---

# D3DWDDM2_0DDI_VIDEO_PROCESSOR_STREAM_BEHAVIOR_HINT structure


## -description


<b>D3DWDDM2_0DDI_VIDEO_PROCESSOR_STREAM_BEHAVIOR_HINT</b> is used to describe behavior hints for the stream.


## -syntax


````
typedef struct D3DWDDM2_0DDI_VIDEO_PROCESSOR_STREAM_BEHAVIOR_HINT {
  BOOL        Enable;
  UINT        Width;
  UINT        Height;
  DXGI_FORMAT Format;
} D3DWDDM2_0DDI_VIDEO_PROCESSOR_STREAM_BEHAVIOR_HINT;
````


## -struct-fields




### -field Enable

Specifies whether this input stream is enabled. If <b>TRUE</b>,  <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3dwddm2_0ddi_videoprocessorgetbehaviorhints.md">VideoProcessorGetBehaviorHints</a> uses this stream to compute the behavior hints. Otherwise, this stream is not used.  


### -field Width

Specifies the width of the input stream.


### -field Height

Specifies the height of the input stream.


### -field Format

Indicates the input format for the specific stream.


## -see-also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3dwddm2_0ddi_videoprocessorgetbehaviorhints.md">VideoProcessorGetBehaviorHints</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DWDDM2_0DDI_VIDEO_PROCESSOR_STREAM_BEHAVIOR_HINT structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

