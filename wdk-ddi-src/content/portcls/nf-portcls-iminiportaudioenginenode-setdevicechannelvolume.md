---
UID: NF:portcls.IMiniportAudioEngineNode.SetDeviceChannelVolume
title: IMiniportAudioEngineNode::SetDeviceChannelVolume (portcls.h)
description: Sets the volume level for a given channel of the audio device.
old-location: audio\iminiportaudioenginenode_setdevicechannelvolume.htm
tech.root: audio
ms.assetid: 05DA619B-B36A-4E14-9F63-E12E90E0BDCD
ms.date: 05/08/2018
keywords: ["IMiniportAudioEngineNode::SetDeviceChannelVolume"]
ms.keywords: IMiniportAudioEngineNode interface [Audio Devices],SetDeviceChannelVolume method, IMiniportAudioEngineNode.SetDeviceChannelVolume, IMiniportAudioEngineNode::SetDeviceChannelVolume, SetDeviceChannelVolume, SetDeviceChannelVolume method [Audio Devices], SetDeviceChannelVolume method [Audio Devices],IMiniportAudioEngineNode interface, audio.iminiportaudioenginenode_setdevicechannelvolume, portcls/IMiniportAudioEngineNode::SetDeviceChannelVolume
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
 - IMiniportAudioEngineNode::SetDeviceChannelVolume
 - portcls/IMiniportAudioEngineNode::SetDeviceChannelVolume
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Portcls.h
api_name:
 - IMiniportAudioEngineNode.SetDeviceChannelVolume
---

# IMiniportAudioEngineNode::SetDeviceChannelVolume


## -description

Sets the volume level for a given channel of the audio device.

## -parameters

### -param ulNodeId 

[in]
The ID for the node that represents the audio device.

### -param ulChannel 

[in]
The audio device channel.

### -param lVolume 

[in]
The volume level to which the channel will be set.

## -returns

<b>SetDeviceChannelVolume</b> returns S_OK, if the call was successful. Otherwise, the method returns an appropriate error code.

## -see-also

<a href="/windows-hardware/drivers/ddi/portcls/nn-portcls-iminiportaudioenginenode">IMiniportAudioEngineNode</a>