---
UID: NI:usbioctl.IOCTL_USB_START_TRACKING_FOR_TIME_SYNC
title: IOCTL_USB_START_TRACKING_FOR_TIME_SYNC
author: windows-driver-content
description: This request registers the caller with USB driver stack for time sync services.
old-location: buses\ioctl_usb_start_tracking_for_time_sync.htm
old-project: UsbRef
ms.assetid: C9EA7A04-3B53-46D4-BC1B-A2766577095F
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: buses.ioctl_usb_start_tracking_for_time_sync, IOCTL_USB_START_TRACKING_FOR_TIME_SYNC control code [Buses], IOCTL_USB_START_TRACKING_FOR_TIME_SYNC, usbioctl/IOCTL_USB_START_TRACKING_FOR_TIME_SYNC
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
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Usbioctl.h
apiname:
-	IOCTL_USB_START_TRACKING_FOR_TIME_SYNC
product: Windows
targetos: Windows
req.typenames: USB_HUB_TYPE
req.product: Windows 10 or later.
---

# IOCTL_USB_START_TRACKING_FOR_TIME_SYNC IOCTL


##  Major Code: 


<a href="https://msdn.microsoft.com/library/windows/hardware/ff548649">IRP_MJ_DEVICE_CONTROL</a>

## -description


This request registers the caller with USB driver stack for time sync services. 


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

A pointer to a <a href="..\usbioctl\ns-usbioctl-_usb_start_tracking_for_time_sync_information.md">USB_START_TRACKING_FOR_TIME_SYNC_INFORMATION</a> structure. On input, the caller must set the <b>TimeTrackingHandle</b> member to NULL. On output, the USB driver stack sets the  <b>TimeTrackingHandle</b> member to a handle that tracks the sync services operation.


### -inout-buffer-length

The size of the <a href="..\usbioctl\ns-usbioctl-_usb_start_tracking_for_time_sync_information.md">USB_START_TRACKING_FOR_TIME_SYNC_INFORMATION</a> structure.


### -status-block

<b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> indicates an the appropriate error condition as a <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code. 


## -remarks



When this IOCTL request completes, the USB driver stack enables certain interrupts from the host controller to keep track of closest frame/microframe boundary in order  to predict the system QPC value with accuracy. Enabling the hardware interrupts adds an overhead to the power consumption because the CPU wakes up every 2.048 seconds when working in the D0 power state. Therefore we recommend that the caller should register for time sync services only when needed.

The driver stack disables those interrupts when it receives and completes the <a href="..\usbioctl\ni-usbioctl-ioctl_usb_stop_tracking_for_time_sync.md">IOCTL_USB_STOP_TRACKING_FOR_TIME_SYNC</a> request.  




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff542894">Creating IOCTL Requests in Drivers</a>



<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendioctlsynchronously.md">WdfIoTargetSendIoctlSynchronously</a>



<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendinternalioctlsynchronously.md">WdfIoTargetSendInternalIoctlSynchronously</a>



<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendioctlsynchronously.md">WdfIoTargetSendIoctlSynchronously</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [UsbRef\buses]:%20IOCTL_USB_START_TRACKING_FOR_TIME_SYNC control code%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

