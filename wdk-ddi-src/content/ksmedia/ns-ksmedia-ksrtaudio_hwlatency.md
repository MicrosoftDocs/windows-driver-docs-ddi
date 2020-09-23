---
UID: NS:ksmedia.__unnamed_struct_27
title: KSRTAUDIO_HWLATENCY (ksmedia.h)
description: The KSRTAUDIO_HWLATENCY structure describes the latency that the audio hardware adds to a wave stream during playback or recording.
old-location: audio\ksrtaudio_hwlatency.htm
tech.root: audio
ms.assetid: dd9998d0-46e6-4b12-aa96-1e6eede15f47
ms.date: 05/08/2018
keywords: ["KSRTAUDIO_HWLATENCY structure"]
ms.keywords: "*PKSRTAUDIO_HWLATENCY, KSRTAUDIO_HWLATENCY, KSRTAUDIO_HWLATENCY structure [Audio Devices], PKSRTAUDIO_HWLATENCY, PKSRTAUDIO_HWLATENCY structure pointer [Audio Devices], aud-prop_dd10bf1b-e1b6-4dfd-bb50-1540ef3caed5.xml, audio.ksrtaudio_hwlatency, ksmedia/KSRTAUDIO_HWLATENCY, ksmedia/PKSRTAUDIO_HWLATENCY"
req.header: ksmedia.h
req.include-header: 
req.target-type: Windows
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
req.irql: 
targetos: Windows
req.typenames: KSRTAUDIO_HWLATENCY, *PKSRTAUDIO_HWLATENCY
f1_keywords:
 - PKSRTAUDIO_HWLATENCY
 - ksmedia/PKSRTAUDIO_HWLATENCY
 - KSRTAUDIO_HWLATENCY
 - ksmedia/KSRTAUDIO_HWLATENCY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - KSRTAUDIO_HWLATENCY
---

# KSRTAUDIO_HWLATENCY structure


## -description

The KSRTAUDIO_HWLATENCY structure describes the latency that the audio hardware adds to a wave stream during playback or recording.

## -struct-fields

### -field FifoSize

Specifies the size, in bytes, of the hardware FIFO.

### -field ChipsetDelay

Specifies the delay through the chipset in 100-nanosecond units.

### -field CodecDelay

Specifies the delay through the codec in 100-nanosecond units.

## -remarks

The <a href="/windows-hardware/drivers/audio/ksproperty-rtaudio-hwlatency">KSPROPERTY_RTAUDIO_HWLATENCY</a> property request uses the KSRTAUDIO_HWLATENCY structure to pass hardware-latency information from the driver to the client.

The <b>FifoSize</b> member specifies the size of the hardware FIFO that the audio device uses to buffer the wave data that is in transit between memory and the digital-to-analog or analog-to-digital converter (DAC or ADC). During playback, the audio device reads data from memory and holds the data in the FIFO until the time arrives to feed the data to the DAC. During recording, the FIFO accumulates data from the ADC before writing it to main memory. The size of the FIFO can vary with the sample rate and transfer mode.

The <b>ChipsetDelay</b> member is the maximum delay that the chipset adds to data packets traveling between the CPU and main memory. Packet-based hardware interfaces such as PCI Express have nonzero delays with guaranteed upper bounds for isochronous transfer modes, that is, continuous data streaming at periodic intervals. However, for legacy PCI, which uses traditional parallel-bus transfers, the delay is specified as 0.

The <b>CodecDelay</b> member is the delay that the codec adds to an audio stream. The time required for a sample to travel between the audio bus and the input or output jack includes delays through the FIFO, DAC, or ADC, and any intermediate processing stages. The codec delay can vary with the sample rate and is therefore only a best estimate.

## -see-also

<a href="/windows-hardware/drivers/audio/ksproperty-rtaudio-hwlatency">KSPROPERTY_RTAUDIO_HWLATENCY</a>