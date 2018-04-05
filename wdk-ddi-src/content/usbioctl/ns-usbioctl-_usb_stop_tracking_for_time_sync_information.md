---
UID: NS:usbioctl._USB_STOP_TRACKING_FOR_TIME_SYNC_INFORMATION
title: "_USB_STOP_TRACKING_FOR_TIME_SYNC_INFORMATION"
author: windows-driver-content
description: The input buffer for the IOCTL_USB_STOP_TRACKING_FOR_TIME_SYNC request.
old-location: buses\usb_stop_tracking_for_time_sync_information.htm
old-project: usbref
ms.assetid: FFD7979B-48E9-433C-86A9-255F4F422BBA
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PUSB_STOP_TRACKING_FOR_TIME_SYNC_INFORMATION, PUSB_STOP_TRACKING_FOR_TIME_SYNC_INFORMATION, PUSB_STOP_TRACKING_FOR_TIME_SYNC_INFORMATION structure pointer [Buses], USB_STOP_TRACKING_FOR_TIME_SYNC_INFORMATION, USB_STOP_TRACKING_FOR_TIME_SYNC_INFORMATION structure [Buses], _USB_STOP_TRACKING_FOR_TIME_SYNC_INFORMATION, buses.usb_stop_tracking_for_time_sync_information, usbioctl/PUSB_STOP_TRACKING_FOR_TIME_SYNC_INFORMATION, usbioctl/USB_STOP_TRACKING_FOR_TIME_SYNC_INFORMATION"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: usbioctl.h
req.include-header: TBD
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	usbioctl.h
api_name:
-	USB_STOP_TRACKING_FOR_TIME_SYNC_INFORMATION
product:
- Windows
targetos: Windows
req.typenames: USB_STOP_TRACKING_FOR_TIME_SYNC_INFORMATION, *PUSB_STOP_TRACKING_FOR_TIME_SYNC_INFORMATION
req.product: Windows 10 or later.
---

# _USB_STOP_TRACKING_FOR_TIME_SYNC_INFORMATION structure


## -description


The input buffer for the <a href="https://msdn.microsoft.com/232AC14B-CE3C-44AC-9428-5594993CD749">IOCTL_USB_STOP_TRACKING_FOR_TIME_SYNC</a> request.


## -struct-fields




### -field TimeTrackingHandle

The time racking handle received in the previous <a href="https://msdn.microsoft.com/232AC14B-CE3C-44AC-9428-5594993CD749">IOCTL_USB_STOP_TRACKING_FOR_TIME_SYNC</a> request.


## -see-also




<a href="https://msdn.microsoft.com/232AC14B-CE3C-44AC-9428-5594993CD749">IOCTL_USB_STOP_TRACKING_FOR_TIME_SYNC</a>
 

 

