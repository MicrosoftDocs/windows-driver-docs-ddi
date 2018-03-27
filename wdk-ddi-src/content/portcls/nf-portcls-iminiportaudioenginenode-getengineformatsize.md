---
UID: NF:portcls.IMiniportAudioEngineNode.GetEngineFormatSize
title: IMiniportAudioEngineNode::GetEngineFormatSize method
author: windows-driver-content
description: Gets the format type and the buffer size for the audio engine's audio data format.
old-location: audio\iminiportaudioenginenode_getengineformatsize.htm
old-project: audio
ms.assetid: 0874EC25-3ABE-410B-B5AC-E98020378D7E
ms.author: windowsdriverdev
ms.date: 3/19/2018
ms.keywords: GetEngineFormatSize method [Audio Devices], GetEngineFormatSize method [Audio Devices], IMiniportAudioEngineNode interface, GetEngineFormatSize,IMiniportAudioEngineNode.GetEngineFormatSize, IMiniportAudioEngineNode, IMiniportAudioEngineNode interface [Audio Devices], GetEngineFormatSize method, IMiniportAudioEngineNode::GetEngineFormatSize, audio.iminiportaudioenginenode_getengineformatsize, portcls/IMiniportAudioEngineNode::GetEngineFormatSize
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
-	IMiniportAudioEngineNode.GetEngineFormatSize
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IMiniportAudioEngineNode::GetEngineFormatSize method


## -description


Gets the format type and the buffer size for the audio engine's audio data format.


## -parameters




### -param ulNodeId [in]

The ID of the audio engine node.


### -param formatType [in]

An enum of type <a href="https://msdn.microsoft.com/library/windows/hardware/dn302035">eEngineFormatType</a> that represents the audio data format type.


### -param pulFormatSize [out]

The data buffer size for the format type.


## -returns



<b>GetEngineFormatSize</b> returns S_OK, if the call was successful. Otherwise, the method returns an appropriate error code.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn302040">IMiniportAudioEngineNode</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn302035">eEngineFormatType</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IMiniportAudioEngineNode::GetEngineFormatSize method%20 RELEASE:%20(3/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

