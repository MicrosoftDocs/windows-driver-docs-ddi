---
UID: NF:portcls.IMiniportAudioEngineNode.GetAudioEngineDescriptor
title: IMiniportAudioEngineNode::GetAudioEngineDescriptor method
author: windows-driver-content
description: Gets the descriptor for the audio engine node.
old-location: audio\iminiportaudioenginenode_getaudioenginedescriptor.htm
old-project: audio
ms.assetid: B8D09AB4-1F36-44E1-8D4F-33E7E4DBBFE3
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: GetAudioEngineDescriptor method [Audio Devices], GetAudioEngineDescriptor method [Audio Devices], IMiniportAudioEngineNode interface, GetAudioEngineDescriptor,IMiniportAudioEngineNode.GetAudioEngineDescriptor, IMiniportAudioEngineNode, IMiniportAudioEngineNode interface [Audio Devices], GetAudioEngineDescriptor method, IMiniportAudioEngineNode::GetAudioEngineDescriptor, audio.iminiportaudioenginenode_getaudioenginedescriptor, portcls/IMiniportAudioEngineNode::GetAudioEngineDescriptor
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	Portcls.h
api_name:
-	IMiniportAudioEngineNode.GetAudioEngineDescriptor
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IMiniportAudioEngineNode::GetAudioEngineDescriptor method


## -description


Gets the descriptor for the audio engine node.


## -syntax


````
NTSTATUS GetAudioEngineDescriptor(
  [in]  ULONG                    ulNodeId,
  [out] KSAUDIOENGINE_DESCRIPTOR *pAudioEngineDescriptor
);
````


## -parameters




### -param ulNodeId [in]

The ID of the audio engine node.


### -param pAudioEngineDescriptor [out]

Audio engine descriptor object. This parameter is of type <a href="..\ksmedia\ns-ksmedia-_tagksaudioengine_descriptor.md">KSAUDIOENGINE_DESCRIPTOR</a>.


## -returns



<b>GetAudioEngineDescriptor</b> returns S_OK if the call was successful. Otherwise, the method returns an appropriate error code.




## -see-also

<a href="..\ksmedia\ns-ksmedia-_tagksaudioengine_descriptor.md">KSAUDIOENGINE_DESCRIPTOR</a>



<a href="..\portcls\nn-portcls-iminiportaudioenginenode.md">IMiniportAudioEngineNode</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IMiniportAudioEngineNode::GetAudioEngineDescriptor method%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

