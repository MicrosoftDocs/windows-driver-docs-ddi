---
UID: NF:portcls.IMiniportStreamAudioEngineNode.SetStreamChannelVolume
title: IMiniportStreamAudioEngineNode::SetStreamChannelVolume
author: windows-driver-content
description: Sets the volume level to be applied to the audio stream.
old-location: audio\iminiportstreamaudioenginenode_setstreamchannelvolume.htm
old-project: audio
ms.assetid: 0110979E-8C57-4394-B43E-BCC7B178A0AF
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: IMiniportStreamAudioEngineNode interface [Audio Devices],SetStreamChannelVolume method, IMiniportStreamAudioEngineNode.SetStreamChannelVolume, IMiniportStreamAudioEngineNode::SetStreamChannelVolume, SetStreamChannelVolume, SetStreamChannelVolume method [Audio Devices], SetStreamChannelVolume method [Audio Devices],IMiniportStreamAudioEngineNode interface, audio.iminiportstreamaudioenginenode_setstreamchannelvolume, portcls/IMiniportStreamAudioEngineNode::SetStreamChannelVolume
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
-	IMiniportStreamAudioEngineNode.SetStreamChannelVolume
product:
- Windows
targetos: Windows
req.typenames: 
---

# IMiniportStreamAudioEngineNode::SetStreamChannelVolume


## -description


Sets the volume level to be applied to the audio stream.


## -parameters




### -param Channel [in]

The audio stream channel.


### -param TargetVolume [in]

The volume level to be applied to the audio stream.


### -param CurveType [in]

The curve algorithm that will be used  to set the volume level. The curve types are represented by the members of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh831852">AUDIO_CURVE_TYPE</a> enum.


### -param CurveDuration [in]

The length of time over which the curve algorithm will be applied.


## -returns



<b>SetStreamChannelVolume</b> returns S_OK, if the call was successful. Otherwise, the method returns an appropriate error 

code.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn265090">IMiniportStreamAudioEngineNode</a>
 

 

