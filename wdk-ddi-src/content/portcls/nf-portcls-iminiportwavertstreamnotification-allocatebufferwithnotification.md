---
UID: NF:portcls.IMiniportWaveRTStreamNotification.AllocateBufferWithNotification
title: IMiniportWaveRTStreamNotification::AllocateBufferWithNotification method
author: windows-driver-content
description: The AllocateAudioBufferWithNotification method allocates a cyclic buffer for audio data when you want to implement DMA-driven event notification. If you do not want event notification, you must use IMiniportWaveRTStream::AllocateAudioBuffer.
old-location: audio\iminiportwavertstreamnotification_allocatebufferwithnotification.htm
old-project: audio
ms.assetid: df1da549-1677-42ef-9644-3d9c5df66894
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: AllocateBufferWithNotification, IMiniportWaveRTStreamNotification::AllocateBufferWithNotification, audmp-routines_84faf4d3-ee36-4996-8de2-0f89b41c18fe.xml, AllocateBufferWithNotification method [Audio Devices], IMiniportWaveRTStreamNotification interface, portcls/IMiniportWaveRTStreamNotification::AllocateBufferWithNotification, IMiniportWaveRTStreamNotification interface [Audio Devices], AllocateBufferWithNotification method, audio.iminiportwavertstreamnotification_allocatebufferwithnotification, IMiniportWaveRTStreamNotification, AllocateBufferWithNotification method [Audio Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
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
req.lib: portcls.h
req.dll: 
req.irql: Passive level.
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	portcls.h
apiname:
-	IMiniportWaveRTStreamNotification.AllocateBufferWithNotification
product: Windows
targetos: Windows
req.typenames: "*PPC_EXIT_LATENCY, PC_EXIT_LATENCY"
---

# IMiniportWaveRTStreamNotification::AllocateBufferWithNotification method


## -description


The <code>AllocateAudioBufferWithNotification</code> method allocates a cyclic buffer for audio data when you want to implement DMA-driven event notification.  If you do not want event notification, you must use <b>IMiniportWaveRTStream::AllocateAudioBuffer</b>.


## -syntax


````
NTSTATUS AllocateBufferWithNotification(
  [in]  ULONG               NotificationCount,
  [in]  ULONG               RequestedSize,
  [out] PMDL                *AudioBufferMdl,
  [out] ULONG               *ActualSize,
  [out] ULONG               *OffsetFromFirstPage,
  [out] MEMORY_CACHING_TYPE *CacheType
);
````


## -parameters




#### - NotificationCount [in]

Specifies the number of notifications wanted per buffer cycle.  Valid values are 1 or 2, where 1 indicates a single notification at the end of the cyclic buffer and 2 indicates two notifications per buffer cycle, one at the mid-point of the buffer and one at the end.


#### - RequestedSize [in]

Specifies the requested size, in bytes, of the audio buffer.


#### - AudioBufferMdl [out]

Output pointer for a memory descriptor list (<a href="http://msdn.microsoft.com/en-us/library/windows/hardware/ff554414(v=vs.85).aspx">MDL</a>) that describes the audio buffer. This parameter points to a caller-allocated pointer variable into which the method writes a pointer to the MDL.


#### - ActualSize [out]

Output pointer for the actual size, in bytes, of the allocated buffer. This parameter points to a ULONG variable into which the method writes the size value.


#### - OffsetFromFirstPage [out]

Output pointer for the offset (in bytes) of the buffer, from the start of the first page in the MDL. This parameter points to a caller-allocated ULONG variable into which the method writes the offset value.


#### - CacheType [out]

Specifies the type of caching that the client requests for the audio buffer. This parameter is a <a href="http://msdn.microsoft.com/en-us/library/windows/hardware/ff554430(v=vs.85).aspx">MEMORY_CACHING_TYPE</a> enumeration value


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


<div class="alert"><b>Note</b>  Miniports for Intel High Definition Audio Codecs must specify a CacheType of MmWriteCombined to ensure cache coherency. This is because the Intel High Definition Audio Controller may be configured for non-snoop operation.</div><div> </div>After receiving a <a href="https://msdn.microsoft.com/library/windows/hardware/ff537374">KSPROPERTY_RTAUDIO_BUFFER_WITH_NOTIFICATION</a> request from the client, the port driver calls the <code>AllocateBufferWithNotification</code> method to allocate a cyclic buffer that the port driver can later map to the virtual address space of the client.  <code>AllocateBufferWithNotification</code> operates in a manner similar to <a href="https://msdn.microsoft.com/library/windows/hardware/ff536744">IMiniportWaveRTStream::AllocateAudioBuffer</a>. Additionally, <code>AllocateBufferWithNotification</code> identifies to the WaveRT port driver that DMA-driven event notification is wanted, and it specifies how many notifications per cycle of the cyclic buffer are needed.



## -see-also

<a href="http://msdn.microsoft.com/en-us/library/windows/hardware/ff554414(v=vs.85).aspx">MDL</a>

<a href="http://msdn.microsoft.com/en-us/library/windows/hardware/ff554430(v=vs.85).aspx">MEMORY_CACHING_TYPE</a>

<a href="..\portcls\nn-portcls-iminiportwavertstreamnotification.md">IMiniportWaveRTStreamNotification</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537374">KSPROPERTY_RTAUDIO_BUFFER_WITH_NOTIFICATION</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff536744">IMiniportWaveRTStream::AllocateAudioBuffer</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IMiniportWaveRTStreamNotification::AllocateBufferWithNotification method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

