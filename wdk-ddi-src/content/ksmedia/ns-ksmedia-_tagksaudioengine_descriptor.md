---
UID: NS:ksmedia._tagKSAUDIOENGINE_DESCRIPTOR
title: "_tagKSAUDIOENGINE_DESCRIPTOR"
author: windows-driver-content
description: The KSAUDIOENGINE_DESCRIPTOR structure describes the static, external properties of the audio engine.
old-location: audio\ksaudioengine_descriptor.htm
old-project: audio
ms.assetid: 6691AB8B-EC6E-483B-A10A-6F9C5A97FEC9
ms.author: windowsdriverdev
ms.date: 3/19/2018
ms.keywords: "*PKSAUDIOENGINE_DESCRIPTOR, KSAUDIOENGINE_DESCRIPTOR, KSAUDIOENGINE_DESCRIPTOR structure [Audio Devices], PKSAUDIOENGINE_DESCRIPTOR, PKSAUDIOENGINE_DESCRIPTOR structure pointer [Audio Devices], _tagKSAUDIOENGINE_DESCRIPTOR, audio.ksaudioengine_descriptor, ksmedia/KSAUDIOENGINE_DESCRIPTOR, ksmedia/PKSAUDIOENGINE_DESCRIPTOR"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ksmedia.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8
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
-	Ksmedia.h
api_name:
-	KSAUDIOENGINE_DESCRIPTOR
product: Windows
targetos: Windows
req.typenames: KSAUDIOENGINE_DESCRIPTOR, *PKSAUDIOENGINE_DESCRIPTOR
---

# _tagKSAUDIOENGINE_DESCRIPTOR structure


## -description


The <b>KSAUDIOENGINE_DESCRIPTOR</b> structure describes the static, external  properties of the audio engine.


## -struct-fields




### -field nHostPinId

Specifies the ID of the pin factory that is connected to the audio engine node that handles host-processed audio data.  This is the pin factory on which a software audio engine will run.


### -field nOffloadPinId

Specifies the ID of the pin factory that is connected to the audio engine node that handles offloaded streams.


### -field nLoopbackPinId

Specifies the ID of the pin factory that is connected to the audio engine node that supplies a post-mix loopback or reference stream.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn265074">GetAudioEngineDescriptor</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh450870">KSPROPERTY_AUDIOENGINE_DESCRIPTOR</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20KSAUDIOENGINE_DESCRIPTOR structure%20 RELEASE:%20(3/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

