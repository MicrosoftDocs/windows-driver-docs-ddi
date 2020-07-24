---
UID: NS:usbioctl._USB_START_TRACKING_FOR_TIME_SYNC_INFORMATION
title: _USB_START_TRACKING_FOR_TIME_SYNC_INFORMATION (usbioctl.h)
description: The input and output buffer for the IOCTL_USB_START_TRACKING_FOR_TIME_SYNC request.
old-location: buses\usb_start_tracking_for_time_sync_information.htm
tech.root: usbref
ms.assetid: 2C82743C-2675-4196-839D-885EE17B2A7A
ms.date: 05/07/2018
keywords: ["_USB_START_TRACKING_FOR_TIME_SYNC_INFORMATION structure"]
ms.keywords: "*PUSB_START_TRACKING_FOR_TIME_SYNC_INFORMATION, PUSB_START_TRACKING_FOR_TIME_SYNC_INFORMATION, PUSB_START_TRACKING_FOR_TIME_SYNC_INFORMATION structure pointer [Buses], USB_START_TRACKING_FOR_TIME_SYNC_INFORMATION, USB_START_TRACKING_FOR_TIME_SYNC_INFORMATION structure [Buses], _USB_START_TRACKING_FOR_TIME_SYNC_INFORMATION, buses.usb_start_tracking_for_time_sync_information, usbioctl/PUSB_START_TRACKING_FOR_TIME_SYNC_INFORMATION, usbioctl/USB_START_TRACKING_FOR_TIME_SYNC_INFORMATION"
f1_keywords:
 - "usbioctl/USB_START_TRACKING_FOR_TIME_SYNC_INFORMATION"
 - "USB_START_TRACKING_FOR_TIME_SYNC_INFORMATION"
req.header: usbioctl.h
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Usbioctl.h
api_name:
- USB_START_TRACKING_FOR_TIME_SYNC_INFORMATION
targetos: Windows
req.typenames: USB_START_TRACKING_FOR_TIME_SYNC_INFORMATION, *PUSB_START_TRACKING_FOR_TIME_SYNC_INFORMATION
---

# _USB_START_TRACKING_FOR_TIME_SYNC_INFORMATION structure


## -description


The input and output buffer for the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbioctl/ni-usbioctl-ioctl_usb_start_tracking_for_time_sync">IOCTL_USB_START_TRACKING_FOR_TIME_SYNC</a> request.


## -struct-fields




### -field TimeTrackingHandle

Registration handle for time sync tracking retrieved through the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbioctl/ni-usbioctl-ioctl_usb_start_tracking_for_time_sync">IOCTL_USB_START_TRACKING_FOR_TIME_SYNC</a> request. On input, this handle must be set to NULL. On output, the USB driver stack sets this member to the assigned handle. 


### -field IsStartupDelayTolerable

On input, the caller must specify whether the initial startup latency of up to 2.048 seconds is tolerable. TRUE indicates that the caller can tolerate the initial startup latency FALSE, the registration is delayed until the USB driver stack is able to detect a valid frame or microframe boundary. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbioctl/ni-usbioctl-ioctl_usb_start_tracking_for_time_sync">IOCTL_USB_START_TRACKING_FOR_TIME_SYNC</a>
 

 

