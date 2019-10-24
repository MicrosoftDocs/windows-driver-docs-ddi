---
UID: NN:portcls.IMiniportAudioEngineNode
title: IMiniportAudioEngineNode (portcls.h)
description: This interface allows a miniport driver to use KS properties that access the audio engine via a KS filter handle.
old-location: audio\iminiportaudioenginenode.htm
tech.root: audio
ms.assetid: 58170D54-869A-49CC-865A-AB64BFB41A4B
ms.date: 05/08/2018
ms.keywords: IMiniportAudioEngineNode, IMiniportAudioEngineNode interface [Audio Devices], IMiniportAudioEngineNode interface [Audio Devices],described, audio.iminiportaudioenginenode, portcls/IMiniportAudioEngineNode
ms.topic: interface
f1_keywords:
 - "portcls/IMiniportAudioEngineNode"
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- Portcls.h
api_name:
- IMiniportAudioEngineNode
product:
- Windows
targetos: Windows
req.typenames: 
---

# IMiniportAudioEngineNode interface


## -description


This interface allows a miniport driver to use KS properties that access the audio engine via a KS filter handle.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IMiniportAudioEngineNode</b> interface inherits from the <a href="https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IMiniportAudioEngineNode</b> also has these types of members:
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
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-iminiportaudioenginenode-getaudioenginedescriptor">GetAudioEngineDescriptor</a>
</td>
<td align="left" width="63%">
Gets the descriptor for the audio engine node.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-iminiportaudioenginenode-getbuffersizerange">GetBufferSizeRange</a>
</td>
<td align="left" width="63%">
Gets the minimum and maximum buffer size that the hardware audio engine can support.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-iminiportaudioenginenode-getdeviceattributesteppings">GetDeviceAttributeSteppings</a>
</td>
<td align="left" width="63%">
Gets the allowed stepping value for the audio device attribute.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-iminiportaudioenginenode-getdevicechannelcount">GetDeviceChannelCount</a>
</td>
<td align="left" width="63%">
Gets a count of the number of channels supported by the audio device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-iminiportaudioenginenode-getdevicechannelmute">GetDeviceChannelMute</a>
</td>
<td align="left" width="63%">
Gets the state of the Mute node for the audio device channel.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-iminiportaudioenginenode-getdevicechannelpeakmeter">GetDeviceChannelPeakMeter</a>
</td>
<td align="left" width="63%">
Gets the PeakMeter value  for the audio device channel.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-iminiportaudioenginenode-getdevicechannelvolume">GetDeviceChannelVolume</a>
</td>
<td align="left" width="63%">
Gets the volume level for a given channel of the audio device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-iminiportaudioenginenode-getdeviceformat">GetDeviceFormat</a>
</td>
<td align="left" width="63%">
Gets the audio data format for an audio device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-iminiportaudioenginenode-getengineformatsize">GetEngineFormatSize</a>
</td>
<td align="left" width="63%">
Gets the format type and the buffer size for the audio engine's audio data format.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-iminiportaudioenginenode-getgfxstate">GetGfxState</a>
</td>
<td align="left" width="63%">
Gets the state of the global effects (GFX) node in the audio engine.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-iminiportaudioenginenode-getmixformat">GetMixFormat</a>
</td>
<td align="left" width="63%">
Gets the audio data format for the audio engine mixer.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-iminiportaudioenginenode-getsupporteddeviceformats">GetSupportedDeviceFormats</a>
</td>
<td align="left" width="63%">
Gets the supported audio data formats for the audio device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-iminiportaudioenginenode-setdevicechannelmute">SetDeviceChannelMute</a>
</td>
<td align="left" width="63%">
Sets the state of the Mute node for the audio device channel.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-iminiportaudioenginenode-setdevicechannelvolume">SetDeviceChannelVolume</a>
</td>
<td align="left" width="63%">
Sets the volume level for a given channel of the audio device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-iminiportaudioenginenode-setdeviceformat">SetDeviceFormat</a>
</td>
<td align="left" width="63%">
Sets the audio data format for an audio device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-iminiportaudioenginenode-setgfxstate">SetGfxState</a>
</td>
<td align="left" width="63%">
Sets the state of the global effects (GFX) node in the audio engine.

</td>
</tr>
</table> 

