---
UID: NI:ntddser.IOCTL_SERIAL_GET_PROPERTIES
title: IOCTL_SERIAL_GET_PROPERTIES (ntddser.h)
description: The IOCTL_SERIAL_GET_PROPERTIES request returns information about the capabilities of a serial controller. The capabilities information is returned in a SERIAL_COMMPROP structure.
old-location: serports\ioctl_serial_get_properties.htm
tech.root: serports
ms.date: 04/23/2018
keywords: ["IOCTL_SERIAL_GET_PROPERTIES IOCTL"]
ms.keywords: IOCTL_SERIAL_GET_PROPERTIES, IOCTL_SERIAL_GET_PROPERTIES control, IOCTL_SERIAL_GET_PROPERTIES control code [Serial Ports], ntddser/IOCTL_SERIAL_GET_PROPERTIES, serports.ioctl_serial_get_properties, serref_aff2123d-9c26-4958-84e7-9921fe45398e.xml
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
 - IOCTL_SERIAL_GET_PROPERTIES
 - ntddser/IOCTL_SERIAL_GET_PROPERTIES
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntddser.h
api_name:
 - IOCTL_SERIAL_GET_PROPERTIES
---

# IOCTL_SERIAL_GET_PROPERTIES IOCTL


## -description

The <b>IOCTL_SERIAL_GET_PROPERTIES</b> request returns information about the capabilities of a serial controller. The capabilities information is returned in a <a href="/windows-hardware/drivers/ddi/ntddser/ns-ntddser-_serial_commprop">SERIAL_COMMPROP</a> structure.

## -ioctlparameters

### -ioctl-major-code

### -input-buffer

None.

### -input-buffer-length

None.

### -output-buffer

The <b>AssociatedIrp.SystemBuffer</b> points to a client-allocated <b>SERIAL_COMMPROP</b> structure that the serial controller driver uses to output information about the capabilities of the serial controller.

### -output-buffer-length

The <b>Parameters.DeviceIoControl.OutputBufferLength</b> is set to the size, in bytes, of a <b>SERIAL_COMMPROP</b> structure.

### -in-out-buffer

### -inout-buffer-length

### -status-block

If the request is successful, the <b>Information</b> member is set to the size, in bytes, of a <b>SERIAL_COMMPROP</b> structure. Otherwise, the <b>Information</b> member is set to zero.

The <b>Status</b> member is set to one of the <a href="/windows-hardware/drivers/serports/serial-device-control-requests2">Generic Status Values for Serial Device Control Requests</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddser/ns-ntddser-_serial_commprop">SERIAL_COMMPROP</a>
