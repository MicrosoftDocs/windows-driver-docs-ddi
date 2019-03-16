---
UID: NE:ksmedia.__unnamed_enum_71
title: KS_VIDEODECODER_FLAGS (ksmedia.h)
description: The KS_VIDEODECODER_FLAGS enumeration defines video decoder capabilities.
old-location: stream\ks_videodecoder_flags.htm
tech.root: stream
ms.assetid: 120d7714-8c32-4b83-adc2-c9a933e541e5
ms.date: 04/23/2018
ms.keywords: KS_VIDEODECODER_FLAGS, KS_VIDEODECODER_FLAGS enumeration [Streaming Media Devices], KS_VIDEODECODER_FLAGS_CAN_DISABLE_OUTPUT, KS_VIDEODECODER_FLAGS_CAN_INDICATE_LOCKED, KS_VIDEODECODER_FLAGS_CAN_USE_VCR_LOCKING, ksmedia/KS_VIDEODECODER_FLAGS, ksmedia/KS_VIDEODECODER_FLAGS_CAN_DISABLE_OUTPUT, ksmedia/KS_VIDEODECODER_FLAGS_CAN_INDICATE_LOCKED, ksmedia/KS_VIDEODECODER_FLAGS_CAN_USE_VCR_LOCKING, stream.ks_videodecoder_flags, vidcapstruct_061ba371-f4a8-44b0-8940-bc90b15dbfed.xml
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ksmedia.h
api_name:
- KS_VIDEODECODER_FLAGS
product:
- Windows
targetos: Windows
req.typenames: KS_VIDEODECODER_FLAGS
---

# KS_VIDEODECODER_FLAGS enumeration


## -description


The KS_VIDEODECODER_FLAGS enumeration defines video decoder capabilities.


## -enum-fields




### -field KS_VIDEODECODER_FLAGS_CAN_DISABLE_OUTPUT

The decoder can translate its output lines. Video decoders that use a video port use this flag.


### -field KS_VIDEODECODER_FLAGS_CAN_USE_VCR_LOCKING

The video decoder can alter its phase locked loop (PLL) timings to lock on to noisy signals. This flag typically is used when the video source is a VCR that introduces variability in the vertical and horizontal sync timing.


### -field KS_VIDEODECODER_FLAGS_CAN_INDICATE_LOCKED

The video decoder can distinguish whether it has locked to an incoming analog video signal.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff566047">KSPROPERTY_VIDEODECODER_CAPS_S</a>
 

 

