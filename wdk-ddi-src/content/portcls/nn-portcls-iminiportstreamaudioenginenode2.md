---
UID: NN:portcls.IMiniportStreamAudioEngineNode2
title: IMiniportStreamAudioEngineNode2
author: windows-driver-content
description: The IMiniportStreamAudioEngineNode2 interface allows an audio miniport driver to extend the capabilities of the IMiniportStreamAudioEngineNode interface.
old-location: audio\iminiportstreamaudioenginenode2.htm
tech.root: audio
ms.assetid: 38888C17-31FC-47F4-A49B-A46A9DF962AF
ms.date: 5/8/2018
ms.keywords: IMiniportStreamAudioEngineNode2, IMiniportStreamAudioEngineNode2 interface [Audio Devices], IMiniportStreamAudioEngineNode2 interface [Audio Devices],described, audio.iminiportstreamaudioenginenode2, portcls/IMiniportStreamAudioEngineNode2
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
-	IMiniportStreamAudioEngineNode2
product:
- Windows
targetos: Windows
req.typenames: 
---

# IMiniportStreamAudioEngineNode2 interface


## -description


The <b>IMiniportStreamAudioEngineNode2</b> interface allows an audio miniport driver to extend the capabilities of the <a href="https://msdn.microsoft.com/library/windows/hardware/dn265090">IMiniportStreamAudioEngineNode</a> interface.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IMiniportStreamAudioEngineNode2</b> interface inherits from the <a href="https://msdn.microsoft.com/33f1d79a-33fc-4ce5-a372-e08bda378332">IUnknown</a> interface. <b>IMiniportStreamAudioEngineNode2</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

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
</table> 

