---
UID: NS:usbioctl._USB_DEVICE_CHARACTERISTICS
title: _USB_DEVICE_CHARACTERISTICS (usbioctl.h)
description: Contains information about the USB device’s characteristics, such as the maximum send and receive delays for any request. This structure is used in the IOCTL_USB_GET_DEVICE_CHARACTERISTICS request.
old-location: buses\usb_device_characteristics.htm
tech.root: usbref
ms.assetid: D4A8DE43-3E81-4A1C-B1C0-ABE6000D9F11
ms.date: 05/07/2018
keywords: ["USB_DEVICE_CHARACTERISTICS structure"]
ms.keywords: "*PUSB_DEVICE_CHARACTERISTICS, PUSB_DEVICE_CHARACTERISTICS, PUSB_DEVICE_CHARACTERISTICS structure pointer [Buses], USB_DEVICE_CHARACTERISTICS, USB_DEVICE_CHARACTERISTICS structure [Buses], _USB_DEVICE_CHARACTERISTICS, buses.usb_device_characteristics, usbioctl/PUSB_DEVICE_CHARACTERISTICS, usbioctl/USB_DEVICE_CHARACTERISTICS"
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
targetos: Windows
req.typenames: USB_DEVICE_CHARACTERISTICS, *PUSB_DEVICE_CHARACTERISTICS
f1_keywords:
 - _USB_DEVICE_CHARACTERISTICS
 - usbioctl/_USB_DEVICE_CHARACTERISTICS
 - PUSB_DEVICE_CHARACTERISTICS
 - usbioctl/PUSB_DEVICE_CHARACTERISTICS
 - USB_DEVICE_CHARACTERISTICS
 - usbioctl/USB_DEVICE_CHARACTERISTICS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Usbioctl.h
api_name:
 - USB_DEVICE_CHARACTERISTICS
---

# _USB_DEVICE_CHARACTERISTICS structure


## -description

Contains information about the USB device’s characteristics, such as the maximum send and receive delays for any request.  This structure is used in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbioctl/ni-usbioctl-ioctl_usb_get_device_characteristics">IOCTL_USB_GET_DEVICE_CHARACTERISTICS</a> request.

## -struct-fields

### -field Version

The version should be set to USB_DEVICE_CHARACTERISTICS_VERSION_1.

### -field Reserved

Reserved.

### -field UsbDeviceCharacteristicsFlags

A bitmask of flags that indicates to  the client driver the transport characteristics that are available and are returned by this structure. 


If the USB_DEVICE_CHARACTERISTICS_MAXIMUM_PATH_DELAYS_AVAILABLE  

flag is set, <b>MaximumSendPathDelayInMilliSeconds</b> and <b>MaximumCompletionPathDelayInMilliSeconds</b> contain valid information. Otherwise they are not available and must not be used by the client driver.

### -field MaximumSendPathDelayInMilliSeconds

Contains the maximum delay in milliseconds for any request that is submitted by the client driver and is received by the USB driver stack to the time it is programmed in the host controller, including the maximum delay associated with the network medium if it is a MA-USB host controller.

### -field MaximumCompletionPathDelayInMilliSeconds

Contains the maximum delay in milliseconds the host controller completes any request for the device to the time the request is completed and sent back to the client driver.  For a MA-USB controller this includes any delay associated with the network medium.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbioctl/ni-usbioctl-ioctl_usb_get_device_characteristics">IOCTL_USB_GET_DEVICE_CHARACTERISTICS</a>

