---
UID: NI:ntddser.IOCTL_SERIAL_LSRMST_INSERT
title: IOCTL_SERIAL_LSRMST_INSERT
author: windows-driver-content
description: The IOCTL_SERIAL_LSRMST_INSERT request enables or disables the insertion of information about line status and modem status in the receive data stream.
old-location: serports\ioctl_serial_lsrmst_insert.htm
old-project: serports
ms.assetid: 363ae373-5474-4c20-a382-20577a72521e
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
req.alt-api: IOCTL_SERIAL_LSRMST_INSERT
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

# IOCTL_SERIAL_LSRMST_INSERT IOCTL



## -description
The <b>IOCTL_SERIAL_LSRMST_INSERT</b> request enables or disables the insertion of information about line status and modem status in the receive data stream. If LSRMST insertion is enabled, the driver inserts event information for the supported event types. The event information includes an <i>event header</i> followed by event-specific data.

The event header contains a client-specified escape character and a SERIAL_LSRMST_<i>XXX</i> constant that indicates the event type. The driver supports the following event types:



A change occurred in the line status. The serial controller driver inserts an event header followed by the event-specific data, which is the value of the line status register followed by the character present in the receive hardware when the line-status change was processed.

A line status change occurred, but no data was available in the receive buffer. The serial controller driver inserts an event header followed by the event-specific data, which is the value of the line status register when the line status change was processed.

A change occurred in the modem status. The serial controller driver inserts an event header followed by the event-specific data, which is the value of the modem status register when the modem-status change was processed.

Indicates that the next character in the receive data stream, which was received from the device, is identical to the client-specified escape character. The serial controller driver inserts an event header. There is no event-specific data.



## -ioctlparameters

### -input-buffer
The <b>AssociatedIrp.SystemBuffer</b> member points to a client-allocated UCHAR input value to use as the escape character. If the escape character is nonzero, insertion is enabled, and the serial driver uses the specified escape character. Otherwise, insertion is disabled.


### -input-buffer-length
The <b>Parameters.DeviceIoControl.InputBufferLength</b> member is set to the size, in bytes, of a UCHAR.


### -output-buffer
None.


### -output-buffer-length
None.


### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
If the request is successful, the <b>Information</b> member is set to the size, in bytes, of a UCHAR. Otherwise, <b>Information</b> is set to zero.

The <b>Status</b> member is set to one of the <a href="serial_device_control_requests.htm#generic_status_values_for_serial_device_control_requests">Generic Status Values for Serial Device Control Requests</a>. A status of STATUS_INVALID_PARAMETER indicates that the specified escape character is the same as the XON (transmit on) or the XOFF (transmit off) character, or that error replacement is enabled with handshake flow control.


## -remarks
