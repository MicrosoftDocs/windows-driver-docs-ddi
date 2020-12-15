---
UID: NI:usbioctl.IOCTL_USB_REGISTER_FOR_TRANSPORT_CHARACTERISTICS_CHANGE
title: IOCTL_USB_REGISTER_FOR_TRANSPORT_CHARACTERISTICS_CHANGE (usbioctl.h)
description: This request registers for notifications about the changes in transport characteristics.
old-location: buses\ioctl_usb_register_for_transport_characteristics_change.htm
tech.root: usbref
ms.date: 05/07/2018
keywords: ["IOCTL_USB_REGISTER_FOR_TRANSPORT_CHARACTERISTICS_CHANGE IOCTL"]
ms.keywords: IOCTL_USB_REGISTER_FOR_TRANSPORT_CHARACTERISTICS_CHANGE, IOCTL_USB_REGISTER_FOR_TRANSPORT_CHARACTERISTICS_CHANGE control, IOCTL_USB_REGISTER_FOR_TRANSPORT_CHARACTERISTICS_CHANGE control code [Buses], buses.ioctl_usb_register_for_transport_characteristics_change, usbioctl/IOCTL_USB_REGISTER_FOR_TRANSPORT_CHARACTERISTICS_CHANGE
req.header: usbioctl.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: Windows Server 2016
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
req.irql: <=DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - IOCTL_USB_REGISTER_FOR_TRANSPORT_CHARACTERISTICS_CHANGE
 - usbioctl/IOCTL_USB_REGISTER_FOR_TRANSPORT_CHARACTERISTICS_CHANGE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Usbioctl.h
api_name:
 - IOCTL_USB_REGISTER_FOR_TRANSPORT_CHARACTERISTICS_CHANGE
---

# IOCTL_USB_REGISTER_FOR_TRANSPORT_CHARACTERISTICS_CHANGE IOCTL


## -description

This request registers for notifications about the changes in transport characteristics.

## -ioctlparameters

### -input-buffer

### -input-buffer-length

### -output-buffer

### -output-buffer-length

### -in-out-buffer

The <b>AssociatedIrp.SystemBuffer</b> member is a pointer to a <a href="/windows-hardware/drivers/ddi/usbioctl/ns-usbioctl-_usb_transport_characteristics_change_registration">USB_TRANSPORT_CHARACTERISTICS_CHANGE_REGISTRATION</a> structure. On input, the client driver can specify the type of notification changes in which the driver is interested by setting the flags in the <b>ChangeNotificationInputFlags</b> member.

On output, the structure is filled with the registration handle and initial values of the transport characteristics.

### -inout-buffer-length

The size of the <a href="/windows-hardware/drivers/ddi/usbioctl/ns-usbioctl-_usb_transport_characteristics_change_registration">USB_TRANSPORT_CHARACTERISTICS_CHANGE_REGISTRATION</a> structure.

### -status-block

<b>Irp->IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> indicates  the appropriate error condition as a <a href="/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> code.

## -remarks

 The transport characteristics of MA-USB mediums can vary significantly over time. If the client diver is interested in knowing the latest information at all times, the driver must register for notification by sending  the request. 

This request can be sent by a user mode application, UMDF driver, or a KMDF driver. USB driver stack checks for stale and bad registration handle. If the request is received on a handle before registration and after unregistration, the driver stack fails the request.

## -see-also

<a href="/windows-hardware/drivers/kernel/creating-ioctl-requests-in-drivers">Creating IOCTL Requests in Drivers</a>



<a href="/windows-hardware/drivers/usbcon/usb-client-drivers-for-ma-usb">USB client drivers for Media-Agnostic (MA-USB)</a>



<a href="/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendinternalioctlotherssynchronously">WdfIoTargetSendInternalIoctlOthersSynchronously</a>



<a href="/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendinternalioctlsynchronously">WdfIoTargetSendInternalIoctlSynchronously</a>



<a href="/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendioctlsynchronously">WdfIoTargetSendIoctlSynchronously</a>
