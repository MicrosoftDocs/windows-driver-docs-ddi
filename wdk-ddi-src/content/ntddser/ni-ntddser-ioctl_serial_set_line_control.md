---
UID: NI:ntddser.IOCTL_SERIAL_SET_LINE_CONTROL
title: IOCTL_SERIAL_SET_LINE_CONTROL (ntddser.h)
description: The IOCTL_SERIAL_SET_LINE_CONTROL request sets the line control register (LCR). The line control register controls the data size, the number of stop bits, and the parity.
old-location: serports\ioctl_serial_set_line_control.htm
tech.root: serports
ms.assetid: 0883b10c-1900-42b1-afc9-1e61effed111
ms.date: 04/23/2018
keywords: ["IOCTL_SERIAL_SET_LINE_CONTROL IOCTL"]
ms.keywords: IOCTL_SERIAL_SET_LINE_CONTROL, IOCTL_SERIAL_SET_LINE_CONTROL control, IOCTL_SERIAL_SET_LINE_CONTROL control code [Serial Ports], ntddser/IOCTL_SERIAL_SET_LINE_CONTROL, serports.ioctl_serial_set_line_control, serref_70796be3-dbb8-4918-899d-d3750813aad3.xml
f1_keywords:
 - "ntddser/IOCTL_SERIAL_SET_LINE_CONTROL"
 - "IOCTL_SERIAL_SET_LINE_CONTROL"
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
- IOCTL_SERIAL_SET_LINE_CONTROL
targetos: Windows
req.typenames: 
---

# IOCTL_SERIAL_SET_LINE_CONTROL IOCTL


## -description


The <b>IOCTL_SERIAL_SET_LINE_CONTROL</b> request sets the line control register (LCR). The line control register controls the data size, the number of stop bits, and the parity.

To obtain the value of the line control register, a client can use an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_get_line_control">IOCTL_SERIAL_GET_LINE_CONTROL</a> request.


## -ioctlparameters




### -input-buffer

The <b>AssociatedIrp.SystemBuffer</b> points to a client-allocated <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ns-ntddser-_serial_line_control">SERIAL_LINE_CONTROL</a> structure that is used to input line control information.


### -input-buffer-length

The <b>Parameters.DeviceIoControl.InputBufferLength</b> is set to the size, in bytes, of a <b>SERIAL_LINE_CONTROL</b> structure.


### -output-buffer

None.


### -output-buffer-length

None.


### -in-out-buffer








### -inout-buffer-length








### -status-block

The <b>Information</b> member is set to zero.

The <b>Status</b> member is set to one of the <a href="https://docs.microsoft.com/windows-hardware/drivers/serports/serial-device-control-requests2">Generic Status Values for Serial Device Control Requests</a>. A status of STATUS_INVALID_PARAMETER indicates that the specified line control information is not valid.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_get_line_control">IOCTL_SERIAL_GET_LINE_CONTROL</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ns-ntddser-_serial_line_control">SERIAL_LINE_CONTROL</a>
 

 

