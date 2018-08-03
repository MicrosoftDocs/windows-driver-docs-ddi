---
UID: NN:portcls.IMiniportAudioSignalProcessing
title: IMiniportAudioSignalProcessing
author: windows-driver-content
description: The IMiniportAudioSignalProcessing interface is implemented by the WaveRT miniport component of any audio driver, if any of its pins support audio signal processing modes.
old-location: audio\iminiportaudiosignalprocessing.htm
tech.root: audio
ms.assetid: 6C520509-347F-4E01-95C4-0D3306031E51
ms.author: windowsdriverdev
ms.date: 5/8/2018
ms.keywords: IMiniportAudioSignalProcessing, IMiniportAudioSignalProcessing interface [Audio Devices], IMiniportAudioSignalProcessing interface [Audio Devices],described, audio.iminiportaudiosignalprocessing, portcls/IMiniportAudioSignalProcessing
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
-	IMiniportAudioSignalProcessing
product:
- Windows
targetos: Windows
req.typenames: 
---

# IMiniportAudioSignalProcessing interface


## -description


The IMiniportAudioSignalProcessing interface is implemented by the WaveRT miniport component of any audio driver, if any of its pins support audio signal processing modes.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IMiniportAudioSignalProcessing</b> interface inherits from the <a href="https://msdn.microsoft.com/33f1d79a-33fc-4ce5-a372-e08bda378332">IUnknown</a> interface. <b>IMiniportAudioSignalProcessing</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IMiniportAudioSignalProcessing</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/dn457660">GetModes</a>
</td>
<td align="left" width="63%">
The GetModes method, Gets the audio signal processing modes supported by an audio pin.

</td>
</tr>
</table> 


## -remarks



Any of the Portcls miniport drivers can also implement the <b>GetModes</b> method.



