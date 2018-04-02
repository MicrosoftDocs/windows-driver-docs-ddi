---
UID: NF:portcls.IMiniportAudioEngineNode.GetDeviceFormat
title: IMiniportAudioEngineNode::GetDeviceFormat method
author: windows-driver-content
description: Gets the audio data format for an audio device.
old-location: audio\iminiportaudioenginenode_getdeviceformat.htm
old-project: audio
ms.assetid: 6EA01AE7-E5D5-4182-862D-2901185C2BF8
ms.author: windowsdriverdev
ms.date: 3/19/2018
ms.keywords: GetDeviceFormat method [Audio Devices], GetDeviceFormat method [Audio Devices], IMiniportAudioEngineNode interface, GetDeviceFormat,IMiniportAudioEngineNode.GetDeviceFormat, IMiniportAudioEngineNode, IMiniportAudioEngineNode interface [Audio Devices], GetDeviceFormat method, IMiniportAudioEngineNode::GetDeviceFormat, audio.iminiportaudioenginenode_getdeviceformat, portcls/IMiniportAudioEngineNode::GetDeviceFormat
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
-	IMiniportAudioEngineNode.GetDeviceFormat
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IMiniportAudioEngineNode::GetDeviceFormat method


## -description


Gets the audio data format for an audio device.


## -parameters




### -param ulNodeId [in]

The ID of the device node.


### -param pFormat [out]

A structure of type  <a href="https://msdn.microsoft.com/library/windows/hardware/ff537095">KSDATAFORMAT_WAVEFORMATEX</a> that represents the audio data format for the device.


### -param ulBufferSize [in]

The audio data buffer size.


## -returns



<b>GetDeviceFormat</b> returns S_OK, if the call was successful. Otherwise, the method 

returns an appropriate error code.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn302040">IMiniportAudioEngineNode</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537095">KSDATAFORMAT_WAVEFORMATEX</a>
 

 

