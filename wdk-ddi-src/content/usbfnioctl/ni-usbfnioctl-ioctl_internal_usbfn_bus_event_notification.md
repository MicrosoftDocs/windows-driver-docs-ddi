---
UID: NI:usbfnioctl.IOCTL_INTERNAL_USBFN_BUS_EVENT_NOTIFICATION
title: IOCTL_INTERNAL_USBFN_BUS_EVENT_NOTIFICATION (usbfnioctl.h)
description: The USB class driver sends this request to prepare for notifications received from the USB function class extension (UFX) in response to an event on the bus, such as a change in the port type or a receipt of a non-standard setup packet.
old-location: buses\ioctl_internal_usbfn_bus_event_notification.htm
tech.root: usbref
ms.date: 05/07/2018
keywords: ["IOCTL_INTERNAL_USBFN_BUS_EVENT_NOTIFICATION IOCTL"]
ms.keywords: IOCTL_INTERNAL_USBFN_BUS_EVENT_NOTIFICATION, IOCTL_INTERNAL_USBFN_BUS_EVENT_NOTIFICATION control, IOCTL_INTERNAL_USBFN_BUS_EVENT_NOTIFICATION control code [Buses], buses.ioctl_internal_usbfn_bus_event_notification, usbfnioctl/IOCTL_INTERNAL_USBFN_BUS_EVENT_NOTIFICATION
req.header: usbfnioctl.h
req.include-header: 
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
 - IOCTL_INTERNAL_USBFN_BUS_EVENT_NOTIFICATION
 - usbfnioctl/IOCTL_INTERNAL_USBFN_BUS_EVENT_NOTIFICATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - usbfnioctl.h
api_name:
 - IOCTL_INTERNAL_USBFN_BUS_EVENT_NOTIFICATION
---

# IOCTL_INTERNAL_USBFN_BUS_EVENT_NOTIFICATION IOCTL


## -description

The USB class driver sends this request to prepare for notifications received from the USB function class extension (UFX) in response to an event on the bus, such as a change in the port type 
		or a receipt of a non-standard setup packet.

## -ioctlparameters

### -ioctl-major-code

[IRP_MJ_INTERNAL_DEVICE_CONTROL](/windows-hardware/drivers/kernel/irp-mj-internal-device-control)

### -input-buffer

NULL.

### -input-buffer-length

None.

### -output-buffer

A pointer to a caller-allocated <a href="/windows-hardware/drivers/ddi/usbfnbase/ns-usbfnbase-_usbfn_notification">USBFN_NOTIFICATION</a> 
			structure that UFX populates with the type of bus event and data associated with that event.

### -output-buffer-length

The size of a <a href="/windows-hardware/drivers/ddi/usbfnbase/ns-usbfnbase-_usbfn_notification">USBFN_NOTIFICATION</a> 
			structure.

### -in-out-buffer

### -inout-buffer-length

### -status-block

If the request is successful, the USB function class extension (UFX) returns STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise it returns a status value for which NT_SUCCESS(status) equals FALSE.

## -remarks

UFX completes this request in response to an event on the bus. It is recommended that class drivers send multiple requests at a time to make sure that critical notifications are not missed.

## -see-also

<a href="/windows-hardware/drivers/ddi/usbfnbase/ne-usbfnbase-_usbfn_event">USBFN_EVENT</a>



<a href="/windows-hardware/drivers/ddi/usbfnbase/ns-usbfnbase-_usbfn_notification">USBFN_NOTIFICATION</a>
