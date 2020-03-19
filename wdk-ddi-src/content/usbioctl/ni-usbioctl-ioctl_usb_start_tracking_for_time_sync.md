---
UID: NI:usbioctl.IOCTL_USB_START_TRACKING_FOR_TIME_SYNC
title: IOCTL_USB_START_TRACKING_FOR_TIME_SYNC (usbioctl.h)
description: This request registers the caller with USB driver stack for time sync services.
old-location: buses\ioctl_usb_start_tracking_for_time_sync.htm
tech.root: usbref
ms.assetid: C9EA7A04-3B53-46D4-BC1B-A2766577095F
ms.date: 05/07/2018
keywords: ["IOCTL_USB_START_TRACKING_FOR_TIME_SYNC IOCTL"]
ms.keywords: IOCTL_USB_START_TRACKING_FOR_TIME_SYNC, IOCTL_USB_START_TRACKING_FOR_TIME_SYNC control, IOCTL_USB_START_TRACKING_FOR_TIME_SYNC control code [Buses], buses.ioctl_usb_start_tracking_for_time_sync, usbioctl/IOCTL_USB_START_TRACKING_FOR_TIME_SYNC
f1_keywords:
 - "usbioctl/IOCTL_USB_START_TRACKING_FOR_TIME_SYNC"
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
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Usbioctl.h
api_name:
- IOCTL_USB_START_TRACKING_FOR_TIME_SYNC
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_USB_START_TRACKING_FOR_TIME_SYNC IOCTL


## -description


This request registers the caller with USB driver stack for time sync services. 


## -ioctlparameters




### -input-buffer








### -input-buffer-length








### -output-buffer








### -output-buffer-length








### -in-out-buffer

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbioctl/ns-usbioctl-_usb_start_tracking_for_time_sync_information">USB_START_TRACKING_FOR_TIME_SYNC_INFORMATION</a> structure. On input, the caller must set the <b>TimeTrackingHandle</b> member to NULL. On output, the USB driver stack sets the  <b>TimeTrackingHandle</b> member to a handle that tracks the sync services operation.


### -inout-buffer-length

The size of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbioctl/ns-usbioctl-_usb_start_tracking_for_time_sync_information">USB_START_TRACKING_FOR_TIME_SYNC_INFORMATION</a> structure.


### -status-block

<b>Irp->IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> indicates an the appropriate error condition as a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> code. 


## -remarks



When this IOCTL request completes, the USB driver stack enables certain interrupts from the host controller to keep track of closest frame/microframe boundary in order  to predict the system QPC value with accuracy. Enabling the hardware interrupts adds an overhead to the power consumption because the CPU wakes up every 2.048 seconds when working in the D0 power state. Therefore we recommend that the caller should register for time sync services only when needed.

The driver stack disables those interrupts when it receives and completes the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbioctl/ni-usbioctl-ioctl_usb_stop_tracking_for_time_sync">IOCTL_USB_STOP_TRACKING_FOR_TIME_SYNC</a> request.  




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/creating-ioctl-requests-in-drivers">Creating IOCTL Requests in Drivers</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendinternalioctlotherssynchronously">WdfIoTargetSendInternalIoctlOthersSynchronously</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendinternalioctlsynchronously">WdfIoTargetSendInternalIoctlSynchronously</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendioctlsynchronously">WdfIoTargetSendIoctlSynchronously</a>
 

 

