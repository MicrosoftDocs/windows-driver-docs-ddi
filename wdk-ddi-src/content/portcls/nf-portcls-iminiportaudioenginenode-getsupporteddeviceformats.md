---
UID: NF:portcls.IMiniportAudioEngineNode.GetSupportedDeviceFormats
title: IMiniportAudioEngineNode::GetSupportedDeviceFormats method
author: windows-driver-content
description: Gets the supported audio data formats for the audio device.
old-location: audio\iminiportaudioenginenode_getsupporteddeviceformats.htm
old-project: audio
ms.assetid: 2B27E92C-8781-4499-A1E0-7C1BBFFAA2DF
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: portcls/IMiniportAudioEngineNode::GetSupportedDeviceFormats, IMiniportAudioEngineNode interface [Audio Devices], GetSupportedDeviceFormats method, IMiniportAudioEngineNode, GetSupportedDeviceFormats, audio.iminiportaudioenginenode_getsupporteddeviceformats, GetSupportedDeviceFormats method [Audio Devices], IMiniportAudioEngineNode::GetSupportedDeviceFormats, GetSupportedDeviceFormats method [Audio Devices], IMiniportAudioEngineNode interface
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
-	IMiniportAudioEngineNode.GetSupportedDeviceFormats
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IMiniportAudioEngineNode::GetSupportedDeviceFormats method


## -description


Gets the supported audio data formats for the audio device.


## -syntax


````
NTSTATUS GetSupportedDeviceFormats(
  [in]  ULONG           ulNodeId,
  [out] KSMULTIPLE_ITEM *pFormats,
  [in]  ULONG           ulBufferSize
);
````


## -parameters




### -param ulNodeId [in]

The ID of the node that represents the audio device.


### -param pFormats [out]

A structure of type <a href="http://msdn.microsoft.com/en-us/library/windows/hardware/ff563441(v=vs.85).aspx">KSMULTIPLE_ITEM</a> that points to the array of audio data formats supported by the audio device.


### -param ulBufferSize [in]

The buffer size for the audio data format information.


## -returns


<b>GetSupportedDeviceFormats</b> returns S_OK, if the call was successful. Otherwise, the method 

returns an appropriate error code.



## -see-also

<a href="..\portcls\nn-portcls-iminiportaudioenginenode.md">IMiniportAudioEngineNode</a>

<a href="http://msdn.microsoft.com/en-us/library/windows/hardware/ff563441(v=vs.85).aspx">KSMULTIPLE_ITEM</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IMiniportAudioEngineNode::GetSupportedDeviceFormats method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

