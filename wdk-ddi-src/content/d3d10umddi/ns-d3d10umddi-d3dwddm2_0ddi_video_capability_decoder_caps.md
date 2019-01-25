---
UID: NS:d3d10umddi.D3DWDDM2_0DDI_VIDEO_CAPABILITY_DECODER_CAPS
title: D3DWDDM2_0DDI_VIDEO_CAPABILITY_DECODER_CAPS (d3d10umddi.h)
description: D3DWDDM2_0DDI_VIDEO_CAPABILITY_DECODER_CAPS contains information describing the capabilities of the video decoder.
old-location: display\d3dwddm2_0ddi_video_capability_decoder_caps.htm
ms.assetid: C248B20E-A9A1-4C79-9053-16AC2059205E
ms.date: 05/10/2018
ms.keywords: D3DWDDM2_0DDI_VIDEO_CAPABILITY_DECODER_CAPS, D3DWDDM2_0DDI_VIDEO_CAPABILITY_DECODER_CAPS structure [Display Devices], d3d10umddi/D3DWDDM2_0DDI_VIDEO_CAPABILITY_DECODER_CAPS, display.d3dwddm2_0ddi_video_capability_decoder_caps
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
-	D3DWDDM2_0DDI_VIDEO_CAPABILITY_DECODER_CAPS
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3DWDDM2_0DDI_VIDEO_CAPABILITY_DECODER_CAPS
---

# D3DWDDM2_0DDI_VIDEO_CAPABILITY_DECODER_CAPS structure


## -description


<b>D3DWDDM2_0DDI_VIDEO_CAPABILITY_DECODER_CAPS</b> contains information describing the capabilities of the video decoder.


## -struct-fields




### -field DecodeProfile

Indicates the decode profile for which the capabilities are queried.


### -field SampleWidth

Indicates the video width for which the capabilities are queried.


### -field SampleHeight

Indicates the video height for which the capabilities are queried.


### -field FrameRate

Indicates the frame rate of the video content.


### -field BitRate

 


### -field pCryptoType

 


### -field Caps

Returns a combination of <a href="https://msdn.microsoft.com/library/windows/hardware/dn894620">D3DWDDM2_0DDI_VIDEO_DECODER_CAPS</a> enumeration values combined together using a bitwise <i>OR</i> operation.

