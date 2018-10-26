---
UID: NS:ksmedia.tag_KS_TRUECOLORINFO
title: tag_KS_TRUECOLORINFO
author: windows-driver-content
description: The KS_TRUECOLORINFO structure describes color palette and bitmask information for video images that also contain a palette.
old-location: stream\ks_truecolorinfo.htm
tech.root: stream
ms.assetid: 8297a687-1c8f-4c19-913d-2796e7ef3a60
ms.date: 04/23/2018
ms.keywords: "*PKS_TRUECOLORINFO, KS_TRUECOLORINFO, KS_TRUECOLORINFO structure [Streaming Media Devices], PKS_TRUECOLORINFO, PKS_TRUECOLORINFO structure pointer [Streaming Media Devices], ksmedia/KS_TRUECOLORINFO, ksmedia/PKS_TRUECOLORINFO, stream.ks_truecolorinfo, tag_KS_TRUECOLORINFO, vidcapstruct_02efd829-b75a-4a08-864d-cd80570d0f3a.xml"
ms.topic: struct
req.header: ksmedia.h
req.include-header: Ksmedia.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
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
-	ksmedia.h
api_name:
-	KS_TRUECOLORINFO
product:
- Windows
targetos: Windows
req.typenames: KS_TRUECOLORINFO, *PKS_TRUECOLORINFO
---

# tag_KS_TRUECOLORINFO structure


## -description


The KS_TRUECOLORINFO structure describes color palette and bitmask information for video images that also contain a palette.


## -struct-fields




### -field dwBitMasks

Array of color masks (one per color element).


### -field bmiColors

Array of palette colors.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff567675">KS_RGBQUAD</a>
 

 

