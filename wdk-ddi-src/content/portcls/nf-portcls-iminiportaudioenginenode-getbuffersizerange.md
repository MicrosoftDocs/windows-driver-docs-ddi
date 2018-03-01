---
UID: NF:portcls.IMiniportAudioEngineNode.GetBufferSizeRange
title: IMiniportAudioEngineNode::GetBufferSizeRange method
author: windows-driver-content
description: Gets the minimum and maximum buffer size that the hardware audio engine can support.
old-location: audio\iminiportaudioenginenode_getbuffersizerange.htm
old-project: audio
ms.assetid: 75CBDD4F-618F-4618-9D53-4A8DF40992B0
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: GetBufferSizeRange method [Audio Devices], GetBufferSizeRange method [Audio Devices], IMiniportAudioEngineNode interface, GetBufferSizeRange,IMiniportAudioEngineNode.GetBufferSizeRange, IMiniportAudioEngineNode, IMiniportAudioEngineNode interface [Audio Devices], GetBufferSizeRange method, IMiniportAudioEngineNode::GetBufferSizeRange, audio.iminiportaudioenginenode_getbuffersizerange, portcls/IMiniportAudioEngineNode::GetBufferSizeRange
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
-	IMiniportAudioEngineNode.GetBufferSizeRange
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IMiniportAudioEngineNode::GetBufferSizeRange method


## -description


Gets the minimum and maximum buffer size that the hardware audio engine can support.


## -syntax


````
NTSTATUS GetBufferSizeRange(
  [in]  ULONG                           ulNodeId,
  [in]  KSDATAFORMAT_WAVEFORMATEX       *pKsDataFormatWfx,
  [out] KSAUDIOENGINE_BUFFER_SIZE_RANGE *pBufferSizeRange
);
````


## -parameters




### -param ulNodeId [in]

The ID for the node that represents the audio device.


### -param pKsDataFormatWfx [in]

A <a href="..\ksmedia\ns-ksmedia-ksdataformat_waveformatex.md">KSDATAFORMAT_WAVEFORMATEX</a> structure that represents the audio data format for the audio device.


### -param pBufferSizeRange [out]

A <a href="..\ksmedia\ns-ksmedia-_tagksaudioengine_buffer_size_range.md">KSAUDIOENGINE_BUFFER_SIZE_RANGE</a> structure that represents the minimum and maximum buffer size that the hardware audio engine can support at the time when it is called.


## -returns



<b>GetBufferSizeRange</b> returns S_OK, if the call was successful. Otherwise, the method returns an appropriate error 

code.




## -see-also

<a href="..\portcls\nn-portcls-iminiportaudioenginenode.md">IMiniportAudioEngineNode</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IMiniportAudioEngineNode::GetBufferSizeRange method%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

