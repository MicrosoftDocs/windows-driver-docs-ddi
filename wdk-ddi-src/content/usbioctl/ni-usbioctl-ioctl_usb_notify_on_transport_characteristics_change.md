---
UID: NI:usbioctl.IOCTL_USB_NOTIFY_ON_TRANSPORT_CHARACTERISTICS_CHANGE
title: IOCTL_USB_NOTIFY_ON_TRANSPORT_CHARACTERISTICS_CHANGE (usbioctl.h)
description: This request notifies the caller of change in transport characteristics.
old-location: buses\ioctl_usb_notify_on_transport_characteristics_change.htm
tech.root: usbref
ms.assetid: 1B71794C-EBAD-4F6C-A71C-C0D419D486BE
ms.date: 05/07/2018
keywords: ["IOCTL_USB_NOTIFY_ON_TRANSPORT_CHARACTERISTICS_CHANGE IOCTL"]
ms.keywords: IOCTL_USB_NOTIFY_ON_TRANSPORT_CHARACTERISTICS_CHANGE, IOCTL_USB_NOTIFY_ON_TRANSPORT_CHARACTERISTICS_CHANGE control, IOCTL_USB_NOTIFY_ON_TRANSPORT_CHARACTERISTICS_CHANGE control code [Buses], buses.ioctl_usb_notify_on_transport_characteristics_change, usbioctl/IOCTL_USB_NOTIFY_ON_TRANSPORT_CHARACTERISTICS_CHANGE
f1_keywords:
 - "usbioctl/IOCTL_USB_NOTIFY_ON_TRANSPORT_CHARACTERISTICS_CHANGE"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Usbioctl.h
api_name:
- IOCTL_USB_NOTIFY_ON_TRANSPORT_CHARACTERISTICS_CHANGE
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_USB_NOTIFY_ON_TRANSPORT_CHARACTERISTICS_CHANGE IOCTL


## -description


This request notifies the caller of change in transport characteristics.  


## -ioctlparameters




### -input-buffer








### -input-buffer-length








### -output-buffer








### -output-buffer-length








### -in-out-buffer

The <b>AssociatedIrp.SystemBuffer</b> member is a pointer to a caller-allocated <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbioctl/ns-usbioctl-_usb_transport_characteristics_change_notification">USB_TRANSPORT_CHARACTERISTICS_CHANGE_NOTIFICATION</a> structure. On input the caller passes the registration handle retrieved in the previous <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbioctl/ni-usbioctl-ioctl_usb_register_for_transport_characteristics_change">IOCTL_USB_REGISTER_FOR_TRANSPORT_CHARACTERISTICS_CHANGE</a> request. On output, the structure is filled  with the latest information about  the type of information for which  the caller.


### -inout-buffer-length

The size of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbioctl/ns-usbioctl-_usb_transport_characteristics_change_notification">USB_TRANSPORT_CHARACTERISTICS_CHANGE_NOTIFICATION</a> structure.


### -status-block

<b>Irp->IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> indicates the appropriate error condition as a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> code. 


## -remarks



This request is kept pending by the USB driver stack until a there is a change in the transport characteristics for which the caller registered. On completion of this request, the USB driver stack returns the information in the output buffer. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/creating-ioctl-requests-in-drivers">Creating IOCTL Requests in Drivers</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/usbcon/usb-client-drivers-for-ma-usb">USB client drivers for Media-Agnostic (MA-USB)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendinternalioctlotherssynchronously">WdfIoTargetSendInternalIoctlOthersSynchronously</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendinternalioctlsynchronously">WdfIoTargetSendInternalIoctlSynchronously</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendioctlsynchronously">WdfIoTargetSendIoctlSynchronously</a>
 

 

