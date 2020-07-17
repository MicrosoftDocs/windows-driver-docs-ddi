---
UID: NF:portcls.IMiniportWavePciStream.GetPosition
title: IMiniportWavePciStream::GetPosition (portcls.h)
description: The GetPosition method gets the current position of the stream.
old-location: audio\iminiportwavepcistream_getposition.htm
tech.root: audio
ms.assetid: 61575632-62f8-47d3-9249-5f5416191dfa
ms.date: 05/08/2018
keywords: ["IMiniportWavePciStream::GetPosition"]
ms.keywords: GetPosition, GetPosition method [Audio Devices], GetPosition method [Audio Devices],IMiniportWavePciStream interface, IMiniportWavePciStream interface [Audio Devices],GetPosition method, IMiniportWavePciStream.GetPosition, IMiniportWavePciStream::GetPosition, audio.iminiportwavepcistream_getposition, audmp-routines_32855554-86ce-4549-af40-700b7b8fcaad.xml, portcls/IMiniportWavePciStream::GetPosition
f1_keywords:
 - "portcls/IMiniportWavePciStream.GetPosition"
 - "IMiniportWavePciStream.GetPosition"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- portcls.h
api_name:
- IMiniportWavePciStream.GetPosition
product:
- Windows
targetos: Windows
req.typenames: 
---

# IMiniportWavePciStream::GetPosition


## -description


The <code>GetPosition</code> method gets the current position of the stream.


## -parameters




### -param Position [out]

Output pointer for the position value. This parameter points to a caller-allocated ULONGLONG variable into which the method writes the current byte position of the stream.


## -returns



<code>GetPosition</code> returns STATUS_SUCCESS if the call was successful. Otherwise, the method returns an appropriate error code.




## -remarks



The position indicated by the <code>GetPosition</code> method is expressed as a byte offset from the beginning of the stream. It represents the miniport driver's best estimate of the byte position of the data currently in the DAC or ADC. The miniport object is required to maintain stream position based on the mappings it acquires, regardless of whether mappings are released or revoked.

The position is zero immediately following initialization of the stream. A transition to the KSSTATE_STOP state (see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ne-ks-ksstate">KSSTATE</a>) resets the position to zero. When the stream is halted by a transition from KSSTATE_RUN to KSSTATE_PAUSE or KSSTATE_ACQUIRE, the position freezes. It unfreezes when the stream transitions from KSSTATE_PAUSE or KSSTATE_ACQUIRE back to KSSTATE_RUN.

The position reported by <code>GetPosition</code> is not an offset into any one physical buffer that either your driver has allocated or a client has allocated. Instead, the offset is stream-relative and can be thought of as an offset into an idealized buffer that contains the entire stream and is contiguous from beginning to end. Any internal offsets that point into the actual physical buffers that contain the data need to be maintained separately.

Note that the offset value retrieved by a <code>GetPosition</code> call is one of the following:

<ul>
<li>
For a render stream, the <code>GetPosition</code> method retrieves the <i>play position</i>, which is the byte offset of the sample that is currently being played through the DAC and transmitted through the speaker jack.

</li>
<li>
For a capture stream, the <code>GetPosition</code> method retrieves the <i>record position</i>, which is the byte offset of the latest sample to be received through the microphone jack and captured by the ADC.

</li>
</ul>
It is not the offset of the sample that the DMA engine in the audio device is currently reading from or writing to the audio buffer.

Some audio hardware contains a position register to keep track of the byte offset of the sample currently in each DAC or ADC, in which case the <code>GetPosition</code> method simply retrieves the contents of the position register for the appropriate stream. Other audio hardware can only supply the driver with DMA pointers into the audio buffers, in which case the <code>GetPosition</code> method must provide a best estimate of the byte offset in the DAC or ADC based on the current DMA position and the buffering delays internal to the device.

Audio hardware that internally buffers a portion of a playback or capture stream might make a precise position reading more difficult to obtain. In this case, the driver should estimate the current position as accurately as possible. For example, if an audio device prefetches the playback stream into an internal buffer, the driver might need to take both the buffer size and timing information into account in order to properly estimate the play position.

The WavePci port driver implements a property handler for <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/ksproperty-audio-position">KSPROPERTY_AUDIO_POSITION</a>. This property handler calls the <code>GetPosition</code> method to obtain the current play or record position from the miniport driver. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/audio-position-property">Audio Position Property</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nn-portcls-iminiportwavepcistream">IMiniportWavePciStream</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/audio/ksproperty-audio-position">KSPROPERTY_AUDIO_POSITION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ne-ks-ksstate">KSSTATE</a>
 

 

