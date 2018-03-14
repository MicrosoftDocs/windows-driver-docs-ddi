---
UID: NF:portcls.IMiniportStreamAudioEngineNode.GetStreamPresentationPosition
title: IMiniportStreamAudioEngineNode::GetStreamPresentationPosition method
author: windows-driver-content
description: Gets the current cursor position in the audio data stream that is being rendered to the endpoint.
old-location: audio\iminiportstreamaudioenginenode_getstreampresentationposition.htm
old-project: audio
ms.assetid: 872A4445-8E0B-4804-ADDC-8CD9608E3EBF
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: GetStreamPresentationPosition method [Audio Devices], GetStreamPresentationPosition method [Audio Devices], IMiniportStreamAudioEngineNode interface, GetStreamPresentationPosition,IMiniportStreamAudioEngineNode.GetStreamPresentationPosition, IMiniportStreamAudioEngineNode, IMiniportStreamAudioEngineNode interface [Audio Devices], GetStreamPresentationPosition method, IMiniportStreamAudioEngineNode::GetStreamPresentationPosition, audio.iminiportstreamaudioenginenode_getstreampresentationposition, portcls/IMiniportStreamAudioEngineNode::GetStreamPresentationPosition
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
-	IMiniportStreamAudioEngineNode.GetStreamPresentationPosition
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IMiniportStreamAudioEngineNode::GetStreamPresentationPosition method


## -description


Gets the current cursor position in the audio data stream that is being rendered to the endpoint.


## -syntax


````
NTSTATUS GetStreamPresentationPosition(
  [out] KSAUDIO_PRESENTATION_POSITION *pPresentationPosition
);
````


## -parameters




### -param pPresentationPosition [out]

A <a href="..\ksmedia\ns-ksmedia-ksaudio_presentation_position.md">KSAUDIO_PRESENTATION_POSITION</a> structure that represents the current cursor position in the audio data stream.


## -returns



<b>GetStreamPresentationPosition</b> returns S_OK, if the call was successful. Otherwise, the method returns an appropriate error 

code.




## -see-also

<a href="..\portcls\nn-portcls-iminiportstreamaudioenginenode.md">IMiniportStreamAudioEngineNode</a>



<a href="..\ksmedia\ns-ksmedia-ksaudio_presentation_position.md">KSAUDIO_PRESENTATION_POSITION</a>



 

 


