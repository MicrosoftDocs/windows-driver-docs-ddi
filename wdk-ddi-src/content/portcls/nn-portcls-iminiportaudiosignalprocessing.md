---
UID: NN:portcls.IMiniportAudioSignalProcessing
title: IMiniportAudioSignalProcessing
author: windows-driver-content
description: The IMiniportAudioSignalProcessing interface is implemented by the WaveRT miniport component of any audio driver, if any of its pins support audio signal processing modes.
old-location: audio\iminiportaudiosignalprocessing.htm
old-project: audio
ms.assetid: 6C520509-347F-4E01-95C4-0D3306031E51
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: PcUnregisterIoTimeout
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
req.alt-api: IMiniportAudioSignalProcessing
req.alt-loc: Portcls.h
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
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IMiniportAudioSignalProcessing interface



## -description
The IMiniportAudioSignalProcessing interface is implemented by the WaveRT miniport component of any audio driver, if any of its pins support audio signal processing modes.



## -inheritance
The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IMiniportAudioSignalProcessing</b> interface inherits from the <a href="com.iunknown" xmlns:loc="http://microsoft.com/wdcml/l10n"><b>IUnknown</b></a> interface. <b>IMiniportAudioSignalProcessing</b> also has these types of members:

The <b>IMiniportAudioSignalProcessing</b> interface has these methods.

The GetModes method, Gets the audio signal processing modes supported by an audio pin.

 


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
</table>The GetModes method, Gets the audio signal processing modes supported by an audio pin.

 


## -remarks
Any of the Portcls miniport drivers can also implement the <b>GetModes</b> method.</p>