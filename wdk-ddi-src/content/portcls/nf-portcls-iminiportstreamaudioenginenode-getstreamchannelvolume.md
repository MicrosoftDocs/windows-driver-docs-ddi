---
UID: NF:portcls.IMiniportStreamAudioEngineNode.GetStreamChannelVolume
title: IMiniportStreamAudioEngineNode::GetStreamChannelVolume method
author: windows-driver-content
description: Gets the current volume level that is applied to the audio stream.
old-location: audio\iminiportstreamaudioenginenode_getstreamchannelvolume.htm
old-project: audio
ms.assetid: 0BD6FCB7-1705-4343-AD41-7362FE095ECB
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: GetStreamChannelVolume method [Audio Devices], GetStreamChannelVolume, IMiniportStreamAudioEngineNode interface [Audio Devices], GetStreamChannelVolume method, portcls/IMiniportStreamAudioEngineNode::GetStreamChannelVolume, IMiniportStreamAudioEngineNode::GetStreamChannelVolume, audio.iminiportstreamaudioenginenode_getstreamchannelvolume, IMiniportStreamAudioEngineNode, GetStreamChannelVolume method [Audio Devices], IMiniportStreamAudioEngineNode interface
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
-	IMiniportStreamAudioEngineNode.GetStreamChannelVolume
product: Windows
targetos: Windows
req.typenames: "*PPC_EXIT_LATENCY, PC_EXIT_LATENCY"
---

# IMiniportStreamAudioEngineNode::GetStreamChannelVolume method


## -description


Gets the current volume level that is applied to the audio stream.


## -syntax


````
NTSTATUS GetStreamChannelVolume(
  [in]  UINT32  ulChannel,
  [out] LONG   *plValue
);
````


## -parameters




### -param ulChannel [in]

The audio stream channel.


### -param plValue [out]

The current volume level.


## -returns


<b>GetStreamChannelVolume</b> returns S_OK, if the call was successful. Otherwise, the method returns an appropriate error 

code.



## -see-also

<a href="..\portcls\nn-portcls-iminiportstreamaudioenginenode.md">IMiniportStreamAudioEngineNode</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IMiniportStreamAudioEngineNode::GetStreamChannelVolume method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

