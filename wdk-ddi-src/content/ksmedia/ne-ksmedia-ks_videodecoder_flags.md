---
UID: NE:ksmedia.KS_VIDEODECODER_FLAGS
title: KS_VIDEODECODER_FLAGS
author: windows-driver-content
description: The KS_VIDEODECODER_FLAGS enumeration defines video decoder capabilities.
old-location: stream\ks_videodecoder_flags.htm
old-project: stream
ms.assetid: 120d7714-8c32-4b83-adc2-c9a933e541e5
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: ",  , ,, A, C, D, E, F, G, I, K, KS_VIDEODECODER_FLAGS, KS_VIDEODECODER_FLAGS enumeration [Streaming Media Devices], KS_VIDEODECODER_FLAGS_CAN_DISABLE_OUTPUT, KS_VIDEODECODER_FLAGS_CAN_INDICATE_LOCKED, KS_VIDEODECODER_FLAGS_CAN_USE_VCR_LOCKING, L, O, R, S, V, _, ksmedia/KS_VIDEODECODER_FLAGS, ksmedia/KS_VIDEODECODER_FLAGS_CAN_DISABLE_OUTPUT, ksmedia/KS_VIDEODECODER_FLAGS_CAN_INDICATE_LOCKED, ksmedia/KS_VIDEODECODER_FLAGS_CAN_USE_VCR_LOCKING, stream.ks_videodecoder_flags, vidcapstruct_061ba371-f4a8-44b0-8940-bc90b15dbfed.xml"
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
-	KS_VIDEODECODER_FLAGS
product: Windows
targetos: Windows
req.typenames: KS_VIDEODECODER_FLAGS
---

# KS_VIDEODECODER_FLAGS enumeration


## -description


The KS_VIDEODECODER_FLAGS enumeration defines video decoder capabilities.


## -syntax


````
typedef enum  { 
  KS_VIDEODECODER_FLAGS_CAN_DISABLE_OUTPUT   = 0X0001,
  KS_VIDEODECODER_FLAGS_CAN_USE_VCR_LOCKING  = 0X0002,
  KS_VIDEODECODER_FLAGS_CAN_INDICATE_LOCKED  = 0X0004
} KS_VIDEODECODER_FLAGS;
````


## -enum-fields




### -field KS_VIDEODECODER_FLAGS_CAN_DISABLE_OUTPUT

The decoder can translate its output lines. Video decoders that use a video port use this flag.


### -field KS_VIDEODECODER_FLAGS_CAN_USE_VCR_LOCKING

The video decoder can alter its phase locked loop (PLL) timings to lock on to noisy signals. This flag typically is used when the video source is a VCR that introduces variability in the vertical and horizontal sync timing.


### -field KS_VIDEODECODER_FLAGS_CAN_INDICATE_LOCKED

The video decoder can distinguish whether it has locked to an incoming analog video signal.


## -see-also

<a href="..\ksmedia\ns-ksmedia-ksproperty_videodecoder_caps_s.md">KSPROPERTY_VIDEODECODER_CAPS_S</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KS_VIDEODECODER_FLAGS enumeration%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

