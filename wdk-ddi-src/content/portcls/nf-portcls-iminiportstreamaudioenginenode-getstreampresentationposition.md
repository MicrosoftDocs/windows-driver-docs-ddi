---
UID: NF:portcls.IMiniportStreamAudioEngineNode.GetStreamPresentationPosition
title: IMiniportStreamAudioEngineNode::GetStreamPresentationPosition method
author: windows-driver-content
description: Gets the current cursor position in the audio data stream that is being rendered to the endpoint.
old-location: audio\iminiportstreamaudioenginenode_getstreampresentationposition.htm
old-project: audio
ms.assetid: 872A4445-8E0B-4804-ADDC-8CD9608E3EBF
ms.author: windowsdriverdev
ms.date: 2/8/2018
ms.keywords: IMiniportStreamAudioEngineNode interface [Audio Devices], GetStreamPresentationPosition method, IMiniportStreamAudioEngineNode, GetStreamPresentationPosition method [Audio Devices], IMiniportStreamAudioEngineNode interface, GetStreamPresentationPosition method [Audio Devices], GetStreamPresentationPosition, portcls/IMiniportStreamAudioEngineNode::GetStreamPresentationPosition, audio.iminiportstreamaudioenginenode_getstreampresentationposition, IMiniportStreamAudioEngineNode::GetStreamPresentationPosition
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
-	IMiniportStreamAudioEngineNode.GetStreamPresentationPosition
product: Windows
targetos: Windows
req.typenames: "*PPC_EXIT_LATENCY, PC_EXIT_LATENCY"
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

<a href="..\ksmedia\ns-ksmedia-ksaudio_presentation_position.md">KSAUDIO_PRESENTATION_POSITION</a>



<a href="..\portcls\nn-portcls-iminiportstreamaudioenginenode.md">IMiniportStreamAudioEngineNode</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IMiniportStreamAudioEngineNode::GetStreamPresentationPosition method%20 RELEASE:%20(2/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

