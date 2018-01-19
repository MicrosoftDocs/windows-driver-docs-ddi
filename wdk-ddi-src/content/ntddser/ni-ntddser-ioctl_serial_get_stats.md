---
UID: NI:ntddser.IOCTL_SERIAL_GET_STATS
title: IOCTL_SERIAL_GET_STATS
author: windows-driver-content
description: The IOCTL_SERIAL_GET_STATS request returns information about the performance of a serial controller.
old-location: serports\ioctl_serial_get_stats.htm
old-project: serports
ms.assetid: 264b8460-acda-46ba-b070-e2956f7cfc50
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: SdBusSubmitRequestAsync
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntddser.h
req.include-header: Ntddser.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_SERIAL_GET_STATS
req.alt-loc: Ntddser.h
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
req.typenames: SD_REQUEST_FUNCTION
---

# IOCTL_SERIAL_GET_STATS IOCTL



## -description
The <b>IOCTL_SERIAL_GET_STATS</b> request returns information about the performance of a serial controller. The statistics include the number of characters transmitted, the number of characters received, and useful error statistics. The driver continuously increments performance values.

To reset the accumulated performance values to zero, a client can use an <a href="..\ntddser\ni-ntddser-ioctl_serial_clear_stats.md">IOCTL_SERIAL_CLEAR_STATS</a> request.



## -ioctlparameters

### -input-buffer
None.


### -input-buffer-length
None.


### -output-buffer
The <b>AssociatedIrp.SystemBuffer</b> member points to a client-allocated <b>SERIALPERF_STATS</b> structure that the serial controller driver uses to output performance information.


### -output-buffer-length
The <b>Parameters.DeviceIoControl.OutputBufferLength</b> member is set to the size, in bytes, of a <a href="..\ntddser\ns-ntddser-_serialperf_stats.md">SERIALPERF_STATS</a> structure.


### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
<b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code. 


## -remarks


## -see-also
<dl>
<dt>
<a href="..\ntddser\ni-ntddser-ioctl_serial_clear_stats.md">IOCTL_SERIAL_CLEAR_STATS</a>
</dt>
<dt>
<a href="..\ntddser\ns-ntddser-_serialperf_stats.md">SERIALPERF_STATS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20IOCTL_SERIAL_GET_STATS control code%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

