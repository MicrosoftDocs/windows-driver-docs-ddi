---
UID: NS:ksmedia.__unnamed_struct_7
title: KSAUDIO_POSITION (ksmedia.h)
description: The KSAUDIO_POSITION structure specifies the current positions of the play and write cursors in the sound buffer for an audio stream.
old-location: audio\ksaudio_position.htm
tech.root: audio
ms.assetid: 91658dfc-dad4-4fbb-8688-13971e7275e2
ms.date: 05/08/2018
keywords: ["KSAUDIO_POSITION structure"]
ms.keywords: "*PKSAUDIO_POSITION, KSAUDIO_POSITION, KSAUDIO_POSITION structure [Audio Devices], PKSAUDIO_POSITION, PKSAUDIO_POSITION structure pointer [Audio Devices], aud-prop_0518af7c-0c1d-4710-8879-43bb42e1ba2a.xml, audio.ksaudio_position, ksmedia/KSAUDIO_POSITION, ksmedia/PKSAUDIO_POSITION"
f1_keywords:
 - "ksmedia/KSAUDIO_POSITION"
 - "KSAUDIO_POSITION"
req.header: ksmedia.h
req.include-header: Ksmedia.h
req.target-type: Windows
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ksmedia.h
api_name:
- KSAUDIO_POSITION
targetos: Windows
req.typenames: KSAUDIO_POSITION, *PKSAUDIO_POSITION
---

# KSAUDIO_POSITION structure


## -description


The KSAUDIO_POSITION structure specifies the current positions of the play and write cursors in the sound buffer for an audio stream.


## -struct-fields




### -field PlayOffset

Specifies the current play position as a byte offset.


### -field WriteOffset

Specifies the current write position as a byte offset.


## -remarks



This structure is used to get and set the data value for the <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/ksproperty-audio-position">KSPROPERTY_AUDIO_POSITION</a> property.

For a looped client buffer (with stream type <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksinterface-standard-looped-streaming">KSINTERFACE_STANDARD_LOOPED_STREAMING</a>), <b>PlayOffset</b> and <b>WriteOffset</b> are byte offsets into the client buffer. When either offset reaches the end of the buffer, it wraps around to the start of the buffer. Hence, neither offset ever exceeds the buffer size.

For a nonlooped client buffer (with stream type <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksinterface-standard-streaming">KSINTERFACE_STANDARD_STREAMING</a>), <b>PlayOffset</b> and <b>WriteOffset</b> are not offsets into any one physical buffer that either your driver has allocated or a client has allocated. Instead, these offsets are stream-relative and can be thought of as offsets into an idealized buffer that contains the entire stream and is contiguous from beginning to end. Any internal offsets that point into the actual physical buffers that contain the data need to be maintained separately.

During playback, the <b>PlayOffset</b> and <b>WriteOffset</b> values are interpreted as follows:

<ul>
<li>
<b>PlayOffset</b> is the offset of the last byte in the buffer that has played. <b>PlayOffset</b> + 1 is the offset of the next byte that will play.

</li>
<li>
<b>WriteOffset</b> is the offset of the last byte in the playback buffer.

</li>
</ul>
When a client submits another buffer to the device for playback, <b>WriteOffset</b> will increment upon receipt of that buffer to indicate the new <b>WriteOffset</b> value, but <b>PlayOffset</b> does not change until after that buffer has actually been played by the device.

During recording, the <b>PlayOffset</b> and <b>WriteOffset</b> values are interpreted as follows:

<ul>
<li>
<b>PlayOffset</b> is the offset of the last byte in the buffer that has been captured. <b>PlayOffset</b> + 1 is the offset of the next byte that will be captured.

</li>
<li>
<b>WriteOffset</b> is the offset of the last byte in the capture buffer.

</li>
</ul>
When an application submits another buffer to the device for capturing, the <b>WriteOffset</b> value will increment upon receipt of that buffer. The <b>PlayOffset</b> value will not change until data has actually been captured into the buffer.

The space between <b>PlayOffset</b> and <b>WriteOffset</b> is considered off-limits to the client because it represents the portion of the client buffer that has already been sent to the driver and might still be in use by the driver.

For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/audio-position-property">Audio Position Property</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksinterface-standard-looped-streaming">KSINTERFACE_STANDARD_LOOPED_STREAMING</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksinterface-standard-streaming">KSINTERFACE_STANDARD_STREAMING</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/audio/ksproperty-audio-position">KSPROPERTY_AUDIO_POSITION</a>
 

 

