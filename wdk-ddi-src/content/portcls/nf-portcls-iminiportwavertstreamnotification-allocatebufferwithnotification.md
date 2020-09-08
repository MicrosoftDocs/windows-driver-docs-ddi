---
UID: NF:portcls.IMiniportWaveRTStreamNotification.AllocateBufferWithNotification
title: IMiniportWaveRTStreamNotification::AllocateBufferWithNotification (portcls.h)
description: The AllocateAudioBufferWithNotification method allocates a cyclic buffer for audio data when you want to implement DMA-driven event notification. If you do not want event notification, you must use IMiniportWaveRTStream::AllocateAudioBuffer.
old-location: audio\iminiportwavertstreamnotification_allocatebufferwithnotification.htm
tech.root: audio
ms.assetid: df1da549-1677-42ef-9644-3d9c5df66894
ms.date: 05/08/2018
keywords: ["IMiniportWaveRTStreamNotification::AllocateBufferWithNotification"]
ms.keywords: AllocateBufferWithNotification, AllocateBufferWithNotification method [Audio Devices], AllocateBufferWithNotification method [Audio Devices],IMiniportWaveRTStreamNotification interface, IMiniportWaveRTStreamNotification interface [Audio Devices],AllocateBufferWithNotification method, IMiniportWaveRTStreamNotification.AllocateBufferWithNotification, IMiniportWaveRTStreamNotification::AllocateBufferWithNotification, audio.iminiportwavertstreamnotification_allocatebufferwithnotification, audmp-routines_84faf4d3-ee36-4996-8de2-0f89b41c18fe.xml, portcls/IMiniportWaveRTStreamNotification::AllocateBufferWithNotification
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
 - IMiniportWaveRTStreamNotification::AllocateBufferWithNotification
 - portcls/IMiniportWaveRTStreamNotification::AllocateBufferWithNotification
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - portcls.h
api_name:
 - IMiniportWaveRTStreamNotification.AllocateBufferWithNotification
---

# IMiniportWaveRTStreamNotification::AllocateBufferWithNotification


## -description

The <code>AllocateAudioBufferWithNotification</code> method allocates a cyclic buffer for audio data when you want to implement DMA-driven event notification.  If you do not want event notification, you must use <b>IMiniportWaveRTStream::AllocateAudioBuffer</b>.

## -parameters

### -param NotificationCount 

[in]
Specifies the number of notifications wanted per buffer cycle.  Valid values are 1 or 2, where 1 indicates a single notification at the end of the cyclic buffer and 2 indicates two notifications per buffer cycle, one at the mid-point of the buffer and one at the end.

### -param RequestedSize 

[in]
Specifies the requested size, in bytes, of the audio buffer.

### -param AudioBufferMdl 

[out]
Output pointer for a memory descriptor list (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_mdl">MDL</a>) that describes the audio buffer. This parameter points to a caller-allocated pointer variable into which the method writes a pointer to the MDL.

### -param ActualSize 

[out]
Output pointer for the actual size, in bytes, of the allocated buffer. This parameter points to a ULONG variable into which the method writes the size value.

### -param OffsetFromFirstPage 

[out]
Output pointer for the offset (in bytes) of the buffer, from the start of the first page in the MDL. This parameter points to a caller-allocated ULONG variable into which the method writes the offset value.

### -param CacheType 

[out]
Specifies the type of caching that the client requests for the audio buffer. This parameter is a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ne-wdm-_memory_caching_type">MEMORY_CACHING_TYPE</a> enumeration value

## -returns

<code>AllocateBufferWithNotification</code> returns STATUS_SUCCESS if the call was successful. Otherwise, the method returns an appropriate error status code. The following table shows some of the possible error status codes.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_UNSUCCESSFUL</b></dt>
</dl>
</td>
<td width="60%">
The driver does not support the specified combination of buffer attributes.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
There is insufficient memory available to allocate the buffer.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_DEVICE_NOT_READY</b></dt>
</dl>
</td>
<td width="60%">
The device is not ready.

</td>
</tr>
</table>

## -remarks

<div class="alert"><b>Note</b>  Miniports for Intel High Definition Audio Codecs must specify a CacheType of MmWriteCombined to ensure cache coherency. This is because the Intel High Definition Audio Controller may be configured for non-snoop operation.</div>
<div> </div>
After receiving a <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/ksproperty-rtaudio-buffer-with-notification">KSPROPERTY_RTAUDIO_BUFFER_WITH_NOTIFICATION</a> request from the client, the port driver calls the <code>AllocateBufferWithNotification</code> method to allocate a cyclic buffer that the port driver can later map to the virtual address space of the client.  <code>AllocateBufferWithNotification</code> operates in a manner similar to <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff536744(v=vs.85)">IMiniportWaveRTStream::AllocateAudioBuffer</a>. Additionally, <code>AllocateBufferWithNotification</code> identifies to the WaveRT port driver that DMA-driven event notification is wanted, and it specifies how many notifications per cycle of the cyclic buffer are needed.

## -see-also

<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff536744(v=vs.85)">IMiniportWaveRTStream::AllocateAudioBuffer</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nn-portcls-iminiportwavertstreamnotification">IMiniportWaveRTStreamNotification</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/audio/ksproperty-rtaudio-buffer-with-notification">KSPROPERTY_RTAUDIO_BUFFER_WITH_NOTIFICATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_mdl">MDL</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ne-wdm-_memory_caching_type">MEMORY_CACHING_TYPE</a>

