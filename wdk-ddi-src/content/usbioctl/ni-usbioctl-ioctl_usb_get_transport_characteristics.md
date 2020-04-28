---
UID: NI:usbioctl.IOCTL_USB_GET_TRANSPORT_CHARACTERISTICS
title: IOCTL_USB_GET_TRANSPORT_CHARACTERISTICS (usbioctl.h)
description: The client driver sends this request to retrieve the transport characteristics.
old-location: buses\ioctl_usb_get_transport_characteristics.htm
tech.root: usbref
ms.assetid: 36CF2034-C816-421A-8B59-A4DC4EFFEB70
ms.date: 05/07/2018
keywords: ["IOCTL_USB_GET_TRANSPORT_CHARACTERISTICS IOCTL"]
ms.keywords: IOCTL_USB_GET_TRANSPORT_CHARACTERISTICS, IOCTL_USB_GET_TRANSPORT_CHARACTERISTICS control, IOCTL_USB_GET_TRANSPORT_CHARACTERISTICS control code [Buses], buses.ioctl_usb_get_transport_characteristics, usbioctl/IOCTL_USB_GET_TRANSPORT_CHARACTERISTICS
f1_keywords:
 - "usbioctl/IOCTL_USB_GET_TRANSPORT_CHARACTERISTICS"
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
- IOCTL_USB_GET_TRANSPORT_CHARACTERISTICS
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_USB_GET_TRANSPORT_CHARACTERISTICS IOCTL


## -description


The client driver sends this request to retrieve the transport characteristics.


## -ioctlparameters




### -input-buffer








### -input-buffer-length








### -output-buffer








### -output-buffer-length








### -in-out-buffer

The <b>AssociatedIrp.SystemBuffer</b> member is a pointer to a caller-allocated <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbioctl/ns-usbioctl-_usb_transport_characteristics">USB_TRANSPORT_CHARACTERISTICS</a> structure.  On input, set <b>Version</b> to USB_TRANSPORT_CHARACTERISTICS_VERSION_1. On output <b>Version</b> is reset to a version less than or equal to USB_TRANSPORT_CHARACTERISTICS_VERSION_1;  he remaining members of the structure is filled with transport information.


### -inout-buffer-length

The size of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbioctl/ns-usbioctl-_usb_transport_characteristics">USB_TRANSPORT_CHARACTERISTICS</a> structure.


### -status-block

<b>Irp->IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> code. 


## -remarks



This request retrieves the transport characteristics to decide on an algorithm for streaming. For example, a display driver can use  the latency and bandwidth information to decide its codec selection. 



This information might not be always available. The USB driver stack depends on the underlying transport to expose these values. Therefore, the client driver must have a back up mechanism for such cases where the request. 

If the client driver is interested in knowing the latest information at all times, the driver must register for notification when transport characteristics change, keep a request pending with the USB driver stack, and unregister when the notification is no longer required. The driver can accomplish all those tasks by sending these IOCTL requests. 

<ul>
<li>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbioctl/ni-usbioctl-ioctl_usb_register_for_transport_characteristics_change">IOCTL_USB_REGISTER_FOR_TRANSPORT_CHARACTERISTICS_CHANGE</a>
</li>
<li>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbioctl/ni-usbioctl-ioctl_usb_notify_on_transport_characteristics_change">IOCTL_USB_NOTIFY_ON_TRANSPORT_CHARACTERISTICS_CHANGE</a>
</li>
<li>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbioctl/ni-usbioctl-ioctl_usb_unregister_for_transport_characteristics_change">IOCTL_USB_UNREGISTER_FOR_TRANSPORT_CHARACTERISTICS_CHANGE</a>
</li>
</ul>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/creating-ioctl-requests-in-drivers">Creating IOCTL Requests in Drivers</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/usbcon/usb-client-drivers-for-ma-usb">USB client drivers for Media-Agnostic (MA-USB)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendinternalioctlotherssynchronously">WdfIoTargetSendInternalIoctlOthersSynchronously</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendinternalioctlsynchronously">WdfIoTargetSendInternalIoctlSynchronously</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendioctlsynchronously">WdfIoTargetSendIoctlSynchronously</a>
 

 

