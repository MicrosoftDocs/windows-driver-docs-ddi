---
UID: NI:ntddser.IOCTL_SERIAL_PURGE
title: IOCTL_SERIAL_PURGE (ntddser.h)
description: The IOCTL_SERIAL_PURGE request cancels the specified requests and deletes data from the specified buffers.
old-location: serports\ioctl_serial_purge.htm
tech.root: serports
ms.date: 05/20/2022
keywords: ["IOCTL_SERIAL_PURGE IOCTL"]
ms.keywords: IOCTL_SERIAL_PURGE, IOCTL_SERIAL_PURGE control, IOCTL_SERIAL_PURGE control code [Serial Ports], ntddser/IOCTL_SERIAL_PURGE, serports.ioctl_serial_purge, serref_d52cfcec-8098-4319-b601-14187a77e438.xml
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IOCTL_SERIAL_PURGE
 - ntddser/IOCTL_SERIAL_PURGE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntddser.h
api_name:
 - IOCTL_SERIAL_PURGE
---

# IOCTL_SERIAL_PURGE IOCTL


## -description

The <b>IOCTL_SERIAL_PURGE</b> request cancels the specified requests and deletes data from the specified buffers. The purge request can be used to cancel all read requests and write requests and to delete all data from the receive buffer and the transmit buffer.

The completion of the purge request does not indicate that the requests canceled by the purge request are completed. A client must verify that the purged requests are completed before the client frees or reuses the corresponding IRPs.

## -ioctlparameters

### -input-buffer

The <b>AssociatedIrp.SystemBuffer</b> member points to a client-allocated ULONG that is used to input a <i>purge mask</i>. The client sets the purge mask to a bitwise-OR of one or more of the following purge flags:

SERIAL_PURGE_RXABORT
<ul>
Purges all read (IRP_MJ_READ) requests.
</ul>

SERIAL_PURGE_RXCLEAR 
<ul>
Purges the receive buffer, if one exists.
</ul>

SERIAL_PURGE_TXABORT 
<ul>
Purges all write (IRP_MJ_WRITE) requests.
</ul>

SERIAL_PURGE_TXCLEAR 
<ul>
Purges the transmit buffer, if one exists.
</ul>

### -input-buffer-length

The <b>Parameters.DeviceIoControl.InputBufferLength</b> member is set to the size, in bytes, of a ULONG.

### -output-buffer

None.

### -output-buffer-length

None.

### -in-out-buffer

### -inout-buffer-length

### -status-block

If the request is successful, the <b>Information</b> member is set to the size, in bytes, of a ULONG. Otherwise, the <b>Information</b> member is set to zero.

The <b>Status</b> member is set to one of the <a href="/windows-hardware/drivers/serports/serial-device-control-requests2">Generic Status Values for Serial Device Control Requests</a>. A status of STATUS_INVALID_PARAMETER indicates that the purge mask is not valid.

## -SERIAL_PURGE_RXABORT

Purges all read (<a href="/windows-hardware/drivers/ifs/irp-mj-read">IRP_MJ_READ</a>) requests.

## -SERIAL_PURGE_RXCLEAR

Purges the receive buffer, if one exists.

## -SERIAL_PURGE_TXABORT

Purges all write (<a href="/windows-hardware/drivers/kernel/irp-mj-write">IRP_MJ_WRITE</a>) requests.

## -SERIAL_PURGE_TXCLEAR

Purges the transmit buffer, if one exists.

## -remarks

Serial.sys and SerCx allow an <b>IOCTL_SERIAL_PURGE</b> request to specify any combination of one or more SERIAL_PURGE_<i>XXX</i> flags. However, SerCx2 is more restrictive.

SerCx2 requires that all read requests be purged if the receive buffer is purged. Thus, if the SERIAL_PURGE_RXCLEAR flag is set in an <b>IOCTL_SERIAL_PURGE</b> request, then either the SerCx2 I/O request queue must not contain any read requests, or the SERIAL_PURGE_RXABORT flag must be set. Otherwise, the <b>IOCTL_SERIAL_PURGE</b> request fails with a STATUS_INVALID_DEVICE_STATE status code.

Similarly, SerCx2 requires that all write requests be purged if the transmit buffer is purged. Thus, if the SERIAL_PURGE_TXCLEAR flag is set in an <b>IOCTL_SERIAL_PURGE</b> request, then either the SerCx2 I/O request queue must not contain any write requests, or the SERIAL_PURGE_TXABORT flag must be set. Otherwise, the <b>IOCTL_SERIAL_PURGE</b> request fails with a STATUS_INVALID_DEVICE_STATE status code.

For more information about SerCx2, SerCx, and Serial.sys, see <a href="/previous-versions/jj241971(v=vs.85)">Serial Controller Drivers Overview</a>.
