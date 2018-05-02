---
UID: NF:portcls.IMiniportAudioEngineNode.SetDeviceChannelMute
title: IMiniportAudioEngineNode::SetDeviceChannelMute
author: windows-driver-content
description: Sets the state of the Mute node for the audio device channel.
old-location: audio\iminiportaudioenginenode_setdevicechannelmute.htm
old-project: audio
ms.assetid: 272B83D4-AACE-419D-9DD7-A1AE1C8A931A
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: IMiniportAudioEngineNode interface [Audio Devices],SetDeviceChannelMute method, IMiniportAudioEngineNode.SetDeviceChannelMute, IMiniportAudioEngineNode::SetDeviceChannelMute, SetDeviceChannelMute, SetDeviceChannelMute method [Audio Devices], SetDeviceChannelMute method [Audio Devices],IMiniportAudioEngineNode interface, audio.iminiportaudioenginenode_setdevicechannelmute, portcls/IMiniportAudioEngineNode::SetDeviceChannelMute
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
-	IMiniportAudioEngineNode.SetDeviceChannelMute
product:
- Windows
targetos: Windows
req.typenames: 
---

# IMiniportAudioEngineNode::SetDeviceChannelMute


## -description


Sets the state of the Mute node for the audio device channel.


## -parameters




### -param ulNodeId [in]

The ID for the node that represents the audio device.


### -param ulChannel [in]

The audio device channel.


### -param bMute [in]

The state to which the Mute node for the audio device channel will be set.


## -returns



<b>SetDeviceChannelMute</b> returns S_OK, if the call was successful. Otherwise, the method returns an appropriate error 

code.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn302040">IMiniportAudioEngineNode</a>
 

 

