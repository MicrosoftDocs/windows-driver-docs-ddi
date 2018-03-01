---
UID: NS:usbioctl._HUB_DEVICE_CONFIG_INFO_V1
title: "_HUB_DEVICE_CONFIG_INFO_V1"
author: windows-driver-content
description: The HUB_DEVICE_CONFIG_INFO structure is used in conjunction with the kernel-mode IOCTL, IOCTL_INTERNAL_USB_GET_DEVICE_CONFIG_INFO to request to report information about a USB device and the hub to which the device is attached.
old-location: buses\hub_device_config_info.htm
old-project: usbref
ms.assetid: 2e94cf01-6edf-40ca-b25e-ce7c125e4686
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PHUB_DEVICE_CONFIG_INFO, HUB_DEVICE_CONFIG_INFO, HUB_DEVICE_CONFIG_INFO structure [Buses], PHUB_DEVICE_CONFIG_INFO, PHUB_DEVICE_CONFIG_INFO structure pointer [Buses], _HUB_DEVICE_CONFIG_INFO_V1, buses.hub_device_config_info, usbioctl/HUB_DEVICE_CONFIG_INFO, usbioctl/PHUB_DEVICE_CONFIG_INFO"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: usbioctl.h
req.include-header: Usbioctl.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows XP and later operating systems.
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
-	HUB_DEVICE_CONFIG_INFO
product: Windows
targetos: Windows
req.typenames: HUB_DEVICE_CONFIG_INFO, *PHUB_DEVICE_CONFIG_INFO
req.product: Windows 10 or later.
---

# _HUB_DEVICE_CONFIG_INFO_V1 structure


## -description


The <b>HUB_DEVICE_CONFIG_INFO</b> structure is used in conjunction with the kernel-mode IOCTL, <a href="..\usbioctl\ni-usbioctl-ioctl_internal_usb_get_device_config_info.md">IOCTL_INTERNAL_USB_GET_DEVICE_CONFIG_INFO</a> to request to report information about a USB device and the hub to which the device is attached. 


## -syntax


````
typedef struct _HUB_DEVICE_CONFIG_INFO {
  ULONG              Version;
  ULONG              Length;
  USB_HUB_CAP_FLAGS  HubFlags;
  USB_ID_STRING      HardwareIds;
  USB_ID_STRING      CompatibleIds;
  USB_ID_STRING      DeviceDescription;
} HUB_DEVICE_CONFIG_INFO, *PHUB_DEVICE_CONFIG_INFO;
````


## -struct-fields




### -field Version

Specifies the version number.  Must be set to 1. 


### -field Length

Specifies the size of the <b>HUB_DEVICE_CONFIG_INFO</b> structure. Must be set by the caller.


### -field HubFlags

Specifies the hub capabilities in a <a href="..\usbioctl\ns-usbioctl-_usb_hub_cap_flags.md">USB_HUB_CAP_FLAGS</a> structure.  


### -field HardwareIds

The PnP hardware ID multi-string for the USB device in a <a href="..\usbioctl\ns-usbioctl-_usb_id_string.md">USB_ID_STRING</a> structure. 


### -field CompatibleIds

 PnP compatible ID multi-string for the USB device in a <a href="..\usbioctl\ns-usbioctl-_usb_id_string.md">USB_ID_STRING</a> structure. 


### -field DeviceDescription

Description of the device in a <a href="..\usbioctl\ns-usbioctl-_usb_id_string.md">USB_ID_STRING</a> structure. This may be set to <b>NULL</b>.


### -field Reserved

 


### -field UxdSettings

 




## -remarks




 The <b>Buffer</b> member of the <a href="..\usbioctl\ns-usbioctl-_usb_id_string.md">USB_ID_STRING</a> structure points to a string that contains <b>HardwareIds</b>, <b>CompatibleIds</b>, and <b>DeviceDescription</b> values.
The caller is responsible for releasing this string buffer, which is allocated by the hub driver.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540160">USB Structures</a>



<a href="..\usbioctl\ns-usbioctl-_usb_hub_cap_flags.md">USB_HUB_CAP_FLAGS</a>



<a href="..\usbioctl\ns-usbioctl-_usb_id_string.md">USB_ID_STRING</a>



<a href="..\usbioctl\ni-usbioctl-ioctl_internal_usb_get_device_config_info.md">IOCTL_INTERNAL_USB_GET_DEVICE_CONFIG_INFO</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20HUB_DEVICE_CONFIG_INFO structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

