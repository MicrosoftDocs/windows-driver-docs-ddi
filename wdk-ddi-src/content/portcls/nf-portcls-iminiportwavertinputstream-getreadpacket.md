---
UID: NF:portcls.IMiniportWaveRTInputStream.GetReadPacket
title: IMiniportWaveRTInputStream::GetReadPacket (portcls.h)
description: Returns information about captured data.
old-location: audio\iminiportwavertinputstream_getreadpacket.htm
tech.root: audio
ms.date: 05/08/2018
keywords: ["IMiniportWaveRTInputStream::GetReadPacket"]
ms.keywords: GetReadPacket, GetReadPacket method [Audio Devices], GetReadPacket method [Audio Devices],IMiniportWaveRTInputStream interface, IMiniportWaveRTInputStream interface [Audio Devices],GetReadPacket method, IMiniportWaveRTInputStream.GetReadPacket, IMiniportWaveRTInputStream::GetReadPacket, audio.iminiportwavertinputstream_getreadpacket, portcls/IMiniportWaveRTInputStream::GetReadPacket
req.header: portcls.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 10 and later.
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
req.irql: Passive level
targetos: Windows
req.typenames: 
f1_keywords:
 - IMiniportWaveRTInputStream::GetReadPacket
 - portcls/IMiniportWaveRTInputStream::GetReadPacket
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - portcls.h
api_name:
 - IMiniportWaveRTInputStream.GetReadPacket
---

# IMiniportWaveRTInputStream::GetReadPacket


## -description

Returns information about captured data.

## -parameters

### -param PacketNumber 

[out]
Returns the packet number relative to the start of capture.

### -param Flags 

[out]
Reserved for future use. Must be set to 0.

### -param PerformanceCounterValue 

[out]
Returns the performance counter value corresponding to the sampling instant of the first sample in the packet.

### -param MoreData 

[out]
 Returns <b>TRUE</b> if there is more data ready immediately. The OS may optionally immediately call this routine again after processing the packet to get the next packet information. If the driver returns <b>FALSE</b>, then capture is operating at real time.

## -returns

<code>GetReadPacket</code> returns STATUS_SUCCESS if the call was successful. Otherwise, the function returns an appropriate error status code.

 STATUS_DEVICE_NOT_READY - The driver returns this error if no new data is available.

## -remarks

Before reading captured audio data from the WaveRT buffer, the OS calls this routine to get information about the available data. 


The packet number identifies a packet within the stream. This resets to zero when the stream is in KSSTATE_STOP. The number advances with each captured buffer. From the packet number the OS can derive the packet location within the WaveRT buffer and can also derive the stream position of the packet relative to start of stream. 


The packet size is the WaveRT buffer size divided by the NotificationCount passed to <a href="/windows-hardware/drivers/ddi/portcls/nf-portcls-iminiportwavertstreamnotification-allocatebufferwithnotification">IMiniportWaveRTStreamNotification::AllocateBufferWithNotification</a>. The OS may call this routine at any time. In normal operation, the OS calls this routine after the driver sets the buffer notification event or after a previous call returns true for MoreData. When the OS calls this routine, the driver may assume that the OS has finished reading all previous packets. If the hardware has captured enough data, the driver may immediately burst the next complete packet to the WaveRT buffer and set the buffer event again.In the case of capture overflow (when the OS does not read data quickly enough) the audio driver may drop or overwrite some audio data. The audio driver drops or overwrites oldest data first, The audio driver may continue to advance its internal packet counter even though the OS may not have read the data.

## -see-also

<a href="/windows-hardware/drivers/ddi/portcls/nn-portcls-iminiportwavertinputstream">IMiniportWaveRTInputStream</a>
