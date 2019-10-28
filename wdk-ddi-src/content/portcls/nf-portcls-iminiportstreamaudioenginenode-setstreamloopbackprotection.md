---
UID: NF:portcls.IMiniportStreamAudioEngineNode.SetStreamLoopbackProtection
title: IMiniportStreamAudioEngineNode::SetStreamLoopbackProtection (portcls.h)
description: Sets the loopback protection status of the audio engine node.
old-location: audio\iminiportstreamaudioenginenode_setstreamloopbackprotection.htm
tech.root: audio
ms.assetid: FAC9AC9B-9C4B-4D53-A59A-8901EC8755BC
ms.date: 05/08/2018
ms.keywords: IMiniportStreamAudioEngineNode interface [Audio Devices],SetStreamLoopbackProtection method, IMiniportStreamAudioEngineNode.SetStreamLoopbackProtection, IMiniportStreamAudioEngineNode::SetStreamLoopbackProtection, SetStreamLoopbackProtection, SetStreamLoopbackProtection method [Audio Devices], SetStreamLoopbackProtection method [Audio Devices],IMiniportStreamAudioEngineNode interface, audio.iminiportstreamaudioenginenode_setstreamloopbackprotection, portcls/IMiniportStreamAudioEngineNode::SetStreamLoopbackProtection
ms.topic: method
f1_keywords:
 - "portcls/IMiniportStreamAudioEngineNode.SetStreamLoopbackProtection"
req.header: portcls.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
- COM
api_location:
- Portcls.h
api_name:
- IMiniportStreamAudioEngineNode.SetStreamLoopbackProtection
product:
- Windows
targetos: Windows
req.typenames: 
---

# IMiniportStreamAudioEngineNode::SetStreamLoopbackProtection


## -description


Sets the loopback protection status of the audio engine node.


## -parameters




### -param ProtectionOption [in]

A CONSTRICTOR_OPTION enumeration  value that indicates status of the loopback protection option.


## -returns



<b>SetStreamLoopbackProtection</b> returns S_OK, if the call was successful. Otherwise, the method returns an appropriate error code.




## -remarks



For more information about audio stream loopback protection, see <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/ksproperty-audioengine-loopback-protection">KSPROPERTY_AUDIOENGINE_LOOPBACK_PROTECTION</a>.




## -see-also




CONSTRICTOR_OPTION



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nn-portcls-iminiportstreamaudioenginenode">IMiniportStreamAudioEngineNode</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/audio/ksproperty-audioengine-loopback-protection">KSPROPERTY_AUDIOENGINE_LOOPBACK_PROTECTION</a>
 

 

