---
UID: NF:portcls.IMiniportStreamAudioEngineNode.GetStreamChannelPeakMeter
title: IMiniportStreamAudioEngineNode::GetStreamChannelPeakMeter method
author: windows-driver-content
description: Gets the value of the PeakMeter node in the path of the audio stream.
old-location: audio\iminiportstreamaudioenginenode_getstreamchannelpeakmeter.htm
old-project: audio
ms.assetid: 69860DFE-DDA6-4889-B796-CEAEE59A10CC
ms.author: windowsdriverdev
ms.date: 3/19/2018
ms.keywords: GetStreamChannelPeakMeter method [Audio Devices], GetStreamChannelPeakMeter method [Audio Devices], IMiniportStreamAudioEngineNode interface, GetStreamChannelPeakMeter,IMiniportStreamAudioEngineNode.GetStreamChannelPeakMeter, IMiniportStreamAudioEngineNode, IMiniportStreamAudioEngineNode interface [Audio Devices], GetStreamChannelPeakMeter method, IMiniportStreamAudioEngineNode::GetStreamChannelPeakMeter, audio.iminiportstreamaudioenginenode_getstreamchannelpeakmeter, portcls/IMiniportStreamAudioEngineNode::GetStreamChannelPeakMeter
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
-	IMiniportStreamAudioEngineNode.GetStreamChannelPeakMeter
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IMiniportStreamAudioEngineNode::GetStreamChannelPeakMeter method


## -description


Gets the value of the PeakMeter node in the path of the audio stream.


## -parameters




### -param ulChannel [in]

The channel of the audio stream.


### -param plPeakMeter [out]

The PeakMeter value.


## -returns



<b>GetStreamChannelPeakMeter</b> returns S_OK, if the call was successful. Otherwise, the method returns an appropriate error 

code.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn265090">IMiniportStreamAudioEngineNode</a>
 

 

