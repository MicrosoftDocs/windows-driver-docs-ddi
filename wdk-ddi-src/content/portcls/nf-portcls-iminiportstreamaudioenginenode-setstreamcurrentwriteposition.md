---
UID: NF:portcls.IMiniportStreamAudioEngineNode.SetStreamCurrentWritePosition
title: IMiniportStreamAudioEngineNode::SetStreamCurrentWritePosition (portcls.h)
description: Sets the current cursor position in the audio data stream that is being captured from the endpoint.
old-location: audio\iminiportstreamaudioenginenode_setstreamcurrentwriteposition.htm
tech.root: audio
ms.assetid: A277FC29-AB92-4D67-9E53-F8E8B36053F9
ms.date: 05/08/2018
keywords: ["IMiniportStreamAudioEngineNode::SetStreamCurrentWritePosition"]
ms.keywords: IMiniportStreamAudioEngineNode interface [Audio Devices],SetStreamCurrentWritePosition method, IMiniportStreamAudioEngineNode.SetStreamCurrentWritePosition, IMiniportStreamAudioEngineNode::SetStreamCurrentWritePosition, SetStreamCurrentWritePosition, SetStreamCurrentWritePosition method [Audio Devices], SetStreamCurrentWritePosition method [Audio Devices],IMiniportStreamAudioEngineNode interface, audio.iminiportstreamaudioenginenode_setstreamcurrentwriteposition, portcls/IMiniportStreamAudioEngineNode::SetStreamCurrentWritePosition
f1_keywords:
 - "portcls/IMiniportStreamAudioEngineNode.SetStreamCurrentWritePosition"
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- Portcls.h
api_name:
- IMiniportStreamAudioEngineNode.SetStreamCurrentWritePosition
product:
- Windows
targetos: Windows
req.typenames: 
---

# IMiniportStreamAudioEngineNode::SetStreamCurrentWritePosition


## -description


Sets the current cursor position in the audio data stream that is being captured from the endpoint.


## -parameters




### -param ulCurrentWritePosition [in]

The current cursor position in the audio data stream.


## -returns



<b>SetStreamCurrentWritePosition</b> returns S_OK, if the call was successful. Otherwise, the method returns an appropriate error code.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nn-portcls-iminiportstreamaudioenginenode">IMiniportStreamAudioEngineNode</a>
 

 

