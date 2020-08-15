---
UID: NF:portcls.IMiniportStreamAudioEngineNode.GetStreamPresentationPosition
title: IMiniportStreamAudioEngineNode::GetStreamPresentationPosition (portcls.h)
description: Gets the current cursor position in the audio data stream that is being rendered to the endpoint.
old-location: audio\iminiportstreamaudioenginenode_getstreampresentationposition.htm
tech.root: audio
ms.assetid: 872A4445-8E0B-4804-ADDC-8CD9608E3EBF
ms.date: 05/08/2018
keywords: ["IMiniportStreamAudioEngineNode::GetStreamPresentationPosition"]
ms.keywords: GetStreamPresentationPosition, GetStreamPresentationPosition method [Audio Devices], GetStreamPresentationPosition method [Audio Devices],IMiniportStreamAudioEngineNode interface, IMiniportStreamAudioEngineNode interface [Audio Devices],GetStreamPresentationPosition method, IMiniportStreamAudioEngineNode.GetStreamPresentationPosition, IMiniportStreamAudioEngineNode::GetStreamPresentationPosition, audio.iminiportstreamaudioenginenode_getstreampresentationposition, portcls/IMiniportStreamAudioEngineNode::GetStreamPresentationPosition
f1_keywords:
 - "portcls/IMiniportStreamAudioEngineNode.GetStreamPresentationPosition"
 - "IMiniportStreamAudioEngineNode.GetStreamPresentationPosition"
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
- IMiniportStreamAudioEngineNode.GetStreamPresentationPosition
targetos: Windows
req.typenames: 
---

# IMiniportStreamAudioEngineNode::GetStreamPresentationPosition


## -description


Gets the current cursor position in the audio data stream that is being rendered to the endpoint.


## -parameters




### -param pPresentationPosition 
[out]
A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-ksaudio_presentation_position">KSAUDIO_PRESENTATION_POSITION</a> structure that represents the current cursor position in the audio data stream.


## -returns



<b>GetStreamPresentationPosition</b> returns S_OK, if the call was successful. Otherwise, the method returns an appropriate error 

code.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nn-portcls-iminiportstreamaudioenginenode">IMiniportStreamAudioEngineNode</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-ksaudio_presentation_position">KSAUDIO_PRESENTATION_POSITION</a>
 

 

