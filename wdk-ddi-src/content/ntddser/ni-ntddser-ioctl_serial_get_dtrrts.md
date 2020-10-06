---
UID: NI:ntddser.IOCTL_SERIAL_GET_DTRRTS
title: IOCTL_SERIAL_GET_DTRRTS (ntddser.h)
description: The IOCTL_SERIAL_GET_DTRRTS request returns information about the data terminal ready (DTR) control signal and the request to send (RTS) control signal.
old-location: serports\ioctl_serial_get_dtrrts.htm
tech.root: serports
ms.assetid: 9ced72c6-24f8-49c6-a68e-2b0c5c81a8c2
ms.date: 04/23/2018
keywords: ["IOCTL_SERIAL_GET_DTRRTS IOCTL"]
ms.keywords: IOCTL_SERIAL_GET_DTRRTS, IOCTL_SERIAL_GET_DTRRTS control, IOCTL_SERIAL_GET_DTRRTS control code [Serial Ports], ntddser/IOCTL_SERIAL_GET_DTRRTS, serports.ioctl_serial_get_dtrrts, serref_7c57fa0a-a5a3-41cd-bea3-b4685b39daad.xml
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
 - IOCTL_SERIAL_GET_DTRRTS
 - ntddser/IOCTL_SERIAL_GET_DTRRTS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntddser.h
api_name:
 - IOCTL_SERIAL_GET_DTRRTS
---

# IOCTL_SERIAL_GET_DTRRTS IOCTL


## -description

The <b>IOCTL_SERIAL_GET_DTRRTS</b> request returns information about the <i>data terminal ready</i> (DTR) control signal and the <i>request to send</i> (RTS) control signal.

## -ioctlparameters

### -input-buffer

None.

### -input-buffer-length

None.

### -output-buffer

The <b>AssociatedIrp.SystemBuffer</b> member points to a client-allocated ULONG buffer that Serial.sys uses to output information about the DTR and RTS. The ULONG buffer is set to zero or to the bitwise-OR of one or more of the following flag bits:

### -output-buffer-length

The <b>Parameters.DeviceIoControl.OutputBufferLength</b> member is set to the size in bytes of a ULONG.

### -in-out-buffer

### -inout-buffer-length

### -status-block

If the request is successful, the <b>Information</b> member is set to the size in bytes of a ULONG. Otherwise, the <b>Information</b> member is set to zero.

The <b>Status</b> member is set to one of the <a href="/windows-hardware/drivers/serports/serial-device-control-requests2">Generic Status Values for Serial Device Control Requests</a>.

## -SERIAL_DTR_STATE

Indicates that DTR is set.

## -SERIAL_RTS_STATE

Indicates that RTS is set.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_set_dtr">IOCTL_SERIAL_SET_DTR</a>



<a href="/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_set_rts">IOCTL_SERIAL_SET_RTS</a>