---
UID: NF:portcls.IMiniportStreamAudioEngineNode.GetLfxState
title: IMiniportStreamAudioEngineNode::GetLfxState method
author: windows-driver-content
description: Gets the state of the local effects (LFX) node that is in the path of the audio stream.
old-location: audio\iminiportstreamaudioenginenode_getlfxstate.htm
old-project: audio
ms.assetid: 2810D8B3-DDB7-4B55-839B-B2D079BDC0FC
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: audio.iminiportstreamaudioenginenode_getlfxstate, portcls/IMiniportStreamAudioEngineNode::GetLfxState, IMiniportStreamAudioEngineNode interface [Audio Devices], GetLfxState method, GetLfxState method [Audio Devices], GetLfxState, GetLfxState method [Audio Devices], IMiniportStreamAudioEngineNode interface, IMiniportStreamAudioEngineNode, IMiniportStreamAudioEngineNode::GetLfxState
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
-	IMiniportStreamAudioEngineNode.GetLfxState
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IMiniportStreamAudioEngineNode::GetLfxState method


## -description


Gets the state of the local effects (LFX) node that is in the path of the audio stream.


## -syntax


````
NTSTATUS GetLfxState(
  [out] BOOL *pbEnable
);
````


## -parameters




### -param pbEnable [out]

The current state of the LFX node.


## -returns



<b>GetLfxState</b> returns S_OK, if the call was successful. Otherwise, the method returns an appropriate error 

code.




## -see-also

<a href="..\portcls\nn-portcls-iminiportstreamaudioenginenode.md">IMiniportStreamAudioEngineNode</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IMiniportStreamAudioEngineNode::GetLfxState method%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

