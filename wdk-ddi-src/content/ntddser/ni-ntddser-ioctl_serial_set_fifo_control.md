---
UID: NI:ntddser.IOCTL_SERIAL_SET_FIFO_CONTROL
title: IOCTL_SERIAL_SET_FIFO_CONTROL (ntddser.h)
description: The IOCTL_SERIAL_SET_FIFO_CONTROL request sets the FIFO control register (FCR). Serial does not verify the specified FIFO control information.
old-location: serports\ioctl_serial_set_fifo_control.htm
tech.root: serports
ms.assetid: b41a13a6-4573-495f-8dfd-9405917d8e66
ms.date: 04/23/2018
keywords: ["IOCTL_SERIAL_SET_FIFO_CONTROL IOCTL"]
ms.keywords: IOCTL_SERIAL_SET_FIFO_CONTROL, IOCTL_SERIAL_SET_FIFO_CONTROL control, IOCTL_SERIAL_SET_FIFO_CONTROL control code [Serial Ports], ntddser/IOCTL_SERIAL_SET_FIFO_CONTROL, serports.ioctl_serial_set_fifo_control, serref_5e21a668-7fca-4d1e-baf2-3356ba2087d9.xml
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
 - IOCTL_SERIAL_SET_FIFO_CONTROL
 - ntddser/IOCTL_SERIAL_SET_FIFO_CONTROL
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntddser.h
api_name:
 - IOCTL_SERIAL_SET_FIFO_CONTROL
---

# IOCTL_SERIAL_SET_FIFO_CONTROL IOCTL


## -description

The <b>IOCTL_SERIAL_SET_FIFO_CONTROL</b> request sets the FIFO control register (FCR). Serial does not verify the specified FIFO control information.

## -ioctlparameters

### -input-buffer

The <b>AssociatedIrp.SystemBuffer</b> member points to a client-allocated ULONG that is used to input FIFO control information.

### -input-buffer-length

The <b>Parameters.DeviceIoControl.InputBufferLength</b> is set to the size, in bytes, of a ULONG.

### -output-buffer

None.

### -output-buffer-length

None.

### -in-out-buffer

### -inout-buffer-length

### -status-block

The <b>Information</b> member is set to zero.

The <b>Status</b> member is set to one of the <a href="/windows-hardware/drivers/serports/serial-device-control-requests2">Generic Status Values for Serial Device Control Requests</a>.