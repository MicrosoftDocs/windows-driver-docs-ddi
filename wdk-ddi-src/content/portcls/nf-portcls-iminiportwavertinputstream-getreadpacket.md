---
UID: NF:portcls.IMiniportWaveRTInputStream.GetReadPacket
title: IMiniportWaveRTInputStream::GetReadPacket method
author: windows-driver-content
description: Returns information about captured data.
old-location: audio\iminiportwavertinputstream_getreadpacket.htm
old-project: audio
ms.assetid: F26F6820-B761-4DF3-B7D7-9C1B174DEEA2
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , ,, ., :, G, GetReadPacket method [Audio Devices], GetReadPacket method [Audio Devices], IMiniportWaveRTInputStream interface, GetReadPacket,IMiniportWaveRTInputStream.GetReadPacket, I, IMiniportWaveRTInputStream, IMiniportWaveRTInputStream interface [Audio Devices], GetReadPacket method, IMiniportWaveRTInputStream::GetReadPacket, M, P, R, S, T, W, a, audio.iminiportwavertinputstream_getreadpacket, c, d, e, i, k, m, n, o, p, portcls/IMiniportWaveRTInputStream::GetReadPacket, r, t, u, v"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
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
req.lib: portcls.h
req.dll: 
req.irql: Passive level
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	portcls.h
apiname:
-	IMiniportWaveRTInputStream.GetReadPacket
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IMiniportWaveRTInputStream::GetReadPacket method


## -description




Returns information about captured data. 



## -syntax


````
NTSTATUS GetReadPacket(
  [out] ULONG     *PacketNumber,
  [out] DWORD     *Flags,
  [out] ULONGLONG *PerformanceCounterValue,
  [out] BOOL      *MoreData
);
````


## -parameters




### -param PacketNumber [out]

Returns the packet number relative to the start of capture.  


### -param Flags [out]

Reserved for future use. Must be set to 0.


### -param PerformanceCounterValue [out]

Returns the performance counter value corresponding to the sampling instant of the first sample in the packet. 



### -param MoreData [out]

 Returns <b>TRUE</b> if there is more data ready immediately. The OS may optionally immediately call this routine again after processing the packet to get the next packet information. If the driver returns <b>FALSE</b>, then capture is operating at real time. 



## -returns



<code>GetReadPacket</code> returns STATUS_SUCCESS if the call was successful. Otherwise, the function returns an appropriate error status code.

 STATUS_DEVICE_NOT_READY - The driver returns this error if no new data is available.




## -remarks



Before reading captured audio data from the WaveRT buffer, the OS calls this routine to get information about the available data. 


The packet number identifies a packet within the stream. This resets to zero when the stream is in KSSTATE_STOP. The number advances with each captured buffer. From the packet number the OS can derive the packet location within the WaveRT buffer and can also derive the stream position of the packet relative to start of stream. 


The packet size is the WaveRT buffer size divided by the NotificationCount passed to <a href="https://msdn.microsoft.com/library/windows/hardware/ff536740">IMiniportWaveRTStreamNotification::AllocateBufferWithNotification</a>. The OS may call this routine at any time. In normal operation, the OS calls this routine after the driver sets the buffer notification event or after a previous call returns true for MoreData. When the OS calls this routine, the driver may assume that the OS has finished reading all previous packets. If the hardware has captured enough data, the driver may immediately burst the next complete packet to the WaveRT buffer and set the buffer event again.In the case of capture overflow (when the OS does not read data quickly enough) the audio driver may drop or overwrite some audio data. The audio driver drops or overwrites oldest data first, The audio driver may continue to advance its internal packet counter even though the OS may not have read the data.  





## -see-also

<a href="..\portcls\nn-portcls-iminiportwavertinputstream.md">IMiniportWaveRTInputStream</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IMiniportWaveRTInputStream::GetReadPacket method%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

