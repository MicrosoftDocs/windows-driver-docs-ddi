---
UID: NI:usbioctl.IOCTL_USB_REGISTER_FOR_TRANSPORT_CHARACTERISTICS_CHANGE
title: IOCTL_USB_REGISTER_FOR_TRANSPORT_CHARACTERISTICS_CHANGE
author: windows-driver-content
description: This request registers for notifications about the changes in transport characteristics.
old-location: buses\ioctl_usb_register_for_transport_characteristics_change.htm
old-project: usbref
ms.assetid: 4192501F-5A30-463C-924D-CD4F2C8C3764
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: IOCTL_USB_REGISTER_FOR_TRANSPORT_CHARACTERISTICS_CHANGE, IOCTL_USB_REGISTER_FOR_TRANSPORT_CHARACTERISTICS_CHANGE control code [Buses], buses.ioctl_usb_register_for_transport_characteristics_change, usbioctl/IOCTL_USB_REGISTER_FOR_TRANSPORT_CHARACTERISTICS_CHANGE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
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
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Usbioctl.h
api_name:
-	IOCTL_USB_REGISTER_FOR_TRANSPORT_CHARACTERISTICS_CHANGE
product: Windows
targetos: Windows
req.typenames: USB_HUB_TYPE
req.product: Windows 10 or later.
---

# IOCTL_USB_REGISTER_FOR_TRANSPORT_CHARACTERISTICS_CHANGE IOCTL


##  Major Code: 


<a href="https://msdn.microsoft.com/library/windows/hardware/ff548649">IRP_MJ_DEVICE_CONTROL</a>

## -description


This request registers for notifications about the changes in transport characteristics. 


## -ioctlparameters




### -input-buffer



<text></text>




### -input-buffer-length



<text></text>




### -output-buffer



<text></text>




### -output-buffer-length



<text></text>




### -in-out-buffer

The <b>AssociatedIrp.SystemBuffer</b> member is a pointer to a <a href="..\usbioctl\ns-usbioctl-_usb_transport_characteristics_change_registration.md">USB_TRANSPORT_CHARACTERISTICS_CHANGE_REGISTRATION</a> structure. On input, the client driver can specify the type of notification changes in which the driver is interested by setting the flags in the <b>ChangeNotificationInputFlags</b> member.

On output, the structure is filled with the registration handle and initial values of the transport characteristics.


### -inout-buffer-length

The size of the <a href="..\usbioctl\ns-usbioctl-_usb_transport_characteristics_change_registration.md">USB_TRANSPORT_CHARACTERISTICS_CHANGE_REGISTRATION</a> structure.


### -status-block

<b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> indicates  the appropriate error condition as a <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code. 


## -remarks



 The transport characteristics of MA-USB mediums can vary significantly over time. If the client diver is interested in knowing the latest information at all times, the driver must register for notification by sending  the request. 

This request can be sent by a user mode application, UMDF driver, or a KMDF driver. USB driver stack checks for stale and bad registration handle. If the request is received on a handle before registration and after unregistration, the driver stack fails the request. 




## -see-also

<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendinternalioctlsynchronously.md">WdfIoTargetSendInternalIoctlSynchronously</a>



<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendioctlsynchronously.md">WdfIoTargetSendIoctlSynchronously</a>



<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendinternalioctlotherssynchronously.md">WdfIoTargetSendInternalIoctlOthersSynchronously</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542894">Creating IOCTL Requests in Drivers</a>



<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/usbcon/usb-client-drivers-for-ma-usb">USB client drivers for Media-Agnostic (MA-USB)</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20IOCTL_USB_REGISTER_FOR_TRANSPORT_CHARACTERISTICS_CHANGE control code%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

