---
UID: NF:portcls.IMiniportStreamAudioEngineNode.SetLfxState
title: IMiniportStreamAudioEngineNode::SetLfxState (portcls.h)
description: Sets the state of the local effects (LFX) node that is in the path of the audio stream.
old-location: audio\iminiportstreamaudioenginenode_setlfxstate.htm
tech.root: audio
ms.date: 05/08/2018
keywords: ["IMiniportStreamAudioEngineNode::SetLfxState"]
ms.keywords: IMiniportStreamAudioEngineNode interface [Audio Devices],SetLfxState method, IMiniportStreamAudioEngineNode.SetLfxState, IMiniportStreamAudioEngineNode::SetLfxState, SetLfxState, SetLfxState method [Audio Devices], SetLfxState method [Audio Devices],IMiniportStreamAudioEngineNode interface, audio.iminiportstreamaudioenginenode_setlfxstate, portcls/IMiniportStreamAudioEngineNode::SetLfxState
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
 - IMiniportStreamAudioEngineNode::SetLfxState
 - portcls/IMiniportStreamAudioEngineNode::SetLfxState
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Portcls.h
api_name:
 - IMiniportStreamAudioEngineNode::SetLfxState
---

# IMiniportStreamAudioEngineNode::SetLfxState


## -description

Sets the state of the local effects (LFX) node that is in the path of the audio stream.

## -parameters

### -param bEnable [in]


The state to which the LFX node will be set.

## -returns

<b>SetLfxState</b> returns S_OK, if the call was successful. Otherwise, the method returns an appropriate error 

code.

## -see-also

<a href="/windows-hardware/drivers/ddi/portcls/nn-portcls-iminiportstreamaudioenginenode">IMiniportStreamAudioEngineNode</a>

