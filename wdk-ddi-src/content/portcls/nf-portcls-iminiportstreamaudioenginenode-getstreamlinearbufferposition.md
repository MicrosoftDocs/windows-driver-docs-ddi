---
UID: NF:portcls.IMiniportStreamAudioEngineNode.GetStreamLinearBufferPosition
title: IMiniportStreamAudioEngineNode::GetStreamLinearBufferPosition (portcls.h)
description: Gets the number of bytes that the DMA has fetched from the audio buffer since the beginning of the stream.
old-location: audio\iminiportstreamaudioenginenode_getstreamlinearbufferposition.htm
tech.root: audio
ms.date: 05/08/2018
keywords: ["IMiniportStreamAudioEngineNode::GetStreamLinearBufferPosition"]
ms.keywords: GetStreamLinearBufferPosition, GetStreamLinearBufferPosition method [Audio Devices], GetStreamLinearBufferPosition method [Audio Devices],IMiniportStreamAudioEngineNode interface, IMiniportStreamAudioEngineNode interface [Audio Devices],GetStreamLinearBufferPosition method, IMiniportStreamAudioEngineNode.GetStreamLinearBufferPosition, IMiniportStreamAudioEngineNode::GetStreamLinearBufferPosition, audio.iminiportstreamaudioenginenode_getstreamlinearbufferposition, portcls/IMiniportStreamAudioEngineNode::GetStreamLinearBufferPosition
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
 - IMiniportStreamAudioEngineNode::GetStreamLinearBufferPosition
 - portcls/IMiniportStreamAudioEngineNode::GetStreamLinearBufferPosition
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Portcls.h
api_name:
 - IMiniportStreamAudioEngineNode.GetStreamLinearBufferPosition
---

# IMiniportStreamAudioEngineNode::GetStreamLinearBufferPosition


## -description

	Gets the number of bytes that the DMA has fetched from the audio buffer since the beginning of the stream.

## -parameters

### -param pullLinearBufferPosition 

[out]
The number of bytes that the DMA has fetched.

## -returns

<b>GetStreamLinearBufferPosition</b> returns S_OK, if the call was successful. Otherwise, the method returns an appropriate error code.

## -see-also

<a href="/windows-hardware/drivers/ddi/portcls/nn-portcls-iminiportstreamaudioenginenode">IMiniportStreamAudioEngineNode</a>
