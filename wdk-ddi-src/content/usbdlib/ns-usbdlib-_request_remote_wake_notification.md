---
UID: NS:usbdlib._REQUEST_REMOTE_WAKE_NOTIFICATION
title: "_REQUEST_REMOTE_WAKE_NOTIFICATION"
author: windows-driver-content
description: The purpose of the REQUEST_REMOTE_WAKE_NOTIFICATION structure is to specify input parameters for the IOCTL_INTERNAL_USB_REQUEST_REMOTE_WAKE_NOTIFICATION I/O control request.
old-location: buses\usbdevice_remote_wake_notification.htm
old-project: usbref
ms.assetid: 229B22AC-8252-4D94-BDB5-F1132BF4AE4C
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PREQUEST_REMOTE_WAKE_NOTIFICATION, PREQUEST_REMOTE_WAKE_NOTIFICATION, PREQUEST_REMOTE_WAKE_NOTIFICATION structure pointer [Buses], REQUEST_REMOTE_WAKE_NOTIFICATION, REQUEST_REMOTE_WAKE_NOTIFICATION structure [Buses], _REQUEST_REMOTE_WAKE_NOTIFICATION, buses.usbdevice_remote_wake_notification, usbdlib/PREQUEST_REMOTE_WAKE_NOTIFICATION, usbdlib/REQUEST_REMOTE_WAKE_NOTIFICATION"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: usbdlib.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Usbdlib.h
api_name:
-	REQUEST_REMOTE_WAKE_NOTIFICATION
product: Windows
targetos: Windows
req.typenames: REQUEST_REMOTE_WAKE_NOTIFICATION, *PREQUEST_REMOTE_WAKE_NOTIFICATION
req.product: Windows 10 or later.
---

# _REQUEST_REMOTE_WAKE_NOTIFICATION structure


## -description


The purpose of the <b>REQUEST_REMOTE_WAKE_NOTIFICATION</b> structure is to specify input parameters for the  <a href="..\usbioctl\ni-usbioctl-ioctl_internal_usb_request_remote_wake_notification.md">IOCTL_INTERNAL_USB_REQUEST_REMOTE_WAKE_NOTIFICATION</a> I/O control request. 


## -syntax


````
typedef struct _REQUEST_REMOTE_WAKE_NOTIFICATION {
  USHORT               Version;
  USHORT               Size;
  USBD_FUNCTION_HANDLE UsbdFunctionHandle;
  ULONG                Interface;
} REQUEST_REMOTE_WAKE_NOTIFICATION, *PREQUEST_REMOTE_WAKE_NOTIFICATION;
````


## -struct-fields




### -field Version

The version of this structure. Set to 0.


### -field Size

The size of the <b>REQUEST_REMOTE_WAKE_NOTIFICATION</b> structure.


### -field UsbdFunctionHandle

A function handle that is associated with the function that sends the resume signal. The handle was obtained in a previous <a href="..\usbioctl\ni-usbioctl-ioctl_internal_usb_register_composite_device.md">IOCTL_INTERNAL_USB_REGISTER_COMPOSITE_DEVICE</a> request.


### -field Interface

Specifies the device-defined index identifier of the interface with which the function is associated.


## -see-also

<a href="https://msdn.microsoft.com/91F96D30-CD18-4DDC-BA5A-7BFFA8FBED9B">How to Implement Function Suspend in a Composite Driver</a>



<a href="..\usbioctl\ni-usbioctl-ioctl_internal_usb_request_remote_wake_notification.md">IOCTL_INTERNAL_USB_REQUEST_REMOTE_WAKE_NOTIFICATION</a>



<a href="..\usbioctl\ni-usbioctl-ioctl_internal_usb_register_composite_device.md">IOCTL_INTERNAL_USB_REGISTER_COMPOSITE_DEVICE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20REQUEST_REMOTE_WAKE_NOTIFICATION structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

