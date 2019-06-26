---
UID: NN:portcls.IMiniportStreamAudioEngineNode
title: IMiniportStreamAudioEngineNode (portcls.h)
description: This interface allows a miniport driver to use KS properties that access the audio engine via a pin instance handle.
old-location: audio\iminiportstreamaudioenginenode.htm
tech.root: audio
ms.assetid: B3F7D3AC-C756-47D2-9E7C-7930621753C3
ms.date: 05/08/2018
ms.keywords: IMiniportStreamAudioEngineNode, IMiniportStreamAudioEngineNode interface [Audio Devices], IMiniportStreamAudioEngineNode interface [Audio Devices],described, audio.iminiportstreamaudioenginenode, portcls/IMiniportStreamAudioEngineNode
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
- IMiniportStreamAudioEngineNode
product:
- Windows
targetos: Windows
req.typenames: 
---

# IMiniportStreamAudioEngineNode interface


## -description


This interface allows a miniport driver to use KS properties that access the audio engine via a pin instance handle.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IMiniportStreamAudioEngineNode</b> interface inherits from the <a href="https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IMiniportStreamAudioEngineNode</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IMiniportStreamAudioEngineNode</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/nf-portcls-iminiportstreamaudioenginenode-getlfxstate">GetLfxState</a>
</td>
<td align="left" width="63%">
Gets the state of the local effects (LFX) node that is in the path of the audio stream.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/nf-portcls-iminiportstreamaudioenginenode-getstreamattributesteppings">GetStreamAttributeSteppings</a>
</td>
<td align="left" width="63%">
Gets the allowed stepping value for the audio stream attribute.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/nf-portcls-iminiportstreamaudioenginenode-getstreamchannelcount">GetStreamChannelCount</a>
</td>
<td align="left" width="63%">
Gets a count of the number of channels available for the stream.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/nf-portcls-iminiportstreamaudioenginenode-getstreamchannelmute">GetStreamChannelMute</a>
</td>
<td align="left" width="63%">
Gets the state of the Mute node in the path of the audio stream.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/nf-portcls-iminiportstreamaudioenginenode-getstreamchannelpeakmeter">GetStreamChannelPeakMeter</a>
</td>
<td align="left" width="63%">
Gets the value of the PeakMeter node in the path of the audio stream.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/nf-portcls-iminiportstreamaudioenginenode-getstreamchannelvolume">GetStreamChannelVolume</a>
</td>
<td align="left" width="63%">
Gets the current volume level that is applied to the audio stream.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/nf-portcls-iminiportstreamaudioenginenode-getstreamlinearbufferposition">GetStreamLinearBufferPosition</a>
</td>
<td align="left" width="63%">
	Gets the number of bytes that the DMA has fetched from the audio buffer since the beginning of the stream.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/nf-portcls-iminiportstreamaudioenginenode-getstreampresentationposition">GetStreamPresentationPosition</a>
</td>
<td align="left" width="63%">
Gets the current cursor position in the audio data stream that is being rendered to the endpoint.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/nf-portcls-iminiportstreamaudioenginenode-setlfxstate">SetLfxState</a>
</td>
<td align="left" width="63%">
Sets the state of the local effects (LFX) node that is in the path of the audio stream.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/nf-portcls-iminiportstreamaudioenginenode-setstreamchannelmute">SetStreamChannelMute</a>
</td>
<td align="left" width="63%">
Sets the state of the Mute node in the path of the audio stream.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/nf-portcls-iminiportstreamaudioenginenode-setstreamchannelvolume">SetStreamChannelVolume</a>
</td>
<td align="left" width="63%">
Sets the volume level to be applied to the audio stream.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/nf-portcls-iminiportstreamaudioenginenode-setstreamcurrentwriteposition">SetStreamCurrentWritePosition</a>
</td>
<td align="left" width="63%">
Sets the current cursor position in the audio data stream that is being captured from the endpoint.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/nf-portcls-iminiportstreamaudioenginenode-setstreamloopbackprotection">SetStreamLoopbackProtection</a>
</td>
<td align="left" width="63%">
Sets the loopback protection status of the audio engine node.

</td>
</tr>
</table> 

