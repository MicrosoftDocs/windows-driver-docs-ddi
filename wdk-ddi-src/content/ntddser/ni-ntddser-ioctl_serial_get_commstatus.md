---
UID: NI:ntddser.IOCTL_SERIAL_GET_COMMSTATUS
title: IOCTL_SERIAL_GET_COMMSTATUS (ntddser.h)
description: The IOCTL_SERIAL_GET_COMMSTATUS request returns information about the communication status of a serial device. For more information about the status information that is retrieved by this request, see SERIAL_STATUS.
old-location: serports\ioctl_serial_get_commstatus.htm
tech.root: serports
ms.date: 04/23/2018
keywords: ["IOCTL_SERIAL_GET_COMMSTATUS IOCTL"]
ms.keywords: IOCTL_SERIAL_GET_COMMSTATUS, IOCTL_SERIAL_GET_COMMSTATUS control, IOCTL_SERIAL_GET_COMMSTATUS control code [Serial Ports], ntddser/IOCTL_SERIAL_GET_COMMSTATUS, serports.ioctl_serial_get_commstatus, serref_4c26c2fc-2285-4b46-8791-0fb613e1c05a.xml
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
 - IOCTL_SERIAL_GET_COMMSTATUS
 - ntddser/IOCTL_SERIAL_GET_COMMSTATUS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntddser.h
api_name:
 - IOCTL_SERIAL_GET_COMMSTATUS
---

# IOCTL_SERIAL_GET_COMMSTATUS IOCTL


## -description

The <b>IOCTL_SERIAL_GET_COMMSTATUS</b> request returns information about the communication status of a serial device. For more information about the status information that is retrieved by this request, see <a href="/windows-hardware/drivers/ddi/ntddser/ns-ntddser-_serial_status">SERIAL_STATUS</a>.

## -ioctlparameters

### -ioctl-major-code

### -input-buffer

None.

### -input-buffer-length

None.

### -output-buffer

The <b>AssociatedIrp.SystemBuffer</b> member points to a client-allocated <b>SERIAL_STATUS</b> structure that the serial controller driver uses to output communication status information.

### -output-buffer-length

The <b>Parameters.DeviceIoControl.OutputBufferLength</b> member is set to the size in bytes of a <b>SERIAL_STATUS</b> structure.

### -in-out-buffer

### -inout-buffer-length

### -status-block

If the request is successful, the <b>Information</b> member is set to the size in bytes of a <b>SERIAL_STATUS</b> structure. Otherwise, the <b>Information</b> member is set to zero.

The <b>Status</b> member is set to one of the <a href="/windows-hardware/drivers/serports/serial-device-control-requests2">Generic Status Values for Serial Device Control Requests</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddser/ns-ntddser-_serial_status">SERIAL_STATUS</a>
