---
UID: NI:ntddser.IOCTL_SERIAL_SET_TIMEOUTS
title: IOCTL_SERIAL_SET_TIMEOUTS (ntddser.h)
description: The IOCTL_SERIAL_SET_TIMEOUTS request sets the time-out values that the serial controller driver uses for read and write requests.
old-location: serports\ioctl_serial_set_timeouts.htm
tech.root: serports
ms.assetid: c73627e1-12fc-465d-9ed9-d241a1c0db8e
ms.date: 04/23/2018
ms.keywords: IOCTL_SERIAL_SET_TIMEOUTS, IOCTL_SERIAL_SET_TIMEOUTS control, IOCTL_SERIAL_SET_TIMEOUTS control code [Serial Ports], ntddser/IOCTL_SERIAL_SET_TIMEOUTS, serports.ioctl_serial_set_timeouts, serref_5aac4101-9b7e-4bff-a61c-108ef9cb76f3.xml
f1_keywords:
 - "ntddser/IOCTL_SERIAL_SET_TIMEOUTS"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Ntddser.h
api_name:
- IOCTL_SERIAL_SET_TIMEOUTS
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_SERIAL_SET_TIMEOUTS IOCTL


## -description


The <b>IOCTL_SERIAL_SET_TIMEOUTS</b> request sets the time-out values that the serial controller driver uses for read and write requests.

To get the time-out values, a client can use an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_get_timeouts">IOCTL_SERIAL_GET_TIMEOUTS</a> request.

For more information about time-outs, see <a href="https://docs.microsoft.com/previous-versions/ff547486(v=vs.85)">Setting Read and Write Time-Outs for a Serial Device</a>.


## -ioctlparameters




### -input-buffer

The <b>AssociatedIrp.SystemBuffer</b> member points to a client-allocated <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ns-ntddser-_serial_timeouts">SERIAL_TIMEOUTS</a> structure that is used to input read and write time-out values.


### -input-buffer-length

The <b>Parameters.DeviceIoControl.InputBufferLength</b> member is set to the size, in bytes, of a <b>SERIAL_TIMEOUTS</b> structure.


### -output-buffer

None.


### -output-buffer-length

None.


### -in-out-buffer








### -inout-buffer-length








### -status-block

The <b>Information</b> member is set to zero.

The <b>Status</b> member is set to one of the <a href="https://docs.microsoft.com/windows-hardware/drivers/serports/serial-device-control-requests2">Generic Status Values for Serial Device Control Requests</a>. A status of STATUS_INVALID_PARAMETER indicates that the read time-out values exceed the maximum permitted values.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_get_timeouts">IOCTL_SERIAL_GET_TIMEOUTS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ns-ntddser-_serial_timeouts">SERIAL_TIMEOUTS</a>
 

 

