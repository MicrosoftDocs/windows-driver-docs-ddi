---
UID: NF:portcls.IMiniportAudioEngineNode.SetGfxState
title: IMiniportAudioEngineNode::SetGfxState
author: windows-driver-content
description: Sets the state of the global effects (GFX) node in the audio engine.
old-location: audio\iminiportaudioenginenode_setgfxstate.htm
tech.root: audio
ms.assetid: B073D354-14FB-477E-BBD7-8BD282696EF4
ms.author: windowsdriverdev
ms.date: 5/8/2018
ms.keywords: IMiniportAudioEngineNode interface [Audio Devices],SetGfxState method, IMiniportAudioEngineNode.SetGfxState, IMiniportAudioEngineNode::SetGfxState, SetGfxState, SetGfxState method [Audio Devices], SetGfxState method [Audio Devices],IMiniportAudioEngineNode interface, audio.iminiportaudioenginenode_setgfxstate, portcls/IMiniportAudioEngineNode::SetGfxState
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	portcls.h
api_name:
-	IMiniportAudioEngineNode.SetGfxState
product:
- Windows
targetos: Windows
req.typenames: 
---

# IMiniportAudioEngineNode::SetGfxState


## -description


Sets the state of the global effects (GFX) node in the audio engine.


## -parameters




### -param ulNodeId [in]

The ID of the GFX node.


### -param bEnable [in]

The state of the GFX node.


## -returns



<b>SetGfxState</b> returns S_OK, if the call was successful. Otherwise, the method returns an appropriate error code.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn302040">IMiniportAudioEngineNode</a>
 

 

