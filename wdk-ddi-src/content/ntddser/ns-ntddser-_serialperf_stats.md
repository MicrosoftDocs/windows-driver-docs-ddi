---
UID: NS:ntddser._SERIALPERF_STATS
title: "_SERIALPERF_STATS"
author: windows-driver-content
description: The SERIALPERF_STATS structure contains performance statistics for a serial port.
old-location: serports\serialperf_stats.htm
old-project: serports
ms.assetid: 47CAAF39-40C6-4D7F-B8DA-5A60768E4CB0
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: ntddser/PSERIALPERF_STATS, _SERIALPERF_STATS, ntddser/SERIALPERF_STATS, SERIALPERF_STATS, *PSERIALPERF_STATS, PSERIALPERF_STATS, PSERIALPERF_STATS structure pointer [Serial Ports], serports.serialperf_stats, SERIALPERF_STATS structure [Serial Ports]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddser.h
req.include-header: 
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ntddser.h
apiname:
-	SERIALPERF_STATS
product: Windows
targetos: Windows
req.typenames: "*PSERIALPERF_STATS, SERIALPERF_STATS"
---

# _SERIALPERF_STATS structure


## -description


The <b>SERIALPERF_STATS</b> structure contains performance statistics for a serial port.


## -syntax


````
typedef struct _SERIALPERF_STATS {
  ULONG ReceivedCount;
  ULONG TransmittedCount;
  ULONG FrameErrorCount;
  ULONG SerialOverrunErrorCount;
  ULONG BufferOverrunErrorCount;
  ULONG ParityErrorCount;
} SERIALPERF_STATS, *PSERIALPERF_STATS;
````


## -struct-fields




### -field ReceivedCount

The number of characters received since either the serial port was opened or the last <a href="..\ntddser\ni-ntddser-ioctl_serial_clear_stats.md">IOCTL_SERIAL_CLEAR_STATS</a> request was processed.


### -field TransmittedCount

The number of characters transmitted since either the serial port was opened or the last <b>IOCTL_SERIAL_CLEAR_STATS</b> request was processed.


### -field FrameErrorCount

The number of frame errors detected since either the serial port was opened or the last <b>IOCTL_SERIAL_CLEAR_STATS</b> request was processed.


### -field SerialOverrunErrorCount

The number of serial overrun errors detected since either the serial port was opened or the last <b>IOCTL_SERIAL_CLEAR_STATS</b> request was processed.


### -field BufferOverrunErrorCount

The number of buffer overrun errors detected since either the serial port was opened or the last <b>IOCTL_SERIAL_CLEAR_STATS</b> request was processed.


### -field ParityErrorCount

The number of parity errors detected since either the serial port was opened or the last <b>IOCTL_SERIAL_CLEAR_STATS</b> request was processed.


## -remarks


This structure is used by the <a href="..\ntddser\ni-ntddser-ioctl_serial_get_stats.md">IOCTL_SERIAL_GET_STATS</a> request.

To reset the performance statistics to zero, send an <a href="..\ntddser\ni-ntddser-ioctl_serial_clear_stats.md">IOCTL_SERIAL_CLEAR_STATS</a> request.



## -see-also

<a href="..\ntddser\ni-ntddser-ioctl_serial_get_stats.md">IOCTL_SERIAL_GET_STATS</a>

<a href="..\ntddser\ni-ntddser-ioctl_serial_clear_stats.md">IOCTL_SERIAL_CLEAR_STATS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20SERIALPERF_STATS structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

