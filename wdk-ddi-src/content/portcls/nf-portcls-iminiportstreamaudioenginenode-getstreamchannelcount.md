---
UID: NF:portcls.IMiniportStreamAudioEngineNode.GetStreamChannelCount
title: IMiniportStreamAudioEngineNode::GetStreamChannelCount (portcls.h)
description: Gets a count of the number of channels available for the stream.
old-location: audio\iminiportstreamaudioenginenode_getstreamchannelcount.htm
tech.root: audio
ms.date: 05/08/2018
keywords: ["IMiniportStreamAudioEngineNode::GetStreamChannelCount"]
ms.keywords: GetStreamChannelCount, GetStreamChannelCount method [Audio Devices], GetStreamChannelCount method [Audio Devices],IMiniportStreamAudioEngineNode interface, IMiniportStreamAudioEngineNode interface [Audio Devices],GetStreamChannelCount method, IMiniportStreamAudioEngineNode.GetStreamChannelCount, IMiniportStreamAudioEngineNode::GetStreamChannelCount, audio.iminiportstreamaudioenginenode_getstreamchannelcount, portcls/IMiniportStreamAudioEngineNode::GetStreamChannelCount
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
 - IMiniportStreamAudioEngineNode::GetStreamChannelCount
 - portcls/IMiniportStreamAudioEngineNode::GetStreamChannelCount
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Portcls.h
api_name:
 - IMiniportStreamAudioEngineNode.GetStreamChannelCount
---

# IMiniportStreamAudioEngineNode::GetStreamChannelCount


## -description

Gets a count of the number of channels available for the stream.

## -parameters

### -param targetType 

[in]
An <a href="/windows-hardware/drivers/ddi/portcls/ne-portcls-echanneltargettype">eChannelTargetType</a> enumerated value that specifies the  target node type.

### -param pulChannelCount 

[out]
The number of available channels.

## -returns

<b>GetStreamChannelCount</b> returns S_OK, if the call was successful. Otherwise, the method returns an appropriate error 

code.

## -see-also

<a href="/windows-hardware/drivers/ddi/portcls/nn-portcls-iminiportstreamaudioenginenode">IMiniportStreamAudioEngineNode</a>



<a href="/windows-hardware/drivers/ddi/portcls/ne-portcls-echanneltargettype">eChannelTargetType</a>
