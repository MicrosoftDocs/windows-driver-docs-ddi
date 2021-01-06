---
UID: NF:portcls.IMiniportStreamAudioEngineNode.SetStreamChannelVolume
title: IMiniportStreamAudioEngineNode::SetStreamChannelVolume (portcls.h)
description: Sets the volume level to be applied to the audio stream.
old-location: audio\iminiportstreamaudioenginenode_setstreamchannelvolume.htm
tech.root: audio
ms.date: 05/08/2018
keywords: ["IMiniportStreamAudioEngineNode::SetStreamChannelVolume"]
ms.keywords: IMiniportStreamAudioEngineNode interface [Audio Devices],SetStreamChannelVolume method, IMiniportStreamAudioEngineNode.SetStreamChannelVolume, IMiniportStreamAudioEngineNode::SetStreamChannelVolume, SetStreamChannelVolume, SetStreamChannelVolume method [Audio Devices], SetStreamChannelVolume method [Audio Devices],IMiniportStreamAudioEngineNode interface, audio.iminiportstreamaudioenginenode_setstreamchannelvolume, portcls/IMiniportStreamAudioEngineNode::SetStreamChannelVolume
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IMiniportStreamAudioEngineNode::SetStreamChannelVolume
 - portcls/IMiniportStreamAudioEngineNode::SetStreamChannelVolume
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Portcls.h
api_name:
 - IMiniportStreamAudioEngineNode.SetStreamChannelVolume
---

# IMiniportStreamAudioEngineNode::SetStreamChannelVolume


## -description

Sets the volume level to be applied to the audio stream.

## -parameters

### -param Channel 

[in]
The audio stream channel.

### -param TargetVolume 

[in]
The volume level to be applied to the audio stream.

### -param CurveType 

[in]
The curve algorithm that will be used  to set the volume level. The curve types are represented by the members of the <a href="/windows-hardware/drivers/ddi/ksmedia/ne-ksmedia-audio_curve_type">AUDIO_CURVE_TYPE</a> enum.

### -param CurveDuration 

[in]
The length of time over which the curve algorithm will be applied.

## -returns

<b>SetStreamChannelVolume</b> returns S_OK, if the call was successful. Otherwise, the method returns an appropriate error 

code.

## -see-also

<a href="/windows-hardware/drivers/ddi/portcls/nn-portcls-iminiportstreamaudioenginenode">IMiniportStreamAudioEngineNode</a>
