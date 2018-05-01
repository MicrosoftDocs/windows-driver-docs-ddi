---
UID: NI:usbioctl.IOCTL_USB_START_TRACKING_FOR_TIME_SYNC
title: IOCTL_USB_START_TRACKING_FOR_TIME_SYNC
author: windows-driver-content
description: This request registers the caller with USB driver stack for time sync services.
old-location: buses\ioctl_usb_start_tracking_for_time_sync.htm
old-project: usbref
ms.assetid: C9EA7A04-3B53-46D4-BC1B-A2766577095F
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: IOCTL_USB_START_TRACKING_FOR_TIME_SYNC, IOCTL_USB_START_TRACKING_FOR_TIME_SYNC control, IOCTL_USB_START_TRACKING_FOR_TIME_SYNC control code [Buses], buses.ioctl_usb_start_tracking_for_time_sync, usbioctl/IOCTL_USB_START_TRACKING_FOR_TIME_SYNC
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Usbioctl.h
api_name:
-	IOCTL_USB_START_TRACKING_FOR_TIME_SYNC
product: Windows
targetos: Windows
req.typenames: 
---

# IOCTL_USB_START_TRACKING_FOR_TIME_SYNC IOCTL


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

A pointer to a <a href="https://msdn.microsoft.com/2C82743C-2675-4196-839D-885EE17B2A7A">USB_START_TRACKING_FOR_TIME_SYNC_INFORMATION</a> structure. On input, the caller must set the <b>TimeTrackingHandle</b> member to NULL. On output, the USB driver stack sets the  <b>TimeTrackingHandle</b> member to a handle that tracks the sync services operation.


### -inout-buffer-length

The size of the <a href="https://msdn.microsoft.com/2C82743C-2675-4196-839D-885EE17B2A7A">USB_START_TRACKING_FOR_TIME_SYNC_INFORMATION</a> structure.


### -status-block

<b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> indicates an the appropriate error condition as a <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code. 


## -remarks



When this IOCTL request completes, the USB driver stack enables certain interrupts from the host controller to keep track of closest frame/microframe boundary in order  to predict the system QPC value with accuracy. Enabling the hardware interrupts adds an overhead to the power consumption because the CPU wakes up every 2.048 seconds when working in the D0 power state. Therefore we recommend that the caller should register for time sync services only when needed.

The driver stack disables those interrupts when it receives and completes the <a href="https://msdn.microsoft.com/232AC14B-CE3C-44AC-9428-5594993CD749">IOCTL_USB_STOP_TRACKING_FOR_TIME_SYNC</a> request.  




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff542894">Creating IOCTL Requests in Drivers</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548651">WdfIoTargetSendInternalIoctlOthersSynchronously</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548656">WdfIoTargetSendInternalIoctlSynchronously</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548660">WdfIoTargetSendIoctlSynchronously</a>
 

 

