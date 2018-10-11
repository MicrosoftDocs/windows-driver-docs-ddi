---
UID: NI:ntddser.IOCTL_SERIAL_LSRMST_INSERT
title: IOCTL_SERIAL_LSRMST_INSERT
author: windows-driver-content
description: The IOCTL_SERIAL_LSRMST_INSERT request enables or disables the insertion of information about line status and modem status in the receive data stream.
old-location: serports\ioctl_serial_lsrmst_insert.htm
tech.root: serports
ms.assetid: 363ae373-5474-4c20-a382-20577a72521e
ms.author: windowsdriverdev
ms.date: 4/23/2018
ms.keywords: IOCTL_SERIAL_LSRMST_INSERT, IOCTL_SERIAL_LSRMST_INSERT control, IOCTL_SERIAL_LSRMST_INSERT control code [Serial Ports], ntddser/IOCTL_SERIAL_LSRMST_INSERT, serports.ioctl_serial_lsrmst_insert, serref_d071ffb1-f8ea-44e3-8caa-08e2c51e0198.xml
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ntddser.h
api_name:
-	IOCTL_SERIAL_LSRMST_INSERT
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_SERIAL_LSRMST_INSERT IOCTL


## -description


The <b>IOCTL_SERIAL_LSRMST_INSERT</b> request enables or disables the insertion of information about line status and modem status in the receive data stream. If LSRMST insertion is enabled, the driver inserts event information for the supported event types. The event information includes an <i>event header</i> followed by event-specific data.

The event header contains a client-specified escape character and a SERIAL_LSRMST_<i>XXX</i> constant that indicates the event type. The driver supports the following event types:


<dl>
<dt><a id="SERIAL_LSRMST_LSR_DATA"></a><a id="serial_lsrmst_lsr_data"></a>SERIAL_LSRMST_LSR_DATA</dt>
<dd>
A change occurred in the line status. The serial controller driver inserts an event header followed by the event-specific data, which is the value of the line status register followed by the character present in the receive hardware when the line-status change was processed.

</dd>
<dt><a id="SERIAL_LSRMST_LSR_NODATA"></a><a id="serial_lsrmst_lsr_nodata"></a>SERIAL_LSRMST_LSR_NODATA</dt>
<dd>
A line status change occurred, but no data was available in the receive buffer. The serial controller driver inserts an event header followed by the event-specific data, which is the value of the line status register when the line status change was processed.

</dd>
<dt><a id="SERIAL_LSRMST_MST"></a><a id="serial_lsrmst_mst"></a>SERIAL_LSRMST_MST</dt>
<dd>
A change occurred in the modem status. The serial controller driver inserts an event header followed by the event-specific data, which is the value of the modem status register when the modem-status change was processed.

</dd>
<dt><a id="SERIAL_LSRMST_ESCAPE"></a><a id="serial_lsrmst_escape"></a>SERIAL_LSRMST_ESCAPE</dt>
<dd>
Indicates that the next character in the receive data stream, which was received from the device, is identical to the client-specified escape character. The serial controller driver inserts an event header. There is no event-specific data.

</dd>
</dl>

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








### -inout-buffer-length








### -status-block

If the request is successful, the <b>Information</b> member is set to the size, in bytes, of a UCHAR. Otherwise, <b>Information</b> is set to zero.

The <b>Status</b> member is set to one of the <a href="https://docs.microsoft.com/windows-hardware/drivers/serports/serial-device-control-requests2">Generic Status Values for Serial Device Control Requests</a>. A status of STATUS_INVALID_PARAMETER indicates that the specified escape character is the same as the XON (transmit on) or the XOFF (transmit off) character, or that error replacement is enabled with handshake flow control.

