---
UID: NF:portcls.IMiniportAudioEngineNode.GetDeviceChannelCount
title: IMiniportAudioEngineNode::GetDeviceChannelCount (portcls.h)
description: Gets a count of the number of channels supported by the audio device.
old-location: audio\iminiportaudioenginenode_getdevicechannelcount.htm
tech.root: audio
ms.assetid: 978193AE-55CD-4255-8722-A1E008E98F08
ms.date: 05/08/2018
ms.keywords: GetDeviceChannelCount, GetDeviceChannelCount method [Audio Devices], GetDeviceChannelCount method [Audio Devices],IMiniportAudioEngineNode interface, IMiniportAudioEngineNode interface [Audio Devices],GetDeviceChannelCount method, IMiniportAudioEngineNode.GetDeviceChannelCount, IMiniportAudioEngineNode::GetDeviceChannelCount, audio.iminiportaudioenginenode_getdevicechannelcount, portcls/IMiniportAudioEngineNode::GetDeviceChannelCount
ms.topic: method
f1_keywords:
 - "portcls/IMiniportAudioEngineNode.GetDeviceChannelCount"
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
- IMiniportAudioEngineNode.GetDeviceChannelCount
product:
- Windows
targetos: Windows
req.typenames: 
---

# IMiniportAudioEngineNode::GetDeviceChannelCount


## -description


Gets a count of the number of channels supported by the audio device.


## -parameters




### -param ulNodeId [in]

The ID of the node that represents the audio device.


### -param targetType [in]

An <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/ne-portcls-echanneltargettype">eChannelTargetType</a> enumerated value that specifies the types of target nodes in the channels. For example, there could be Volume, Mute or PeakMeter nodes.


### -param pulChannelCount [out]

The number of channels supported by the audio device.


## -returns



<b>GetDeviceChannelCount</b> returns S_OK, if the call was successful. Otherwise, the method 

returns an appropriate error code.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/nn-portcls-iminiportaudioenginenode">IMiniportAudioEngineNode</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/ne-portcls-echanneltargettype">eChannelTargetType</a>
 

 

