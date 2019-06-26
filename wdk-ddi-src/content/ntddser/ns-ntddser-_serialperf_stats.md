---
UID: NS:ntddser._SERIALPERF_STATS
title: _SERIALPERF_STATS (ntddser.h)
description: The SERIALPERF_STATS structure contains performance statistics for a serial port.
old-location: serports\serialperf_stats.htm
tech.root: serports
ms.assetid: 47CAAF39-40C6-4D7F-B8DA-5A60768E4CB0
ms.date: 04/23/2018
ms.keywords: "*PSERIALPERF_STATS, PSERIALPERF_STATS, PSERIALPERF_STATS structure pointer [Serial Ports], SERIALPERF_STATS, SERIALPERF_STATS structure [Serial Ports], _SERIALPERF_STATS, ntddser/PSERIALPERF_STATS, ntddser/SERIALPERF_STATS, serports.serialperf_stats"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Ntddser.h
api_name:
- SERIALPERF_STATS
product:
- Windows
targetos: Windows
req.typenames: SERIALPERF_STATS, *PSERIALPERF_STATS
---

# _SERIALPERF_STATS structure


## -description


The <b>SERIALPERF_STATS</b> structure contains performance statistics for a serial port.


## -struct-fields




### -field ReceivedCount

The number of characters received since either the serial port was opened or the last <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddser/ni-ntddser-ioctl_serial_clear_stats">IOCTL_SERIAL_CLEAR_STATS</a> request was processed.


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



This structure is used by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddser/ni-ntddser-ioctl_serial_get_stats">IOCTL_SERIAL_GET_STATS</a> request.

To reset the performance statistics to zero, send an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddser/ni-ntddser-ioctl_serial_clear_stats">IOCTL_SERIAL_CLEAR_STATS</a> request.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddser/ni-ntddser-ioctl_serial_clear_stats">IOCTL_SERIAL_CLEAR_STATS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddser/ni-ntddser-ioctl_serial_get_stats">IOCTL_SERIAL_GET_STATS</a>
 

 

