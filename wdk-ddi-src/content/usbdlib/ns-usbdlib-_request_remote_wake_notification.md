---
UID: NS:usbdlib._REQUEST_REMOTE_WAKE_NOTIFICATION
title: _REQUEST_REMOTE_WAKE_NOTIFICATION (usbdlib.h)
description: The purpose of the REQUEST_REMOTE_WAKE_NOTIFICATION structure is to specify input parameters for the IOCTL_INTERNAL_USB_REQUEST_REMOTE_WAKE_NOTIFICATION I/O control request.
old-location: buses\usbdevice_remote_wake_notification.htm
tech.root: usbref
ms.assetid: 229B22AC-8252-4D94-BDB5-F1132BF4AE4C
ms.date: 05/07/2018
ms.keywords: "*PREQUEST_REMOTE_WAKE_NOTIFICATION, PREQUEST_REMOTE_WAKE_NOTIFICATION, PREQUEST_REMOTE_WAKE_NOTIFICATION structure pointer [Buses], REQUEST_REMOTE_WAKE_NOTIFICATION, REQUEST_REMOTE_WAKE_NOTIFICATION structure [Buses], _REQUEST_REMOTE_WAKE_NOTIFICATION, buses.usbdevice_remote_wake_notification, usbdlib/PREQUEST_REMOTE_WAKE_NOTIFICATION, usbdlib/REQUEST_REMOTE_WAKE_NOTIFICATION"
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Usbdlib.h
api_name:
-	REQUEST_REMOTE_WAKE_NOTIFICATION
product:
- Windows
targetos: Windows
req.typenames: REQUEST_REMOTE_WAKE_NOTIFICATION, *PREQUEST_REMOTE_WAKE_NOTIFICATION
---

# _REQUEST_REMOTE_WAKE_NOTIFICATION structure


## -description


The purpose of the <b>REQUEST_REMOTE_WAKE_NOTIFICATION</b> structure is to specify input parameters for the  <a href="https://msdn.microsoft.com/library/windows/hardware/hh450856">IOCTL_INTERNAL_USB_REQUEST_REMOTE_WAKE_NOTIFICATION</a> I/O control request. 


## -struct-fields




### -field Version

The version of this structure. Set to 0.


### -field Size

The size of the <b>REQUEST_REMOTE_WAKE_NOTIFICATION</b> structure.


### -field UsbdFunctionHandle

A function handle that is associated with the function that sends the resume signal. The handle was obtained in a previous <a href="https://msdn.microsoft.com/library/windows/hardware/hh450854">IOCTL_INTERNAL_USB_REGISTER_COMPOSITE_DEVICE</a> request.


### -field Interface

Specifies the device-defined index identifier of the interface with which the function is associated.


## -see-also




<a href="https://msdn.microsoft.com/91F96D30-CD18-4DDC-BA5A-7BFFA8FBED9B">How to Implement Function Suspend in a Composite Driver</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh450854">IOCTL_INTERNAL_USB_REGISTER_COMPOSITE_DEVICE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh450856">IOCTL_INTERNAL_USB_REQUEST_REMOTE_WAKE_NOTIFICATION</a>
 

 

