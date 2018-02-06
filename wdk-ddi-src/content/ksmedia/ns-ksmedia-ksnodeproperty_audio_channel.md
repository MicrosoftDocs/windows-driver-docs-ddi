---
UID: NS:ksmedia.KSNODEPROPERTY_AUDIO_CHANNEL
title: KSNODEPROPERTY_AUDIO_CHANNEL
author: windows-driver-content
description: The KSNODEPROPERTY_AUDIO_CHANNEL structure specifies a property of a channel in a node.
old-location: audio\ksnodeproperty_audio_channel.htm
old-project: audio
ms.assetid: f76f5552-725b-4d8c-ab29-1f2de7bdc81f
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: PKSNODEPROPERTY_AUDIO_CHANNEL structure pointer [Audio Devices], KSNODEPROPERTY_AUDIO_CHANNEL, *PKSNODEPROPERTY_AUDIO_CHANNEL, aud-prop_a804d95b-c793-43c0-9579-af759c3c007f.xml, PKSNODEPROPERTY_AUDIO_CHANNEL, KSNODEPROPERTY_AUDIO_CHANNEL structure [Audio Devices], ksmedia/PKSNODEPROPERTY_AUDIO_CHANNEL, ksmedia/KSNODEPROPERTY_AUDIO_CHANNEL, audio.ksnodeproperty_audio_channel
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
-	KSNODEPROPERTY_AUDIO_CHANNEL
product: Windows
targetos: Windows
req.typenames: "*PKSNODEPROPERTY_AUDIO_CHANNEL, KSNODEPROPERTY_AUDIO_CHANNEL"
---

# KSNODEPROPERTY_AUDIO_CHANNEL structure


## -description


The KSNODEPROPERTY_AUDIO_CHANNEL structure specifies a property of a channel in a node.


## -syntax


````
typedef struct {
  KSNODEPROPERTY NodeProperty;
  LONG           Channel;
  ULONG          Reserved;
} KSNODEPROPERTY_AUDIO_CHANNEL, *PKSNODEPROPERTY_AUDIO_CHANNEL;
````


## -struct-fields




### -field NodeProperty

Specifies both the target node and the property to get or set. This member is a structure of type <a href="..\ksmedia\ns-ksmedia-ksnodeproperty.md">KSNODEPROPERTY</a>.


### -field Channel

Specifies a channel number. This member identifies the channel that is to be controlled. Given a stream with <i>n</i> channels, the channels are numbered 0 to <i>n</i>-1. When a channel number of -1 (0xFFFFFFFF) is specified, the level applies to the entire stream.

It is important  to note that the standard USB audio specification provides a mechanism that allows audio drivers that support the master channel control feature, to apply channel-specific information to an entire stream. To implement this mechanism, the USB audio driver must set the channel number to zero (0). Therefore, when a USB audio driver sets the channel number to -1, there is no guarantee that the property information will be applied to the entire stream.


### -field Reserved

Reserved for internal use by operating system. Do not use.


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh831855">KSPROPERTY_AUDIOENGINE_VOLUMELEVEL</a>

<a href="..\ksmedia\ns-ksmedia-ksnodeproperty.md">KSNODEPROPERTY</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20KSNODEPROPERTY_AUDIO_CHANNEL structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

