---
UID: NF:portcls.IMiniportAudioEngineNode.GetGfxState
title: IMiniportAudioEngineNode::GetGfxState method
author: windows-driver-content
description: Gets the state of the global effects (GFX) node in the audio engine.
old-location: audio\iminiportaudioenginenode_getgfxstate.htm
old-project: audio
ms.assetid: C2D4EB3E-0A39-4458-B0E7-C6D943AB4203
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: GetGfxState method [Audio Devices], GetGfxState method [Audio Devices], IMiniportAudioEngineNode interface, GetGfxState,IMiniportAudioEngineNode.GetGfxState, IMiniportAudioEngineNode, IMiniportAudioEngineNode interface [Audio Devices], GetGfxState method, IMiniportAudioEngineNode::GetGfxState, audio.iminiportaudioenginenode_getgfxstate, portcls/IMiniportAudioEngineNode::GetGfxState
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
req.lib: portcls.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	Portcls.h
apiname:
-	IMiniportAudioEngineNode.GetGfxState
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IMiniportAudioEngineNode::GetGfxState method


## -description


Gets the state of the global effects (GFX) node in the audio engine.


## -syntax


````
NTSTATUS GetGfxState(
  [in]  ULONG ulNodeId,
  [out] BOOL  *pbEnable
);
````


## -parameters




### -param ulNodeId [in]

The ID of the GFX node.


### -param pbEnable [out]

Pointer to a <b>BOOL</b> data type.


## -returns



<b>GetGfxState</b> returns S_OK if the call was successful. Otherwise, the method returns an appropriate error code.




## -see-also

<a href="..\portcls\nn-portcls-iminiportaudioenginenode.md">IMiniportAudioEngineNode</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IMiniportAudioEngineNode::GetGfxState method%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

