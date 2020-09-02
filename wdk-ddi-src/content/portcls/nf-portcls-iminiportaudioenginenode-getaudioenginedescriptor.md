---
UID: NF:portcls.IMiniportAudioEngineNode.GetAudioEngineDescriptor
title: IMiniportAudioEngineNode::GetAudioEngineDescriptor (portcls.h)
description: Gets the descriptor for the audio engine node.
old-location: audio\iminiportaudioenginenode_getaudioenginedescriptor.htm
tech.root: audio
ms.assetid: B8D09AB4-1F36-44E1-8D4F-33E7E4DBBFE3
ms.date: 05/08/2018
keywords: ["IMiniportAudioEngineNode::GetAudioEngineDescriptor"]
ms.keywords: GetAudioEngineDescriptor, GetAudioEngineDescriptor method [Audio Devices], GetAudioEngineDescriptor method [Audio Devices],IMiniportAudioEngineNode interface, IMiniportAudioEngineNode interface [Audio Devices],GetAudioEngineDescriptor method, IMiniportAudioEngineNode.GetAudioEngineDescriptor, IMiniportAudioEngineNode::GetAudioEngineDescriptor, audio.iminiportaudioenginenode_getaudioenginedescriptor, portcls/IMiniportAudioEngineNode::GetAudioEngineDescriptor
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
 - IMiniportAudioEngineNode::GetAudioEngineDescriptor
 - portcls/IMiniportAudioEngineNode::GetAudioEngineDescriptor
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Portcls.h
api_name:
 - IMiniportAudioEngineNode.GetAudioEngineDescriptor
---

# IMiniportAudioEngineNode::GetAudioEngineDescriptor


## -description

Gets the descriptor for the audio engine node.

## -parameters

### -param ulNodeId 

[in]
The ID of the audio engine node.

### -param pAudioEngineDescriptor 

[out]
Audio engine descriptor object. This parameter is of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-_tagksaudioengine_descriptor">KSAUDIOENGINE_DESCRIPTOR</a>.

## -returns

<b>GetAudioEngineDescriptor</b> returns S_OK if the call was successful. Otherwise, the method returns an appropriate error code.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nn-portcls-iminiportaudioenginenode">IMiniportAudioEngineNode</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-_tagksaudioengine_descriptor">KSAUDIOENGINE_DESCRIPTOR</a>

