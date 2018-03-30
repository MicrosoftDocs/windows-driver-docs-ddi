---
UID: NF:portcls.IMiniportAudioEngineNode.GetDeviceChannelMute
title: IMiniportAudioEngineNode::GetDeviceChannelMute method
author: windows-driver-content
description: Gets the state of the Mute node for the audio device channel.
old-location: audio\iminiportaudioenginenode_getdevicechannelmute.htm
old-project: audio
ms.assetid: 60CEBF40-25D3-49F0-A4BF-40440E1A3EE6
ms.author: windowsdriverdev
ms.date: 3/19/2018
ms.keywords: GetDeviceChannelMute method [Audio Devices], GetDeviceChannelMute method [Audio Devices], IMiniportAudioEngineNode interface, GetDeviceChannelMute,IMiniportAudioEngineNode.GetDeviceChannelMute, IMiniportAudioEngineNode, IMiniportAudioEngineNode interface [Audio Devices], GetDeviceChannelMute method, IMiniportAudioEngineNode::GetDeviceChannelMute, audio.iminiportaudioenginenode_getdevicechannelmute, portcls/IMiniportAudioEngineNode::GetDeviceChannelMute
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
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
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	Portcls.h
api_name:
-	IMiniportAudioEngineNode.GetDeviceChannelMute
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IMiniportAudioEngineNode::GetDeviceChannelMute method


## -description


Gets the state of the Mute node for the audio device channel.


## -parameters




### -param ulNodeId [in]

The ID for the node that represents the audio device.


### -param ulChannel [in]

The audio device channel.


### -param pbMute [out]

The current state of the Mute node for the audio device channel.


## -returns



<b>GetDeviceChannelMute</b> returns S_OK, if the call was successful. Otherwise, the method returns an appropriate error 

code.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn302040">IMiniportAudioEngineNode</a>
 

 

