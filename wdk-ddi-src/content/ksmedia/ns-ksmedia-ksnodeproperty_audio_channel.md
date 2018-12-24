---
UID: NS:ksmedia.__unnamed_struct_61
title: KSNODEPROPERTY_AUDIO_CHANNEL
description: The KSNODEPROPERTY_AUDIO_CHANNEL structure specifies a property of a channel in a node.
old-location: audio\ksnodeproperty_audio_channel.htm
tech.root: audio
ms.assetid: f76f5552-725b-4d8c-ab29-1f2de7bdc81f
ms.date: 05/08/2018
ms.keywords: "*PKSNODEPROPERTY_AUDIO_CHANNEL, KSNODEPROPERTY_AUDIO_CHANNEL, KSNODEPROPERTY_AUDIO_CHANNEL structure [Audio Devices], PKSNODEPROPERTY_AUDIO_CHANNEL, PKSNODEPROPERTY_AUDIO_CHANNEL structure pointer [Audio Devices], aud-prop_a804d95b-c793-43c0-9579-af759c3c007f.xml, audio.ksnodeproperty_audio_channel, ksmedia/KSNODEPROPERTY_AUDIO_CHANNEL, ksmedia/PKSNODEPROPERTY_AUDIO_CHANNEL"
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
-	KSNODEPROPERTY_AUDIO_CHANNEL
product:
- Windows
targetos: Windows
req.typenames: KSNODEPROPERTY_AUDIO_CHANNEL, *PKSNODEPROPERTY_AUDIO_CHANNEL
---

# KSNODEPROPERTY_AUDIO_CHANNEL structure


## -description


The KSNODEPROPERTY_AUDIO_CHANNEL structure specifies a property of a channel in a node.


## -struct-fields




### -field NodeProperty

Specifies both the target node and the property to get or set. This member is a structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff537143">KSNODEPROPERTY</a>.


### -field Channel

Specifies a channel number. This member identifies the channel that is to be controlled. Given a stream with <i>n</i> channels, the channels are numbered 0 to <i>n</i>-1. When a channel number of -1 (0xFFFFFFFF) is specified, the level applies to the entire stream.

It is important  to note that the standard USB audio specification provides a mechanism that allows audio drivers that support the master channel control feature, to apply channel-specific information to an entire stream. To implement this mechanism, the USB audio driver must set the channel number to zero (0). Therefore, when a USB audio driver sets the channel number to -1, there is no guarantee that the property information will be applied to the entire stream.


### -field Reserved

Reserved for internal use by operating system. Do not use.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff537143">KSNODEPROPERTY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh831855">KSPROPERTY_AUDIOENGINE_VOLUMELEVEL</a>
 

 

