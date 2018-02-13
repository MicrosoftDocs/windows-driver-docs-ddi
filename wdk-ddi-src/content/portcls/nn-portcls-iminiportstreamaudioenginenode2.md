---
UID: NN:portcls.IMiniportStreamAudioEngineNode2
title: IMiniportStreamAudioEngineNode2
author: windows-driver-content
description: The IMiniportStreamAudioEngineNode2 interface allows an audio miniport driver to extend the capabilities of the IMiniportStreamAudioEngineNode interface.
old-location: audio\iminiportstreamaudioenginenode2.htm
old-project: audio
ms.assetid: 38888C17-31FC-47F4-A49B-A46A9DF962AF
ms.author: windowsdriverdev
ms.date: 2/8/2018
ms.keywords: audio.iminiportstreamaudioenginenode2, IMiniportStreamAudioEngineNode2 interface [Audio Devices], IMiniportStreamAudioEngineNode2 interface [Audio Devices], described, IMiniportStreamAudioEngineNode2, portcls/IMiniportStreamAudioEngineNode2
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: portcls.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Portcls.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	Portcls.h
apiname:
-	IMiniportStreamAudioEngineNode2
product: Windows
targetos: Windows
req.typenames: "*PPC_EXIT_LATENCY, PC_EXIT_LATENCY"
---

# IMiniportStreamAudioEngineNode2 interface


## -description


The <b>IMiniportStreamAudioEngineNode2</b> interface allows an audio miniport driver to extend the capabilities of the <a href="..\portcls\nn-portcls-iminiportstreamaudioenginenode.md">IMiniportStreamAudioEngineNode</a> interface.


## -members

The <b>IMiniportStreamAudioEngineNode2</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/dn338128">SetStreamCurrentWritePositionForLastBuffer</a>
</td>
<td align="left" width="63%">
Sets the current cursor position in the last audio data stream that was written to the audio buffer.

</td>
</tr>
</table>Sets the current cursor position in the last audio data stream that was written to the audio buffer.

 

