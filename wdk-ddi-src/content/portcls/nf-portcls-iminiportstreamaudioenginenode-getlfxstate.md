---
UID: NF:portcls.IMiniportStreamAudioEngineNode.GetLfxState
title: IMiniportStreamAudioEngineNode::GetLfxState (portcls.h)
description: Gets the state of the local effects (LFX) node that is in the path of the audio stream.
old-location: audio\iminiportstreamaudioenginenode_getlfxstate.htm
tech.root: audio
ms.assetid: 2810D8B3-DDB7-4B55-839B-B2D079BDC0FC
ms.date: 05/08/2018
keywords: ["IMiniportStreamAudioEngineNode::GetLfxState"]
ms.keywords: GetLfxState, GetLfxState method [Audio Devices], GetLfxState method [Audio Devices],IMiniportStreamAudioEngineNode interface, IMiniportStreamAudioEngineNode interface [Audio Devices],GetLfxState method, IMiniportStreamAudioEngineNode.GetLfxState, IMiniportStreamAudioEngineNode::GetLfxState, audio.iminiportstreamaudioenginenode_getlfxstate, portcls/IMiniportStreamAudioEngineNode::GetLfxState
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
 - IMiniportStreamAudioEngineNode::GetLfxState
 - portcls/IMiniportStreamAudioEngineNode::GetLfxState
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Portcls.h
api_name:
 - IMiniportStreamAudioEngineNode.GetLfxState
---

# IMiniportStreamAudioEngineNode::GetLfxState


## -description

Gets the state of the local effects (LFX) node that is in the path of the audio stream.

## -parameters

### -param pbEnable 

[out]
The current state of the LFX node.

## -returns

<b>GetLfxState</b> returns S_OK, if the call was successful. Otherwise, the method returns an appropriate error 

code.

## -see-also

<a href="/windows-hardware/drivers/ddi/portcls/nn-portcls-iminiportstreamaudioenginenode">IMiniportStreamAudioEngineNode</a>