---
UID: NF:portcls.IPreFetchOffset.SetPreFetchOffset
title: IPreFetchOffset::SetPreFetchOffset (portcls.h)
description: The SetPreFetchOffset method sets the prefetch offset, which is the number of bytes of data separating the write cursor from the play cursor in a DirectSound output stream.
old-location: audio\iprefetchoffset_setprefetchoffset.htm
tech.root: audio
ms.assetid: fef8e8b8-7e79-4d88-b643-9b371e4297fd
ms.date: 05/08/2018
ms.keywords: IPreFetchOffset interface [Audio Devices],SetPreFetchOffset method, IPreFetchOffset.SetPreFetchOffset, IPreFetchOffset::SetPreFetchOffset, SetPreFetchOffset, SetPreFetchOffset method [Audio Devices], SetPreFetchOffset method [Audio Devices],IPreFetchOffset interface, audio.iprefetchoffset_setprefetchoffset, audmp-routines_7fb7bb20-d9e0-4022-9de4-1c5952bfccf8.xml, portcls/IPreFetchOffset::SetPreFetchOffset
ms.topic: method
f1_keywords:
 - "portcls/IPreFetchOffset.SetPreFetchOffset"
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
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
req.irql: Any level
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- portcls.h
api_name:
- IPreFetchOffset.SetPreFetchOffset
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPreFetchOffset::SetPreFetchOffset


## -description


The <code>SetPreFetchOffset</code> method sets the prefetch offset, which is the number of bytes of data separating the write cursor from the play cursor in a DirectSound output stream.


## -parameters




### -param PreFetchOffset [in]

Specifies the prefetch offset size in bytes.


## -returns



None




## -remarks



A WavePci miniport driver calls the <code>SetPreFetchOffset</code> method to specify the prefetch offset of a hardware-accelerated DirectSound output stream.

The prefetch offset is the number of bytes of data separating the write cursor from the play cursor in the audio device's hardware buffer:

<ul>
<li>
The write cursor specifies the buffer position into which a DirectSound application can safely write the next sound sample.

</li>
<li>
The play cursor specifies the buffer position of the sound sample that is currently being played by the audio device.

</li>
</ul>
For more information about write cursors and play cursors, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ksmedia/ns-ksmedia-ksaudio_position">KSAUDIO_POSITION</a>.

For information about using <code>SetPreFetchOffset</code> to control a DirectSound stream's prefetch offset, see <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/prefetch-offsets">Prefetch Offsets</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/nf-portcls-iminiportwavepcistream-getposition">IMiniportWavePciStream::GetPosition</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/nf-portcls-iportwavepcistream-getmapping">IPortWavePciStream::GetMapping</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/nn-portcls-iprefetchoffset">IPreFetchOffset</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ksmedia/ns-ksmedia-ksaudio_position">KSAUDIO_POSITION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/audio/ksproperty-audio-position">KSPROPERTY_AUDIO_POSITION</a>
 

 

