---
UID: NF:portcls.IMiniportMidi.NewStream
title: IMiniportMidi::NewStream (portcls.h)
description: The NewStream method creates a new instance of a logical stream associated with a specified physical channel.
old-location: audio\iminiportmidi_newstream.htm
tech.root: audio
ms.date: 05/08/2018
keywords: ["IMiniportMidi::NewStream"]
ms.keywords: IMiniportMidi interface [Audio Devices],NewStream method, IMiniportMidi.NewStream, IMiniportMidi::NewStream, NewStream, NewStream method [Audio Devices], NewStream method [Audio Devices],IMiniportMidi interface, audio.iminiportmidi_newstream, audmp-routines_4cc2fc38-bf0b-467e-83d4-678189d8fc0f.xml, portcls/IMiniportMidi::NewStream
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
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - IMiniportMidi::NewStream
 - portcls/IMiniportMidi::NewStream
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - portcls.h
api_name:
 - IMiniportMidi::NewStream
---

# IMiniportMidi::NewStream


## -description

The <code>NewStream</code> method creates a new instance of a logical stream associated with a specified physical channel.

## -parameters

### -param Stream 

[out]
Output pointer for the new stream. This parameter points to a caller-allocated pointer variable into which the method writes a pointer to the stream object's <a href="/windows-hardware/drivers/ddi/portcls/nn-portcls-iminiportmidistream">IMiniportMidiStream</a> interface.

### -param OuterUnknown 

[in, optional]
Pointer to the <b>IUnknown</b> interface of an object that needs to aggregate the stream object. This parameter is optional. If aggregation is not required, the caller specifies this parameter as <b>NULL</b>.

### -param PoolType 

[in]
Specifies the type of memory pool from which the storage for the DMA-channel object should be allocated. This parameter is set to one of the <a href="/windows-hardware/drivers/ddi/wdm/ne-wdm-_pool_type">POOL_TYPE</a> enumeration values.

### -param Pin 

[in]
Specifies the pin ID. This parameter identifies the pin that is to be opened. If the MIDI miniport object's <a href="/windows-hardware/drivers/ddi/portcls/nf-portcls-iminiport-getdescription">IMiniport::GetDescription</a> method outputs a filter descriptor that specifies a total of <i>n</i> pin factories on the filter, then valid pin IDs are in the range 0 to <i>n</i>-1.

### -param Capture 

[in]
Specifies whether the channel is to be used for capture or for playback. If <b>TRUE</b>, it is a capture (input) channel. If <b>FALSE</b>, it is a playback (output) channel.

### -param DataFormat 

[in]
Pointer to a <a href="/windows-hardware/drivers/ddi/ks/ns-ks-ksdataformat">KSDATAFORMAT</a> structure that specifies the data format to use for this stream instance.

### -param ServiceGroup 

[out]
Output pointer for the service group. This parameter points to a caller-allocated pointer variable into which the method writes a pointer to the <a href="/windows-hardware/drivers/ddi/portcls/nn-portcls-iservicegroup">IServiceGroup</a> interface of the stream's service group object. This is the service group that is being registered for interrupt notification.

## -returns

<code>NewStream</code> returns STATUS_SUCCESS if the call was successful. Otherwise, the method returns an appropriate error code.

## -remarks

The <code>NewStream</code> method sets the initial state of the stream to KSSTATE_STOP.

The <i>Stream</i>, <i>OuterUnknown</i>, and <i>ServiceGroup</i> parameters follow the <a href="/windows-hardware/drivers/audio/reference-counting-conventions-for-com-objects">reference-counting conventions for COM objects</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/portcls/nf-portcls-iminiport-getdescription">IMiniport::GetDescription</a>



<a href="/windows-hardware/drivers/ddi/portcls/nn-portcls-iminiportmidi">IMiniportMidi</a>



<a href="/windows-hardware/drivers/ddi/portcls/nn-portcls-iminiportmidistream">IMiniportMidiStream</a>



<a href="/windows-hardware/drivers/ddi/portcls/nn-portcls-iservicegroup">IServiceGroup</a>



<a href="/windows-hardware/drivers/ddi/ks/ns-ks-ksdataformat">KSDATAFORMAT</a>



<a href="/windows-hardware/drivers/ddi/wdm/ne-wdm-_pool_type">POOL_TYPE</a>

