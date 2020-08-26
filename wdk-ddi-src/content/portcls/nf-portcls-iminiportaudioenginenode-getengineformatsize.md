---
UID: NF:portcls.IMiniportAudioEngineNode.GetEngineFormatSize
title: IMiniportAudioEngineNode::GetEngineFormatSize (portcls.h)
description: Gets the format type and the buffer size for the audio engine's audio data format.
old-location: audio\iminiportaudioenginenode_getengineformatsize.htm
tech.root: audio
ms.assetid: 0874EC25-3ABE-410B-B5AC-E98020378D7E
ms.date: 05/08/2018
keywords: ["IMiniportAudioEngineNode::GetEngineFormatSize"]
ms.keywords: GetEngineFormatSize, GetEngineFormatSize method [Audio Devices], GetEngineFormatSize method [Audio Devices],IMiniportAudioEngineNode interface, IMiniportAudioEngineNode interface [Audio Devices],GetEngineFormatSize method, IMiniportAudioEngineNode.GetEngineFormatSize, IMiniportAudioEngineNode::GetEngineFormatSize, audio.iminiportaudioenginenode_getengineformatsize, portcls/IMiniportAudioEngineNode::GetEngineFormatSize
f1_keywords:
 - "portcls/IMiniportAudioEngineNode.GetEngineFormatSize"
 - "IMiniportAudioEngineNode.GetEngineFormatSize"
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
- IMiniportAudioEngineNode.GetEngineFormatSize
targetos: Windows
req.typenames: 
---

# IMiniportAudioEngineNode::GetEngineFormatSize


## -description


Gets the format type and the buffer size for the audio engine's audio data format.


## -parameters




### -param ulNodeId 
[in]
The ID of the audio engine node.


### -param formatType 
[in]
An enum of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/ne-portcls-eengineformattype">eEngineFormatType</a> that represents the audio data format type.


### -param pulFormatSize 
[out]
The data buffer size for the format type.


## -returns



<b>GetEngineFormatSize</b> returns S_OK, if the call was successful. Otherwise, the method returns an appropriate error code.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nn-portcls-iminiportaudioenginenode">IMiniportAudioEngineNode</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/ne-portcls-eengineformattype">eEngineFormatType</a>
 

 

