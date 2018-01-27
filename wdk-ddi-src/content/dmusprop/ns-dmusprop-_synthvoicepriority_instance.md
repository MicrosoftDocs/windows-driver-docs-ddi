---
UID: NS:dmusprop._SYNTHVOICEPRIORITY_INSTANCE
title: _SYNTHVOICEPRIORITY_INSTANCE
author: windows-driver-content
description: The SYNTHVOICEPRIORITY_INSTANCE structure identifies a voice in a MIDI synthesizer by specifying the voice's channel group (set of 16 MIDI channels) and its channel number within that group.
old-location: audio\synthvoicepriority_instance.htm
old-project: audio
ms.assetid: dc9acd16-c515-4e47-9a0b-9dec46e30f74
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: PSYNTHVOICEPRIORITY_INSTANCE, SYNTHVOICEPRIORITY_INSTANCE structure [Audio Devices], PSYNTHVOICEPRIORITY_INSTANCE structure pointer [Audio Devices], audio.synthvoicepriority_instance, _SYNTHVOICEPRIORITY_INSTANCE, dmusprop/SYNTHVOICEPRIORITY_INSTANCE, dmusprop/PSYNTHVOICEPRIORITY_INSTANCE, *PSYNTHVOICEPRIORITY_INSTANCE, SYNTHVOICEPRIORITY_INSTANCE, aud-prop_86a44512-a1b5-4380-a96a-5e9184ff71c2.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dmusprop.h
req.include-header: Dmusprop.h
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
-	dmusprop.h
apiname: 
-	SYNTHVOICEPRIORITY_INSTANCE
product: Windows
targetos: Windows
req.typenames: *PSYNTHVOICEPRIORITY_INSTANCE, SYNTHVOICEPRIORITY_INSTANCE
---

# _SYNTHVOICEPRIORITY_INSTANCE structure


## -description


The SYNTHVOICEPRIORITY_INSTANCE structure identifies a voice in a MIDI synthesizer by specifying the voice's channel group (set of 16 MIDI channels) and its channel number within that group.


## -syntax


````
typedef struct _SYNTHVOICEPRIORITY_INSTANCE {
  DWORD ChannelGroup;
  DWORD Channel;
} SYNTHVOICEPRIORITY_INSTANCE, *PSYNTHVOICEPRIORITY_INSTANCE;
````


## -struct-fields




### -field ChannelGroup

Specifies the channel group that the voice belongs to. Channel groups are numbered beginning at zero. Each channel group contains 16 channels.


### -field Channel

Specifies the channel that the voice is on. This member contains a channel number in the range 0 through 15. It identifies a channel in the channel group.


## -remarks


The <a href="https://msdn.microsoft.com/library/windows/hardware/ff537407">KSPROPERTY_SYNTH_VOICEPRIORITY</a> property request uses the SYNTHVOICEPRIORITY_INSTANCE structure for its property descriptor. The structure specifies which voice gets priority when the miniport driver needs to bump voices from the cache.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537407">KSPROPERTY_SYNTH_VOICEPRIORITY</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20SYNTHVOICEPRIORITY_INSTANCE structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

