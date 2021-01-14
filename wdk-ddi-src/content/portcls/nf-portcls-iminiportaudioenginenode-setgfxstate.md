---
UID: NF:portcls.IMiniportAudioEngineNode.SetGfxState
title: IMiniportAudioEngineNode::SetGfxState (portcls.h)
description: Sets the state of the global effects (GFX) node in the audio engine.
old-location: audio\iminiportaudioenginenode_setgfxstate.htm
tech.root: audio
ms.date: 05/08/2018
keywords: ["IMiniportAudioEngineNode::SetGfxState"]
ms.keywords: IMiniportAudioEngineNode interface [Audio Devices],SetGfxState method, IMiniportAudioEngineNode.SetGfxState, IMiniportAudioEngineNode::SetGfxState, SetGfxState, SetGfxState method [Audio Devices], SetGfxState method [Audio Devices],IMiniportAudioEngineNode interface, audio.iminiportaudioenginenode_setgfxstate, portcls/IMiniportAudioEngineNode::SetGfxState
req.header: portcls.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
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
 - IMiniportAudioEngineNode::SetGfxState
 - portcls/IMiniportAudioEngineNode::SetGfxState
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - portcls.h
api_name:
 - IMiniportAudioEngineNode::SetGfxState
---

# IMiniportAudioEngineNode::SetGfxState


## -description

Sets the state of the global effects (GFX) node in the audio engine.

## -parameters

### -param ulNodeId 

[in]
The ID of the GFX node.

### -param bEnable 

[in]
The state of the GFX node.

## -returns

<b>SetGfxState</b> returns S_OK, if the call was successful. Otherwise, the method returns an appropriate error code.

## -see-also

<a href="/windows-hardware/drivers/ddi/portcls/nn-portcls-iminiportaudioenginenode">IMiniportAudioEngineNode</a>

