---
UID: NF:portcls.IMiniportAudioEngineNode.GetDeviceChannelPeakMeter
title: IMiniportAudioEngineNode::GetDeviceChannelPeakMeter
author: windows-driver-content
description: Gets the PeakMeter value for the audio device channel.
old-location: audio\iminiportaudioenginenode_getdevicechannelpeakmeter.htm
tech.root: audio
ms.assetid: 31F291ED-0B04-4CDF-A83B-7CF3717EC234
ms.author: windowsdriverdev
ms.date: 5/8/2018
ms.keywords: GetDeviceChannelPeakMeter, GetDeviceChannelPeakMeter method [Audio Devices], GetDeviceChannelPeakMeter method [Audio Devices],IMiniportAudioEngineNode interface, IMiniportAudioEngineNode interface [Audio Devices],GetDeviceChannelPeakMeter method, IMiniportAudioEngineNode.GetDeviceChannelPeakMeter, IMiniportAudioEngineNode::GetDeviceChannelPeakMeter, audio.iminiportaudioenginenode_getdevicechannelpeakmeter, portcls/IMiniportAudioEngineNode::GetDeviceChannelPeakMeter
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
-	IMiniportAudioEngineNode.GetDeviceChannelPeakMeter
product:
- Windows
targetos: Windows
req.typenames: 
---

# IMiniportAudioEngineNode::GetDeviceChannelPeakMeter


## -description


Gets the PeakMeter value  for the audio device channel.


## -parameters




### -param ulNodeId [in]

The ID for the node that represents the audio device.


### -param ulChannel [in]

The audio device channel.


### -param plPeakMeter [out]

The PeakMeter value for the audio device channel.


## -returns



<b>GetDeviceChannelPeakMeter</b> returns S_OK, if the call was successful. Otherwise, the method returns an appropriate error 

code.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn302040">IMiniportAudioEngineNode</a>
 

 

