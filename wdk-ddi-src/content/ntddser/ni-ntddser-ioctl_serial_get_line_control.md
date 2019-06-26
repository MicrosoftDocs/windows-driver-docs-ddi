---
UID: NI:ntddser.IOCTL_SERIAL_GET_LINE_CONTROL
title: IOCTL_SERIAL_GET_LINE_CONTROL (ntddser.h)
description: The IOCTL_SERIAL_GET_LINE_CONTROL request returns information about the line control set for a serial device. The line control parameters include the number of stop bits, the number of data bits, and the parity.
old-location: serports\ioctl_serial_get_line_control.htm
tech.root: serports
ms.assetid: 72585a00-ee43-44fa-a6f4-baa9fe5a2e3f
ms.date: 04/23/2018
ms.keywords: IOCTL_SERIAL_GET_LINE_CONTROL, IOCTL_SERIAL_GET_LINE_CONTROL control, IOCTL_SERIAL_GET_LINE_CONTROL control code [Serial Ports], ntddser/IOCTL_SERIAL_GET_LINE_CONTROL, serports.ioctl_serial_get_line_control, serref_46b42112-a960-44dc-8ce7-3c8d68746fe9.xml
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Ntddser.h
api_name:
- IOCTL_SERIAL_GET_LINE_CONTROL
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_SERIAL_GET_LINE_CONTROL IOCTL


## -description


The <b>IOCTL_SERIAL_GET_LINE_CONTROL</b> request returns information about the line control set for a serial device. The line control parameters include the number of stop bits, the number of data bits, and the parity.

To configure the line control, a client can use an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddser/ni-ntddser-ioctl_serial_set_line_control">IOCTL_SERIAL_SET_LINE_CONTROL</a> request.

For information about valid line control register settings, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddser/ns-ntddser-_serial_line_control">SERIAL_LINE_CONTROL</a>.


## -ioctlparameters




### -input-buffer

None.


### -input-buffer-length

None.


### -output-buffer

The <b>AssociatedIrp.SystemBuffer</b> member points to a client-allocated <b>SERIAL_LINE_CONTROL</b> structure that the serial controller driver uses to output information about the line control configuration.


### -output-buffer-length

The <b>Parameters.DeviceIoControl.OutputBufferLength</b> member is set to the size, in bytes, of a <b>SERIAL_LINE_CONTROL</b> structure.


### -in-out-buffer








### -inout-buffer-length








### -status-block

If the request is successful, the <b>Information</b> member is set to the size, in bytes, of a <b>SERIAL_LINE_CONTROL</b> structure. Otherwise, the <b>Information</b> member is set to zero.

The <b>Status</b> member is set to one of the <a href="https://docs.microsoft.com/windows-hardware/drivers/serports/serial-device-control-requests2">Generic Status Values for Serial Device Control Requests</a>.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddser/ni-ntddser-ioctl_serial_set_line_control">IOCTL_SERIAL_SET_LINE_CONTROL</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddser/ns-ntddser-_serial_line_control">SERIAL_LINE_CONTROL</a>
 

 

