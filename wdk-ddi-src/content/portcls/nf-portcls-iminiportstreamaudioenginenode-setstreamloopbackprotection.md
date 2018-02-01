---
UID: NF:portcls.IMiniportStreamAudioEngineNode.SetStreamLoopbackProtection
title: IMiniportStreamAudioEngineNode::SetStreamLoopbackProtection method
author: windows-driver-content
description: Sets the loopback protection status of the audio engine node.
old-location: audio\iminiportstreamaudioenginenode_setstreamloopbackprotection.htm
old-project: audio
ms.assetid: FAC9AC9B-9C4B-4D53-A59A-8901EC8755BC
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: SetStreamLoopbackProtection method [Audio Devices], IMiniportStreamAudioEngineNode interface, portcls/IMiniportStreamAudioEngineNode::SetStreamLoopbackProtection, IMiniportStreamAudioEngineNode interface [Audio Devices], SetStreamLoopbackProtection method, IMiniportStreamAudioEngineNode, IMiniportStreamAudioEngineNode::SetStreamLoopbackProtection, audio.iminiportstreamaudioenginenode_setstreamloopbackprotection, SetStreamLoopbackProtection method [Audio Devices], SetStreamLoopbackProtection
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
-	IMiniportStreamAudioEngineNode.SetStreamLoopbackProtection
product: Windows
targetos: Windows
req.typenames: "*PPC_EXIT_LATENCY, PC_EXIT_LATENCY"
---

# IMiniportStreamAudioEngineNode::SetStreamLoopbackProtection method


## -description


Sets the loopback protection status of the audio engine node.


## -syntax


````
NTSTATUS SetStreamLoopbackProtection(
  [in] CONSTRICTOR_OPTION ProtectionOption
);
````


## -parameters




### -param ProtectionOption [in]

A CONSTRICTOR_OPTION enumeration  value that indicates status of the loopback protection option.


## -returns


<b>SetStreamLoopbackProtection</b> returns S_OK, if the call was successful. Otherwise, the method returns an appropriate error code.



## -remarks


For more information about audio stream loopback protection, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh450878">KSPROPERTY_AUDIOENGINE_LOOPBACK_PROTECTION</a>.



## -see-also

<a href="..\portcls\nn-portcls-iminiportstreamaudioenginenode.md">IMiniportStreamAudioEngineNode</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh450878">KSPROPERTY_AUDIOENGINE_LOOPBACK_PROTECTION</a>

CONSTRICTOR_OPTION

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IMiniportStreamAudioEngineNode::SetStreamLoopbackProtection method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

