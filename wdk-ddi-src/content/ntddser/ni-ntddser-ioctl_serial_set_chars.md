---
UID: NI:ntddser.IOCTL_SERIAL_SET_CHARS
title: IOCTL_SERIAL_SET_CHARS (ntddser.h)
description: The IOCTL_SERIAL_SET_CHARS request sets the special characters that the serial controller driver uses for handshake flow control. This driver verifies the specified special characters.
old-location: serports\ioctl_serial_set_chars.htm
tech.root: serports
ms.assetid: f792bd01-19e1-4f15-917a-19ad46e7a4a9
ms.date: 04/23/2018
keywords: ["IOCTL_SERIAL_SET_CHARS IOCTL"]
ms.keywords: IOCTL_SERIAL_SET_CHARS, IOCTL_SERIAL_SET_CHARS control, IOCTL_SERIAL_SET_CHARS control code [Serial Ports], ntddser/IOCTL_SERIAL_SET_CHARS, serports.ioctl_serial_set_chars, serref_57af2187-3244-4b5d-a096-684050127a24.xml
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
 - IOCTL_SERIAL_SET_CHARS
 - ntddser/IOCTL_SERIAL_SET_CHARS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntddser.h
api_name:
 - IOCTL_SERIAL_SET_CHARS
---

# IOCTL_SERIAL_SET_CHARS IOCTL


## -description

The <b>IOCTL_SERIAL_SET_CHARS</b> request sets the special characters that the serial controller driver uses for handshake flow control. This driver verifies the specified special characters.

To obtain the special characters, a client can use an <a href="/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_get_chars">IOCTL_SERIAL_GET_CHARS</a> request.

## -ioctlparameters

### -input-buffer

The <b>AssociatedIrp.SystemBuffer</b> member points to a client-allocated <a href="/windows-hardware/drivers/ddi/ntddser/ns-ntddser-_serial_chars">SERIAL_CHARS</a> structure that is used to input special characters.

### -input-buffer-length

The <b>Parameters.DeviceIoControl.InputBufferLength</b> member is set to the size, in bytes, of a <b>SERIAL_CHARS</b> structure.

### -output-buffer

None.

### -output-buffer-length

None.

### -in-out-buffer

### -inout-buffer-length

### -status-block

The <b>Information</b> member is set to zero.

The <b>Status</b> member is set to one of the <a href="/windows-hardware/drivers/serports/serial-device-control-requests2">Generic Status Values for Serial Device Control Requests</a>. A status of STATUS_INVALID_PARAMETER indicates that <b>XoffChar</b> equals <b>XonChar</b>, or that one of them equals the handshake flow control escape character.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_get_chars">IOCTL_SERIAL_GET_CHARS</a>



<a href="/windows-hardware/drivers/ddi/ntddser/ns-ntddser-_serial_chars">SERIAL_CHARS</a>