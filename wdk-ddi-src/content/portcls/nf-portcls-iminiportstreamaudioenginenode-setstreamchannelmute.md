---
UID: NF:portcls.IMiniportStreamAudioEngineNode.SetStreamChannelMute
title: IMiniportStreamAudioEngineNode::SetStreamChannelMute (portcls.h)
description: Sets the state of the Mute node in the path of the audio stream.
old-location: audio\iminiportstreamaudioenginenode_setstreamchannelmute.htm
tech.root: audio
ms.assetid: AAD0101E-13FB-48A2-8834-799472B93931
ms.date: 05/08/2018
keywords: ["IMiniportStreamAudioEngineNode::SetStreamChannelMute"]
ms.keywords: IMiniportStreamAudioEngineNode interface [Audio Devices],SetStreamChannelMute method, IMiniportStreamAudioEngineNode.SetStreamChannelMute, IMiniportStreamAudioEngineNode::SetStreamChannelMute, SetStreamChannelMute, SetStreamChannelMute method [Audio Devices], SetStreamChannelMute method [Audio Devices],IMiniportStreamAudioEngineNode interface, audio.iminiportstreamaudioenginenode_setstreamchannelmute, portcls/IMiniportStreamAudioEngineNode::SetStreamChannelMute
f1_keywords:
 - "portcls/IMiniportStreamAudioEngineNode.SetStreamChannelMute"
 - "IMiniportStreamAudioEngineNode.SetStreamChannelMute"
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
- IMiniportStreamAudioEngineNode.SetStreamChannelMute
targetos: Windows
req.typenames: 
---

# IMiniportStreamAudioEngineNode::SetStreamChannelMute


## -description


Sets the state of the Mute node in the path of the audio stream.


## -parameters




### -param ulChannel 
[in]
The channel for the audio stream.


### -param bMute 
[in]
The state to which the Mute node will be set.


## -returns



<b>SetStreamChannelMute</b> returns S_OK, if the call was successful. Otherwise, the method returns an appropriate error 

code.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nn-portcls-iminiportstreamaudioenginenode">IMiniportStreamAudioEngineNode</a>
 

 

