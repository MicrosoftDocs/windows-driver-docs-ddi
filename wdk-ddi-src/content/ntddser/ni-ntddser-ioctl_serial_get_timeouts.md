---
UID: NI:ntddser.IOCTL_SERIAL_GET_TIMEOUTS
title: IOCTL_SERIAL_GET_TIMEOUTS (ntddser.h)
description: The IOCTL_SERIAL_GET_TIMEOUTS request returns the time-out values that the serial controller driver uses with read and write requests.
old-location: serports\ioctl_serial_get_timeouts.htm
tech.root: serports
ms.date: 04/23/2018
keywords: ["IOCTL_SERIAL_GET_TIMEOUTS IOCTL"]
ms.keywords: IOCTL_SERIAL_GET_TIMEOUTS, IOCTL_SERIAL_GET_TIMEOUTS control, IOCTL_SERIAL_GET_TIMEOUTS control code [Serial Ports], ntddser/IOCTL_SERIAL_GET_TIMEOUTS, serports.ioctl_serial_get_timeouts, serref_7e3bc962-fbe3-4474-bf7b-1fc035a39a29.xml
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
 - IOCTL_SERIAL_GET_TIMEOUTS
 - ntddser/IOCTL_SERIAL_GET_TIMEOUTS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntddser.h
api_name:
 - IOCTL_SERIAL_GET_TIMEOUTS
---

# IOCTL_SERIAL_GET_TIMEOUTS IOCTL


## -description

The <b>IOCTL_SERIAL_GET_TIMEOUTS</b> request returns the time-out values that the serial controller driver uses with read and write requests.

To set time-outs, a client can use an <a href="/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_set_timeouts">IOCTL_SERIAL_SET_TIMEOUTS</a> request. 

For more information about time-outs, see <a href="/previous-versions/ff547486(v=vs.85)">Setting Read and Write Time-Outs for a Serial Device</a>.

## -ioctlparameters

### -ioctl-major-code

### -input-buffer

None.

### -input-buffer-length

None.

### -output-buffer

The <b>AssociatedIrp.SystemBuffer</b> member points to a client-allocated <b>SERIAL_TIMEOUTS</b> structure that the serial controller driver uses to output information about read and write time-out values.

### -output-buffer-length

The <b>Parameters.DeviceIoControl.OutputBufferLength</b> member is set to the size, in bytes, of a <a href="/windows-hardware/drivers/ddi/ntddser/ns-ntddser-_serial_timeouts">SERIAL_TIMEOUTS</a> structure.

### -in-out-buffer

### -inout-buffer-length

### -status-block

If the request is successful, the <b>Information</b> member is set to the size, in bytes, of a <a href="/windows-hardware/drivers/ddi/ntddser/ns-ntddser-_serial_timeouts">SERIAL_TIMEOUTS</a> structure. Otherwise, the <b>Information</b> member is set to zero.

The <b>Status</b> member is set to one of the <a href="/windows-hardware/drivers/serports/serial-device-control-requests2">Generic Status Values for Serial Device Control Requests</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_set_timeouts">IOCTL_SERIAL_SET_TIMEOUTS</a>



<a href="/windows-hardware/drivers/ddi/ntddser/ns-ntddser-_serial_timeouts">SERIAL_TIMEOUTS</a>
