---
UID: NS:usbioctl._USB_DEVICE_CHARACTERISTICS
title: _USB_DEVICE_CHARACTERISTICS
author: windows-driver-content
description: Contains information about the USB device’s characteristics, such as the maximum send and receive delays for any request. This structure is used in the IOCTL_USB_GET_DEVICE_CHARACTERISTICS request.
old-location: buses\usb_device_characteristics.htm
old-project: usbref
ms.assetid: D4A8DE43-3E81-4A1C-B1C0-ABE6000D9F11
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: _USB_DEVICE_CHARACTERISTICS, USB_DEVICE_CHARACTERISTICS, *PUSB_DEVICE_CHARACTERISTICS
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
req.alt-api: USB_DEVICE_CHARACTERISTICS
req.alt-loc: Usbioctl.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <=DISPATCH_LEVEL
req.typenames: USB_DEVICE_CHARACTERISTICS, *PUSB_DEVICE_CHARACTERISTICS
req.product: Windows 10 or later.
---

# _USB_DEVICE_CHARACTERISTICS structure



## -description
Contains information about the USB device’s characteristics, such as the maximum send and receive delays for any request.  This structure is used in the <a href="..\usbioctl\ni-usbioctl-ioctl_usb_get_device_characteristics.md">IOCTL_USB_GET_DEVICE_CHARACTERISTICS</a> request.



## -syntax

````
typedef struct _USB_DEVICE_CHARACTERISTICS {
  ULONG                     Version;
  ULONG                     Reserved[2];
  ULONG                     UsbDeviceCharacteristicsFlags;
  ULONG                     MaximumSendPathDelayInMilliSeconds;
  ULONG                     MaximumCompletionPathDelayInMilliSeconds;
} USB_DEVICE_CHARACTERISTICS, *PUSB_DEVICE_CHARACTERISTICS;
````


## -struct-fields

### -field                     Version

The version should be set to USB_DEVICE_CHARACTERISTICS_VERSION_1. 



### -field                     Reserved

Reserved.


### -field                     UsbDeviceCharacteristicsFlags

A bitmask of flags that indicates to  the client driver the transport characteristics that are available and are returned by this structure. 


If the USB_DEVICE_CHARACTERISTICS_MAXIMUM_PATH_DELAYS_AVAILABLE  

flag is set, <b>MaximumSendPathDelayInMilliSeconds</b> and <b>MaximumCompletionPathDelayInMilliSeconds</b> contain valid information. Otherwise they are not available and must not be used by the client driver. 



### -field                     MaximumSendPathDelayInMilliSeconds

Contains the maximum delay in milliseconds for any request that is submitted by the client driver and is received by the USB driver stack to the time it is programmed in the host controller, including the maximum delay associated with the network medium if it is a MA-USB host controller. 
 



### -field                     MaximumCompletionPathDelayInMilliSeconds

Contains the maximum delay in milliseconds the host controller completes any request for the device to the time the request is completed and sent back to the client driver.  For a MA-USB controller this includes any delay associated with the network medium. 



## -remarks


## -see-also
<dl>
<dt>
<a href="..\usbioctl\ni-usbioctl-ioctl_usb_get_device_characteristics.md">IOCTL_USB_GET_DEVICE_CHARACTERISTICS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20USB_DEVICE_CHARACTERISTICS structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

