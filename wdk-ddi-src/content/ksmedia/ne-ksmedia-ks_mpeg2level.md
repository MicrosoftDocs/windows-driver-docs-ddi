---
UID: NE:ksmedia.KS_MPEG2Level
title: KS_MPEG2Level
author: windows-driver-content
description: The KS_MPEG2Level enumeration describes MPEG-2 levels.
old-location: stream\ks_mpeg2level.htm
old-project: stream
ms.assetid: 5ba271ba-ed92-402e-9ef9-ac198a8ea510
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , ,, 2, E, G, K, KS_MPEG2Level, KS_MPEG2Level enumeration [Streaming Media Devices], KS_MPEG2Level_High, KS_MPEG2Level_High1440, KS_MPEG2Level_Low, KS_MPEG2Level_Main, L, M, P, S, _, e, ksmedia/KS_MPEG2Level, ksmedia/KS_MPEG2Level_High, ksmedia/KS_MPEG2Level_High1440, ksmedia/KS_MPEG2Level_Low, ksmedia/KS_MPEG2Level_Main, l, stream.ks_mpeg2level, v, vidcapstruct_a97daeef-93e4-4ded-98dc-f583c1893095.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
-	KS_MPEG2Level
product: Windows
targetos: Windows
req.typenames: KS_MPEG2Level
---

# KS_MPEG2Level enumeration


## -description


The KS_MPEG2Level enumeration describes MPEG-2 levels.


## -syntax


````
typedef enum  { 
  KS_MPEG2Level_Low       = 0,
  KS_MPEG2Level_Main      = 1,
  KS_MPEG2Level_High1440  = 2,
  KS_MPEG2Level_High      = 3
} KS_MPEG2Level;
````


## -enum-fields




### -field KS_MPEG2Level_Low

Specifies the low MPEG-2 resolution, or 352 × 240 at 30 frames per second.


### -field KS_MPEG2Level_Main

Specifies the main MPEG-2 resolution, or 720 × 480 at 30 frames per second.


### -field KS_MPEG2Level_High1440

Specifies the high-1440 MPEG-2 resolution, or 1440 × 1152 at 30 frames per second.


### -field KS_MPEG2Level_High

Specifies the high MPEG-2 resolution, or 1920 × 1080 at 30 frames per second.


## -see-also

<a href="..\ksmedia\ns-ksmedia-tagks_mpegvideoinfo2.md">KS_MPEGVIDEOINFO2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KS_MPEG2Level enumeration%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

