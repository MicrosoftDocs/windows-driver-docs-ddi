---
UID: NF:portcls.IMiniportStreamAudioEngineNode.SetStreamChannelVolume
title: IMiniportStreamAudioEngineNode::SetStreamChannelVolume method
author: windows-driver-content
description: Sets the volume level to be applied to the audio stream.
old-location: audio\iminiportstreamaudioenginenode_setstreamchannelvolume.htm
old-project: audio
ms.assetid: 0110979E-8C57-4394-B43E-BCC7B178A0AF
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: SetStreamChannelVolume method [Audio Devices], IMiniportStreamAudioEngineNode::SetStreamChannelVolume, SetStreamChannelVolume, IMiniportStreamAudioEngineNode, IMiniportStreamAudioEngineNode interface [Audio Devices], SetStreamChannelVolume method, audio.iminiportstreamaudioenginenode_setstreamchannelvolume, portcls/IMiniportStreamAudioEngineNode::SetStreamChannelVolume, SetStreamChannelVolume method [Audio Devices], IMiniportStreamAudioEngineNode interface
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
-	IMiniportStreamAudioEngineNode.SetStreamChannelVolume
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IMiniportStreamAudioEngineNode::SetStreamChannelVolume method


## -description


Sets the volume level to be applied to the audio stream.


## -syntax


````
NTSTATUS SetStreamChannelVolume(
  [in] UINT32           Channel,
  [in] LONG             TargetVolume,
  [in] AUDIO_CURVE_TYPE CurveType,
  [in] ULONGLONG        CurveDuration
);
````


## -parameters




### -param Channel [in]

The audio stream channel.


### -param TargetVolume [in]

The volume level to be applied to the audio stream.


### -param CurveType [in]

The curve algorithm that will be used  to set the volume level. The curve types are represented by the members of the <a href="..\ksmedia\ne-ksmedia-audio_curve_type.md">AUDIO_CURVE_TYPE</a> enum.


### -param CurveDuration [in]

The length of time over which the curve algorithm will be applied.


## -returns


<b>SetStreamChannelVolume</b> returns S_OK, if the call was successful. Otherwise, the method returns an appropriate error 

code.



## -see-also

<a href="..\portcls\nn-portcls-iminiportstreamaudioenginenode.md">IMiniportStreamAudioEngineNode</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IMiniportStreamAudioEngineNode::SetStreamChannelVolume method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

