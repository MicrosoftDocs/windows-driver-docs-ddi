---
UID: NF:portcls.IMiniportAudioEngineNode.SetDeviceFormat
title: IMiniportAudioEngineNode::SetDeviceFormat method
author: windows-driver-content
description: Sets the audio data format for an audio device.
old-location: audio\iminiportaudioenginenode_setdeviceformat.htm
old-project: audio
ms.assetid: A6FFC14B-0736-425F-A923-DFF54494887C
ms.author: windowsdriverdev
ms.date: 3/19/2018
ms.keywords: IMiniportAudioEngineNode, IMiniportAudioEngineNode interface [Audio Devices], SetDeviceFormat method, IMiniportAudioEngineNode::SetDeviceFormat, SetDeviceFormat method [Audio Devices], SetDeviceFormat method [Audio Devices], IMiniportAudioEngineNode interface, SetDeviceFormat,IMiniportAudioEngineNode.SetDeviceFormat, audio.iminiportaudioenginenode_setdeviceformat, portcls/IMiniportAudioEngineNode::SetDeviceFormat
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
-	IMiniportAudioEngineNode.SetDeviceFormat
product:
- Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IMiniportAudioEngineNode::SetDeviceFormat method


## -description


Sets the audio data format for an audio device.


## -parameters




### -param ulNodeId [in]

The ID of the node that represents the device.


### -param pFormat [in]

A structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff537095">KSDATAFORMAT_WAVEFORMATEX</a> that represents the audio data format to be set for the device.


### -param ulBufferSize [in]

The audio data buffer size.


## -returns



<b>SetDeviceFormat</b> returns S_OK, if the call was successful. Otherwise, the method 

returns an appropriate error code.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn302040">IMiniportAudioEngineNode</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537095">KSDATAFORMAT_WAVEFORMATEX</a>
 

 

