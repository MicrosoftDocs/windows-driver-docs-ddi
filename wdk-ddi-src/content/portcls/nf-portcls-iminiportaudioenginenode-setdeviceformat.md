---
UID: NF:portcls.IMiniportAudioEngineNode.SetDeviceFormat
title: IMiniportAudioEngineNode::SetDeviceFormat method
author: windows-driver-content
description: Sets the audio data format for an audio device.
old-location: audio\iminiportaudioenginenode_setdeviceformat.htm
old-project: audio
ms.assetid: A6FFC14B-0736-425F-A923-DFF54494887C
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: SetDeviceFormat, portcls/IMiniportAudioEngineNode::SetDeviceFormat, SetDeviceFormat method [Audio Devices], IMiniportAudioEngineNode interface, IMiniportAudioEngineNode::SetDeviceFormat, audio.iminiportaudioenginenode_setdeviceformat, IMiniportAudioEngineNode interface [Audio Devices], SetDeviceFormat method, SetDeviceFormat method [Audio Devices], IMiniportAudioEngineNode
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
-	IMiniportAudioEngineNode.SetDeviceFormat
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IMiniportAudioEngineNode::SetDeviceFormat method


## -description


Sets the audio data format for an audio device.


## -syntax


````
NTSTATUS SetDeviceFormat(
  [in] ULONG                     ulNodeId,
  [in] KSDATAFORMAT_WAVEFORMATEX *pFormat,
  [in] ULONG                     ulBufferSize
);
````


## -parameters




### -param ulNodeId [in]

The ID of the node that represents the device.


### -param pFormat [in]

A structure of type <a href="..\ksmedia\ns-ksmedia-ksdataformat_waveformatex.md">KSDATAFORMAT_WAVEFORMATEX</a> that represents the audio data format to be set for the device.


### -param ulBufferSize [in]

The audio data buffer size.


## -returns


<b>SetDeviceFormat</b> returns S_OK, if the call was successful. Otherwise, the method 

returns an appropriate error code.



## -see-also

<a href="..\portcls\nn-portcls-iminiportaudioenginenode.md">IMiniportAudioEngineNode</a>

<a href="..\ksmedia\ns-ksmedia-ksdataformat_waveformatex.md">KSDATAFORMAT_WAVEFORMATEX</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IMiniportAudioEngineNode::SetDeviceFormat method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

