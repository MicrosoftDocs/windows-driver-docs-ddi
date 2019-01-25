---
UID: NF:portcls.IMiniportStreamAudioEngineNode.GetStreamChannelCount
title: IMiniportStreamAudioEngineNode::GetStreamChannelCount (portcls.h)
description: Gets a count of the number of channels available for the stream.
old-location: audio\iminiportstreamaudioenginenode_getstreamchannelcount.htm
tech.root: audio
ms.assetid: D39376D8-CD1D-4E07-8017-0B552A4D2E59
ms.date: 05/08/2018
ms.keywords: GetStreamChannelCount, GetStreamChannelCount method [Audio Devices], GetStreamChannelCount method [Audio Devices],IMiniportStreamAudioEngineNode interface, IMiniportStreamAudioEngineNode interface [Audio Devices],GetStreamChannelCount method, IMiniportStreamAudioEngineNode.GetStreamChannelCount, IMiniportStreamAudioEngineNode::GetStreamChannelCount, audio.iminiportstreamaudioenginenode_getstreamchannelcount, portcls/IMiniportStreamAudioEngineNode::GetStreamChannelCount
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
-	IMiniportStreamAudioEngineNode.GetStreamChannelCount
product:
- Windows
targetos: Windows
req.typenames: 
---

# IMiniportStreamAudioEngineNode::GetStreamChannelCount


## -description


Gets a count of the number of channels available for the stream.


## -parameters




### -param targetType [in]

An <a href="https://msdn.microsoft.com/library/windows/hardware/dn302034">eChannelTargetType</a> enumerated value that specifies the  target node type.


### -param pulChannelCount [out]

The number of available channels.


## -returns



<b>GetStreamChannelCount</b> returns S_OK, if the call was successful. Otherwise, the method returns an appropriate error 

code.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn265090">IMiniportStreamAudioEngineNode</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn302034">eChannelTargetType</a>
 

 

