---
UID: NF:portcls.IMiniportWaveRT.NewStream
title: IMiniportWaveRT::NewStream (portcls.h)
description: The NewStream method creates a new instance of a WaveRT stream object.
old-location: audio\iminiportwavert_newstream.htm
tech.root: audio
ms.date: 05/08/2018
keywords: ["IMiniportWaveRT::NewStream"]
ms.keywords: IMiniportWaveRT interface [Audio Devices],NewStream method, IMiniportWaveRT.NewStream, IMiniportWaveRT::NewStream, NewStream, NewStream method [Audio Devices], NewStream method [Audio Devices],IMiniportWaveRT interface, audio.iminiportwavert_newstream, audmp-routines_f6e65bf7-d19d-42fc-a0f0-2d2c83e88250.xml, portcls/IMiniportWaveRT::NewStream
req.header: portcls.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later Windows operating systems.
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
req.irql: Passive level.
targetos: Windows
req.typenames: 
f1_keywords:
 - IMiniportWaveRT::NewStream
 - portcls/IMiniportWaveRT::NewStream
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - portcls.h
api_name:
 - IMiniportWaveRT.NewStream
---

# IMiniportWaveRT::NewStream


## -description

The <code>NewStream</code> method creates a new instance of a WaveRT stream object.

## -parameters

### -param Stream 

[out]
Output pointer for the new stream. This parameter points to a caller-allocated pointer variable, into which the <code>NewStream</code> method writes a pointer to the <b>IMiniportWaveRTStream</b> interface of the new stream object. The caller specifies a valid, non-<b>NULL</b> pointer for this parameter.

### -param PortStream 

[in]
Pointer to the <a href="/windows-hardware/drivers/ddi/portcls/nn-portcls-iportwavertstream">IPortWaveRTStream</a>.

### -param Pin 

[in]
Specifies a pin ID that identifies the pin to be opened. If the filter descriptor of the WaveRT miniport driver specifies a total of <i>n</i> pin factories on the filter, valid values for the <i>Pin</i> parameter are in the range 0 to <i>n</i>-1. For more information about filter descriptors, see the <a href="/windows-hardware/drivers/audio/filter-factories">Filter Factories</a> topic.

### -param Capture 

[in]
Specifies a Boolean value that indicates whether to create a capture stream or a render stream. This parameter is <b>TRUE</b> for a capture (input) stream, and <b>FALSE</b> for a playback (output) stream.

### -param DataFormat 

[in]
Pointer to a <a href="/windows-hardware/drivers/ddi/ks/ns-ks-ksdataformat">KSDATAFORMAT</a> structure that specifies the data format of the new stream. For more information, see the following Remarks section.

## -returns

<code>NewStream</code> returns STATUS_SUCCESS if the call was successful. Otherwise, the method returns an appropriate error status code.

## -remarks

The <code>NewStream</code> method sets the initial state of the stream to <a href="/windows-hardware/drivers/stream/state-transitions">KSSTATE_STOP</a> and its initial position to 0. For more information, see related methods <a href="/windows-hardware/drivers/ddi/portcls/nf-portcls-iminiportwavertstream-setstate">IMiniportWaveRTStream::SetState</a> and <a href="/windows-hardware/drivers/ddi/portcls/nf-portcls-iminiportwavertstream-getposition">IMiniportWaveRTStream::GetPosition</a>.

The <i>DataFormat</i> parameter, which specifies the data format of the stream, points to one of the following audio-specific, extended versions of the KSDATAFORMAT structure:

<ul>
<li>

<a href="/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-ksdataformat_waveformatex">KSDATAFORMAT_WAVEFORMATEX</a>


</li>
<li>

<a href="/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-ksdataformat_dsound">KSDATAFORMAT_DSOUND</a>


</li>
</ul>
The <i>Stream</i> and <i>PortStream</i> parameters follow the reference-counting conventions for COM objects.

## -see-also

<a href="/windows-hardware/drivers/ddi/portcls/nn-portcls-iminiportwavert">IMiniportWaveRT</a>



IMiniportWaveRTStream



<a href="/windows-hardware/drivers/ddi/portcls/nf-portcls-iminiportwavertstream-getposition">IMiniportWaveRTStream::GetPosition</a>



<a href="/windows-hardware/drivers/ddi/portcls/nf-portcls-iminiportwavertstream-setstate">IMiniportWaveRTStream::SetState</a>



<a href="/windows-hardware/drivers/ddi/portcls/nn-portcls-iportwavertstream">IPortWaveRTStream</a>
