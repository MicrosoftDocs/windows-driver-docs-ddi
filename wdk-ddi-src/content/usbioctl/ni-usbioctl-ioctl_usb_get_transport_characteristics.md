---
UID: NI:usbioctl.IOCTL_USB_GET_TRANSPORT_CHARACTERISTICS
title: IOCTL_USB_GET_TRANSPORT_CHARACTERISTICS
author: windows-driver-content
description: The client driver sends this request to retrieve the transport characteristics.
old-location: buses\ioctl_usb_get_transport_characteristics.htm
old-project: usbref
ms.assetid: 36CF2034-C816-421A-8B59-A4DC4EFFEB70
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: buses.ioctl_usb_get_transport_characteristics, IOCTL_USB_GET_TRANSPORT_CHARACTERISTICS control code [Buses], IOCTL_USB_GET_TRANSPORT_CHARACTERISTICS, usbioctl/IOCTL_USB_GET_TRANSPORT_CHARACTERISTICS
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Usbioctl.h
apiname:
-	IOCTL_USB_GET_TRANSPORT_CHARACTERISTICS
product: Windows
targetos: Windows
req.typenames: USB_HUB_TYPE
req.product: Windows 10 or later.
---

# IOCTL_USB_GET_TRANSPORT_CHARACTERISTICS IOCTL


##  Major Code: 


<a href="https://msdn.microsoft.com/library/windows/hardware/ff548649">IRP_MJ_DEVICE_CONTROL</a>

## -description


The client driver sends this request to retrieve the transport characteristics.


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

The <b>AssociatedIrp.SystemBuffer</b> member is a pointer to a caller-allocated <a href="..\usbioctl\ns-usbioctl-_usb_transport_characteristics.md">USB_TRANSPORT_CHARACTERISTICS</a> structure.  On input, set <b>Version</b> to USB_TRANSPORT_CHARACTERISTICS_VERSION_1. On output <b>Version</b> is reset to a version less than or equal to USB_TRANSPORT_CHARACTERISTICS_VERSION_1;  he remaining members of the structure is filled with transport information.


### -inout-buffer-length

The size of the <a href="..\usbioctl\ns-usbioctl-_usb_transport_characteristics.md">USB_TRANSPORT_CHARACTERISTICS</a> structure.


### -status-block

<b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code. 


## -remarks


This request retrieves the transport characteristics to decide on an algorithm for streaming. For example, a display driver can use  the latency and bandwidth information to decide its codec selection. 



This information might not be always available. The USB driver stack depends on the underlying transport to expose these values. Therefore, the client driver must have a back up mechanism for such cases where the request. 

If the client diver is interested in knowing the latest information at all times, the driver must register for notification when transport characteristics change, keep a request pending with the USB driver stack, and unregister when the notification is no longer required. The driver can accomplish all those tasks by sending these IOCTL requests. 
<ul>
<li>
<a href="..\usbioctl\ni-usbioctl-ioctl_usb_register_for_transport_characteristics_change.md">IOCTL_USB_REGISTER_FOR_TRANSPORT_CHARACTERISTICS_CHANGE</a>
</li>
<li>
<a href="..\usbioctl\ni-usbioctl-ioctl_usb_notify_on_transport_characteristics_change.md">IOCTL_USB_NOTIFY_ON_TRANSPORT_CHARACTERISTICS_CHANGE</a>
</li>
<li>
<a href="..\usbioctl\ni-usbioctl-ioctl_usb_unregister_for_transport_characteristics_change.md">IOCTL_USB_UNREGISTER_FOR_TRANSPORT_CHARACTERISTICS_CHANGE</a>
</li>
</ul>


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff542894">Creating IOCTL Requests in Drivers</a>

<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/usbcon/usb-client-drivers-for-ma-usb">USB client drivers for Media-Agnostic (MA-USB)</a>

<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendinternalioctlotherssynchronously.md">WdfIoTargetSendInternalIoctlOthersSynchronously</a>

<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendioctlsynchronously.md">WdfIoTargetSendIoctlSynchronously</a>

<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendinternalioctlsynchronously.md">WdfIoTargetSendInternalIoctlSynchronously</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20IOCTL_USB_GET_TRANSPORT_CHARACTERISTICS control code%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

