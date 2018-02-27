---
UID: NS:usbioctl._USB_START_TRACKING_FOR_TIME_SYNC_INFORMATION
title: "_USB_START_TRACKING_FOR_TIME_SYNC_INFORMATION"
author: windows-driver-content
description: The input and output buffer for the IOCTL_USB_START_TRACKING_FOR_TIME_SYNC request.
old-location: buses\usb_start_tracking_for_time_sync_information.htm
old-project: usbref
ms.assetid: 2C82743C-2675-4196-839D-885EE17B2A7A
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PUSB_START_TRACKING_FOR_TIME_SYNC_INFORMATION, PUSB_START_TRACKING_FOR_TIME_SYNC_INFORMATION, PUSB_START_TRACKING_FOR_TIME_SYNC_INFORMATION structure pointer [Buses], USB_START_TRACKING_FOR_TIME_SYNC_INFORMATION, USB_START_TRACKING_FOR_TIME_SYNC_INFORMATION structure [Buses], _USB_START_TRACKING_FOR_TIME_SYNC_INFORMATION, buses.usb_start_tracking_for_time_sync_information, usbioctl/PUSB_START_TRACKING_FOR_TIME_SYNC_INFORMATION, usbioctl/USB_START_TRACKING_FOR_TIME_SYNC_INFORMATION"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.irql: "<=DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Usbioctl.h
apiname:
-	USB_START_TRACKING_FOR_TIME_SYNC_INFORMATION
product: Windows
targetos: Windows
req.typenames: USB_START_TRACKING_FOR_TIME_SYNC_INFORMATION, *PUSB_START_TRACKING_FOR_TIME_SYNC_INFORMATION
req.product: Windows 10 or later.
---

# _USB_START_TRACKING_FOR_TIME_SYNC_INFORMATION structure


## -description


The input and output buffer for the <a href="..\usbioctl\ni-usbioctl-ioctl_usb_start_tracking_for_time_sync.md">IOCTL_USB_START_TRACKING_FOR_TIME_SYNC</a> request.


## -syntax


````
typedef struct _USB_START_TRACKING_FOR_TIME_SYNC_INFORMATION {
  HANDLE  TimeTrackingHandle;
  BOOLEAN IsStartupDelayTolerable;
} USB_START_TRACKING_FOR_TIME_SYNC_INFORMATION, *PUSB_START_TRACKING_FOR_TIME_SYNC_INFORMATION;
````


## -struct-fields




### -field TimeTrackingHandle

Registration handle for time sync tracking retrieved through the <a href="..\usbioctl\ni-usbioctl-ioctl_usb_start_tracking_for_time_sync.md">IOCTL_USB_START_TRACKING_FOR_TIME_SYNC</a> request. On input, this handle must be set to NULL. On output, the USB driver stack sets this member to the assigned handle. 


### -field IsStartupDelayTolerable

On input, the caller must specify whether the initial startup latency of up to 2.048 seconds is tolerable. TRUE indicates that the caller can tolerate the initial startup latency FALSE, the registration is delayed until the USB driver stack is able to detect a valid frame or microframe boundary. 




## -see-also

<a href="..\usbioctl\ni-usbioctl-ioctl_usb_start_tracking_for_time_sync.md">IOCTL_USB_START_TRACKING_FOR_TIME_SYNC</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20USB_START_TRACKING_FOR_TIME_SYNC_INFORMATION structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

