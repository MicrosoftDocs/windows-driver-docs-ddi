---
UID: NF:portcls.IMiniportWaveCyclicStream.GetPosition
title: IMiniportWaveCyclicStream::GetPosition method
author: windows-driver-content
description: The GetPosition method gets the current position of the stream.
old-location: audio\iminiportwavecyclicstream_getposition.htm
old-project: audio
ms.assetid: a0d59215-5201-4e1a-9cb2-d9ff6109c3bb
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: GetPosition, audio.iminiportwavecyclicstream_getposition, audmp-routines_016da0e2-bc56-4c06-9755-a13b75d6c5c9.xml, IMiniportWaveCyclicStream, GetPosition method [Audio Devices], IMiniportWaveCyclicStream interface [Audio Devices], GetPosition method, portcls/IMiniportWaveCyclicStream::GetPosition, IMiniportWaveCyclicStream::GetPosition, GetPosition method [Audio Devices], IMiniportWaveCyclicStream interface
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
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
req.lib: portcls.h
req.dll: 
req.irql: <=DISPATCH_LEVEL
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	COM
apilocation: 
-	portcls.h
apiname: 
-	IMiniportWaveCyclicStream.GetPosition
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IMiniportWaveCyclicStream::GetPosition method


## -description


The <code>GetPosition</code> method gets the current position of the stream.


## -syntax


````
NTSTATUS GetPosition(
  [out] PULONG Position
);
````


## -parameters




### -param Position [out]

Output pointer for the position value. This parameter points to a caller-allocated variable into which the method writes the current byte position of the stream.


## -returns


<code>GetPosition</code> returns STATUS_SUCCESS if the call was successful. Otherwise, the method returns an appropriate error code.



## -remarks


<code>GetPosition</code> reports the stream's current play or record position. The position is expressed as a byte offset from the beginning of the DMA buffer and represents the miniport driver's best estimate of the byte position of the data currently in the DAC or ADC.

The position is zero immediately following initialization of the stream. A transition to the KSSTATE_STOP state (see <a href="..\ks\ne-ks-pksstate.md">KSSTATE</a>) resets the position to zero. When the stream is halted by a transition from KSSTATE_RUN to KSSTATE_PAUSE or KSSTATE_ACQUIRE, the position freezes. It unfreezes when the stream transitions from KSSTATE_PAUSE or KSSTATE_ACQUIRE back to KSSTATE_RUN.

<code>GetPosition</code> specifies the position as an offset into the cyclic buffer. When the position reaches the end of the cyclic buffer, it wraps around to the beginning of the buffer. Hence, the position never exceeds the buffer size.

Note that the offset value retrieved by a <code>GetPosition</code> call is one of the following:
<ul>
<li>
For a render stream, the <code>GetPosition</code> method retrieves the play position, which is the byte offset of the sample that is currently being played through the DAC and transmitted through the speaker jack.

</li>
<li>
For a capture stream, the <code>GetPosition</code> method retrieves the record position, which is the byte offset of the latest sample to be received through the microphone jack and captured by the ADC.

</li>
</ul>It is not the offset of the sample that the DMA engine in the audio device is currently reading from or writing to the audio buffer.

Some audio hardware contains a position register to keep track of the byte offset of the sample currently in each DAC or ADC, in which case the <code>GetPosition</code> method simply retrieves the contents of the position register for the appropriate stream. Other audio hardware can only supply the driver with DMA pointers into the audio buffers, in which case the <code>GetPosition</code> method must provide a best estimate of the byte offset in the DAC or ADC based on the current DMA position and the buffering delays internal to the device.

Audio hardware that internally buffers a portion of a playback or capture stream might make a precise position reading more difficult to obtain. In this case, the driver should estimate the current position as accurately as possible. For example, if an audio device prefetches the playback stream into an internal buffer, the driver might need to take both the buffer size and timing information into account in order to properly estimate the play position.

The WaveCyclic port driver implements a property handler for <a href="https://msdn.microsoft.com/library/windows/hardware/ff537297">KSPROPERTY_AUDIO_POSITION</a>. This property handler calls the <code>GetPosition</code> method to obtain the current play or record position from the miniport driver. For more information, see <a href="https://msdn.microsoft.com/893fea84-9136-4107-96d2-8a4e2ab7bd2a">Audio Position Property</a>. 



## -see-also

<a href="..\portcls\nn-portcls-iminiportwavecyclicstream.md">IMiniportWaveCyclicStream</a>

<a href="..\ks\ne-ks-pksstate.md">KSSTATE</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537297">KSPROPERTY_AUDIO_POSITION</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IMiniportWaveCyclicStream::GetPosition method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

