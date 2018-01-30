---
UID: NS:ksmedia.tag_KS_TRUECOLORINFO
title: tag_KS_TRUECOLORINFO
author: windows-driver-content
description: The KS_TRUECOLORINFO structure describes color palette and bitmask information for video images that also contain a palette.
old-location: stream\ks_truecolorinfo.htm
old-project: stream
ms.assetid: 8297a687-1c8f-4c19-913d-2796e7ef3a60
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: KS_TRUECOLORINFO, KS_TRUECOLORINFO structure [Streaming Media Devices], PKS_TRUECOLORINFO structure pointer [Streaming Media Devices], *PKS_TRUECOLORINFO, tag_KS_TRUECOLORINFO, PKS_TRUECOLORINFO, ksmedia/PKS_TRUECOLORINFO, stream.ks_truecolorinfo, vidcapstruct_02efd829-b75a-4a08-864d-cd80570d0f3a.xml, ksmedia/KS_TRUECOLORINFO
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ksmedia.h
apiname:
-	KS_TRUECOLORINFO
product: Windows
targetos: Windows
req.typenames: KS_TRUECOLORINFO, *PKS_TRUECOLORINFO
---

# tag_KS_TRUECOLORINFO structure


## -description


The KS_TRUECOLORINFO structure describes color palette and bitmask information for video images that also contain a palette.


## -syntax


````
typedef struct tag_KS_TRUECOLORINFO {
  DWORD      dwBitMasks[KS_iMASK_COLORS];
  KS_RGBQUAD bmiColors[KS_iPALETTE_COLORS];
} KS_TRUECOLORINFO, *PKS_TRUECOLORINFO;
````


## -struct-fields




### -field dwBitMasks

Array of color masks (one per color element).


### -field bmiColors

Array of palette colors.


## -see-also

<a href="..\ksmedia\ns-ksmedia-tagks_rgbquad.md">KS_RGBQUAD</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KS_TRUECOLORINFO structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

