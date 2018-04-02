---
UID: NI:usbioctl.IOCTL_USB_STOP_TRACKING_FOR_TIME_SYNC
title: IOCTL_USB_STOP_TRACKING_FOR_TIME_SYNC
author: windows-driver-content
description: This request unegisters the caller with USB driver stack for time sync services.
old-location: buses\_ioctl_usb_stop_tracking_for_time_sync.htm
old-project: usbref
ms.assetid: 232AC14B-CE3C-44AC-9428-5594993CD749
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IOCTL_USB_STOP_TRACKING_FOR_TIME_SYNC, IOCTL_USB_STOP_TRACKING_FOR_TIME_SYNC control code [Buses], buses._ioctl_usb_stop_tracking_for_time_sync, usbioctl/ IOCTL_USB_STOP_TRACKING_FOR_TIME_SYNC
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
-	IOCTL_USB_STOP_TRACKING_FOR_TIME_SYNC
product: Windows
targetos: Windows
req.typenames: USB_HUB_TYPE
req.product: Windows 10 or later.
---

# IOCTL_USB_STOP_TRACKING_FOR_TIME_SYNC IOCTL


## -description


This request unegisters the caller with USB driver stack for time sync services. 


## -ioctlparameters




### -input-buffer

A pointer to a <a href="https://msdn.microsoft.com/FFD7979B-48E9-433C-86A9-255F4F422BBA">USB_STOP_TRACKING_FOR_TIME_SYNC_INFORMATION</a> structure that contains the time tracking handle previously received through the <a href="https://msdn.microsoft.com/C9EA7A04-3B53-46D4-BC1B-A2766577095F">IOCTL_USB_START_TRACKING_FOR_TIME_SYNC</a> request.


### -input-buffer-length

The size of the <a href="https://msdn.microsoft.com/FFD7979B-48E9-433C-86A9-255F4F422BBA">USB_STOP_TRACKING_FOR_TIME_SYNC_INFORMATION</a> structure.


### -output-buffer



<text></text>




### -output-buffer-length



<text></text>




### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

<b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> indicates an the appropriate error condition as a <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code. 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff542894">Creating IOCTL Requests in Drivers</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548651">WdfIoTargetSendInternalIoctlOthersSynchronously</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548656">WdfIoTargetSendInternalIoctlSynchronously</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548660">WdfIoTargetSendIoctlSynchronously</a>
 

 

