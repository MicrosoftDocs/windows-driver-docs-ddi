---
UID: NF:portcls.IMiniportAudioEngineNode.GetGfxState
title: IMiniportAudioEngineNode::GetGfxState
author: windows-driver-content
description: Gets the state of the global effects (GFX) node in the audio engine.
old-location: audio\iminiportaudioenginenode_getgfxstate.htm
old-project: audio
ms.assetid: C2D4EB3E-0A39-4458-B0E7-C6D943AB4203
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: GetGfxState, GetGfxState method [Audio Devices], GetGfxState method [Audio Devices],IMiniportAudioEngineNode interface, IMiniportAudioEngineNode interface [Audio Devices],GetGfxState method, IMiniportAudioEngineNode.GetGfxState, IMiniportAudioEngineNode::GetGfxState, audio.iminiportaudioenginenode_getgfxstate, portcls/IMiniportAudioEngineNode::GetGfxState
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
-	IMiniportAudioEngineNode.GetGfxState
product:
- Windows
targetos: Windows
req.typenames: 
---

# IMiniportAudioEngineNode::GetGfxState


## -description


Gets the state of the global effects (GFX) node in the audio engine.


## -parameters




### -param ulNodeId [in]

The ID of the GFX node.


### -param pbEnable [out]

Pointer to a <b>BOOL</b> data type.


## -returns



<b>GetGfxState</b> returns S_OK if the call was successful. Otherwise, the method returns an appropriate error code.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn302040">IMiniportAudioEngineNode</a>
 

 

