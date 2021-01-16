---
UID: NF:portcls.IMiniportAudioEngineNode.GetDeviceChannelMute
title: IMiniportAudioEngineNode::GetDeviceChannelMute (portcls.h)
description: Gets the state of the Mute node for the audio device channel.
old-location: audio\iminiportaudioenginenode_getdevicechannelmute.htm
tech.root: audio
ms.date: 05/08/2018
keywords: ["IMiniportAudioEngineNode::GetDeviceChannelMute"]
ms.keywords: GetDeviceChannelMute, GetDeviceChannelMute method [Audio Devices], GetDeviceChannelMute method [Audio Devices],IMiniportAudioEngineNode interface, IMiniportAudioEngineNode interface [Audio Devices],GetDeviceChannelMute method, IMiniportAudioEngineNode.GetDeviceChannelMute, IMiniportAudioEngineNode::GetDeviceChannelMute, audio.iminiportaudioenginenode_getdevicechannelmute, portcls/IMiniportAudioEngineNode::GetDeviceChannelMute
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
 - IMiniportAudioEngineNode::GetDeviceChannelMute
 - portcls/IMiniportAudioEngineNode::GetDeviceChannelMute
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Portcls.h
api_name:
 - IMiniportAudioEngineNode::GetDeviceChannelMute
---

# IMiniportAudioEngineNode::GetDeviceChannelMute


## -description

Gets the state of the Mute node for the audio device channel.

## -parameters

### -param ulNodeId 

[in]
The ID for the node that represents the audio device.

### -param ulChannel 

[in]
The audio device channel.

### -param pbMute 

[out]
The current state of the Mute node for the audio device channel.

## -returns

<b>GetDeviceChannelMute</b> returns S_OK, if the call was successful. Otherwise, the method returns an appropriate error 

code.

## -see-also

<a href="/windows-hardware/drivers/ddi/portcls/nn-portcls-iminiportaudioenginenode">IMiniportAudioEngineNode</a>

