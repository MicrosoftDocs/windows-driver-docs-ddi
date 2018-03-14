---
UID: NF:portcls.IMiniportStreamAudioEngineNode.SetStreamCurrentWritePosition
title: IMiniportStreamAudioEngineNode::SetStreamCurrentWritePosition method
author: windows-driver-content
description: Sets the current cursor position in the audio data stream that is being captured from the endpoint.
old-location: audio\iminiportstreamaudioenginenode_setstreamcurrentwriteposition.htm
old-project: audio
ms.assetid: A277FC29-AB92-4D67-9E53-F8E8B36053F9
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: IMiniportStreamAudioEngineNode, IMiniportStreamAudioEngineNode interface [Audio Devices], SetStreamCurrentWritePosition method, IMiniportStreamAudioEngineNode::SetStreamCurrentWritePosition, SetStreamCurrentWritePosition method [Audio Devices], SetStreamCurrentWritePosition method [Audio Devices], IMiniportStreamAudioEngineNode interface, SetStreamCurrentWritePosition,IMiniportStreamAudioEngineNode.SetStreamCurrentWritePosition, audio.iminiportstreamaudioenginenode_setstreamcurrentwriteposition, portcls/IMiniportStreamAudioEngineNode::SetStreamCurrentWritePosition
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
-	IMiniportStreamAudioEngineNode.SetStreamCurrentWritePosition
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IMiniportStreamAudioEngineNode::SetStreamCurrentWritePosition method


## -description


Sets the current cursor position in the audio data stream that is being captured from the endpoint.


## -syntax


````
NTSTATUS SetStreamCurrentWritePosition(
  [in] ULONG ulCurrentWritePosition
);
````


## -parameters




### -param ulCurrentWritePosition [in]

The current cursor position in the audio data stream.


## -returns



<b>SetStreamCurrentWritePosition</b> returns S_OK, if the call was successful. Otherwise, the method returns an appropriate error code.




## -see-also

<a href="..\portcls\nn-portcls-iminiportstreamaudioenginenode.md">IMiniportStreamAudioEngineNode</a>



 

 


