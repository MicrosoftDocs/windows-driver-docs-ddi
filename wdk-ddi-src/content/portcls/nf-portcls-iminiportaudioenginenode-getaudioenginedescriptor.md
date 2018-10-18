---
UID: NF:portcls.IMiniportAudioEngineNode.GetAudioEngineDescriptor
title: IMiniportAudioEngineNode::GetAudioEngineDescriptor
author: windows-driver-content
description: Gets the descriptor for the audio engine node.
old-location: audio\iminiportaudioenginenode_getaudioenginedescriptor.htm
tech.root: audio
ms.assetid: B8D09AB4-1F36-44E1-8D4F-33E7E4DBBFE3
ms.date: 5/8/2018
ms.keywords: GetAudioEngineDescriptor, GetAudioEngineDescriptor method [Audio Devices], GetAudioEngineDescriptor method [Audio Devices],IMiniportAudioEngineNode interface, IMiniportAudioEngineNode interface [Audio Devices],GetAudioEngineDescriptor method, IMiniportAudioEngineNode.GetAudioEngineDescriptor, IMiniportAudioEngineNode::GetAudioEngineDescriptor, audio.iminiportaudioenginenode_getaudioenginedescriptor, portcls/IMiniportAudioEngineNode::GetAudioEngineDescriptor
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
-	IMiniportAudioEngineNode.GetAudioEngineDescriptor
product:
- Windows
targetos: Windows
req.typenames: 
---

# IMiniportAudioEngineNode::GetAudioEngineDescriptor


## -description


Gets the descriptor for the audio engine node.


## -parameters




### -param ulNodeId [in]

The ID of the audio engine node.


### -param pAudioEngineDescriptor [out]

Audio engine descriptor object. This parameter is of type <a href="https://msdn.microsoft.com/library/windows/hardware/hh450862">KSAUDIOENGINE_DESCRIPTOR</a>.


## -returns



<b>GetAudioEngineDescriptor</b> returns S_OK if the call was successful. Otherwise, the method returns an appropriate error code.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn302040">IMiniportAudioEngineNode</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh450862">KSAUDIOENGINE_DESCRIPTOR</a>
 

 

