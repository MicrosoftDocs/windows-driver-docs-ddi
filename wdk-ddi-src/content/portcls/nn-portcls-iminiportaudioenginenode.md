---
UID: NN:portcls.IMiniportAudioEngineNode
title: IMiniportAudioEngineNode
author: windows-driver-content
description: This interface allows a miniport driver to use KS properties that access the audio engine via a KS filter handle.
old-location: audio\iminiportaudioenginenode.htm
old-project: audio
ms.assetid: 58170D54-869A-49CC-865A-AB64BFB41A4B
ms.author: windowsdriverdev
ms.date: 3/19/2018
ms.keywords: IMiniportAudioEngineNode, IMiniportAudioEngineNode interface [Audio Devices], IMiniportAudioEngineNode interface [Audio Devices], described, audio.iminiportaudioenginenode, portcls/IMiniportAudioEngineNode
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: portcls.h
req.include-header: 
req.target-type: Windows
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
req.lib: Portcls.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	Portcls.h
api_name:
-	IMiniportAudioEngineNode
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IMiniportAudioEngineNode interface


## -description


This interface allows a miniport driver to use KS properties that access the audio engine via a KS filter handle.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IMiniportAudioEngineNode</b> interface inherits from the <a href="https://msdn.microsoft.com/33f1d79a-33fc-4ce5-a372-e08bda378332">IUnknown</a> interface. <b>IMiniportAudioEngineNode</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IMiniportAudioEngineNode</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/dn265074">GetAudioEngineDescriptor</a>
</td>
<td align="left" width="63%">
Gets the descriptor for the audio engine node.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/dn265075">GetBufferSizeRange</a>
</td>
<td align="left" width="63%">
Gets the minimum and maximum buffer size that the hardware audio engine can support.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/dn265076">GetDeviceAttributeSteppings</a>
</td>
<td align="left" width="63%">
Gets the allowed stepping value for the audio device attribute.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/dn265077">GetDeviceChannelCount</a>
</td>
<td align="left" width="63%">
Gets a count of the number of channels supported by the audio device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/dn265078">GetDeviceChannelMute</a>
</td>
<td align="left" width="63%">
Gets the state of the Mute node for the audio device channel.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/dn265079">GetDeviceChannelPeakMeter</a>
</td>
<td align="left" width="63%">
Gets the PeakMeter value  for the audio device channel.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/dn265080">GetDeviceChannelVolume</a>
</td>
<td align="left" width="63%">
Gets the volume level for a given channel of the audio device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/dn265081">GetDeviceFormat</a>
</td>
<td align="left" width="63%">
Gets the audio data format for an audio device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/dn265082">GetEngineFormatSize</a>
</td>
<td align="left" width="63%">
Gets the format type and the buffer size for the audio engine's audio data format.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/dn265083">GetGfxState</a>
</td>
<td align="left" width="63%">
Gets the state of the global effects (GFX) node in the audio engine.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/dn265084">GetMixFormat</a>
</td>
<td align="left" width="63%">
Gets the audio data format for the audio engine mixer.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/dn265085">GetSupportedDeviceFormats</a>
</td>
<td align="left" width="63%">
Gets the supported audio data formats for the audio device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/dn265086">SetDeviceChannelMute</a>
</td>
<td align="left" width="63%">
Sets the state of the Mute node for the audio device channel.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/dn265087">SetDeviceChannelVolume</a>
</td>
<td align="left" width="63%">
Sets the volume level for a given channel of the audio device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/dn265088">SetDeviceFormat</a>
</td>
<td align="left" width="63%">
Sets the audio data format for an audio device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/dn265089">SetGfxState</a>
</td>
<td align="left" width="63%">
Sets the state of the global effects (GFX) node in the audio engine.

</td>
</tr>
</table> 

