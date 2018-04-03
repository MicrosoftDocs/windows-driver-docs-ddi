---
UID: NF:portcls.IMiniportAudioEngineNode.GetDeviceChannelVolume
title: IMiniportAudioEngineNode::GetDeviceChannelVolume method
author: windows-driver-content
description: Gets the volume level for a given channel of the audio device.
old-location: audio\iminiportaudioenginenode_getdevicechannelvolume.htm
old-project: audio
ms.assetid: 195AAD37-6993-4F0A-BEF7-848122402742
ms.author: windowsdriverdev
ms.date: 3/19/2018
ms.keywords: GetDeviceChannelVolume method [Audio Devices], GetDeviceChannelVolume method [Audio Devices], IMiniportAudioEngineNode interface, GetDeviceChannelVolume,IMiniportAudioEngineNode.GetDeviceChannelVolume, IMiniportAudioEngineNode, IMiniportAudioEngineNode interface [Audio Devices], GetDeviceChannelVolume method, IMiniportAudioEngineNode::GetDeviceChannelVolume, audio.iminiportaudioenginenode_getdevicechannelvolume, portcls/IMiniportAudioEngineNode::GetDeviceChannelVolume
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
-	IMiniportAudioEngineNode.GetDeviceChannelVolume
product:
- Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IMiniportAudioEngineNode::GetDeviceChannelVolume method


## -description


Gets the volume level for a given channel of the audio device.


## -parameters




### -param ulNodeId [in]

The ID for the node that represents the audio device.


### -param ulChannel [in]

The audio device channel.


### -param plVolume [out]

The current volume level for the audio device channel.


## -returns



<b>GetDeviceChannelVolume</b> returns S_OK, if the call was successful. Otherwise, the method returns an appropriate error 

code.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn302040">IMiniportAudioEngineNode</a>
 

 

