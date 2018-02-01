---
UID: NS:usbdlib._COMPOSITE_DEVICE_CAPABILITIES
title: "_COMPOSITE_DEVICE_CAPABILITIES"
author: windows-driver-content
description: The COMPOSITE_DEVICE_CAPABILITIES structure specifies the capabilities of the driver of a USB multi-function device (composite driver). To initialize the structure, use the COMPOSITE_DEVICE_CAPABILITIES_INIT macro.
old-location: buses\composite_driver_capabilities.htm
old-project: usbref
ms.assetid: 3C1BF8C6-3489-4636-9B3F-B0C2C1327466
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: usbdlib/COMPOSITE_DEVICE_CAPABILITIES, _COMPOSITE_DEVICE_CAPABILITIES, *PCOMPOSITE_DEVICE_CAPABILITIES, usbdlib/PCOMPOSITE_DEVICE_CAPABILITIES, PCOMPOSITE_DEVICE_CAPABILITIES structure pointer [Buses], buses.composite_driver_capabilities, PCOMPOSITE_DEVICE_CAPABILITIES, COMPOSITE_DEVICE_CAPABILITIES, COMPOSITE_DEVICE_CAPABILITIES structure [Buses]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: usbdlib.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8.
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	usbdlib.h
apiname:
-	COMPOSITE_DEVICE_CAPABILITIES
product: Windows
targetos: Windows
req.typenames: "*PCOMPOSITE_DEVICE_CAPABILITIES, COMPOSITE_DEVICE_CAPABILITIES"
req.product: Windows 10 or later.
---

# _COMPOSITE_DEVICE_CAPABILITIES structure


## -description


The <b>COMPOSITE_DEVICE_CAPABILITIES</b> structure specifies the capabilities of the  driver of a USB multi-function device (composite driver). To initialize the structure, use the <a href="..\usbdlib\nf-usbdlib-composite_device_capabilities_init.md">COMPOSITE_DEVICE_CAPABILITIES_INIT</a> macro.


## -syntax


````
typedef struct _COMPOSITE_DEVICE_CAPABILITIES {
  ULONG  CapabilityFunctionSuspend  :1;
  ULONG  Reserved  :31;
} COMPOSITE_DEVICE_CAPABILITIES, *PCOMPOSITE_DEVICE_CAPABILITIES;
````


## -struct-fields




### -field CapabilityFunctionSuspend

If set to 1, indicates that the composite driver supports the USB function suspend feature. 


### -field Reserved

Reserved.


## -see-also

<a href="..\usbdlib\nf-usbdlib-composite_device_capabilities_init.md">COMPOSITE_DEVICE_CAPABILITIES_INIT</a>

<a href="..\usbioctl\ni-usbioctl-ioctl_internal_usb_register_composite_device.md">IOCTL_INTERNAL_USB_REGISTER_COMPOSITE_DEVICE</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh450897">How to Register a Composite Device</a>

<a href="..\usbdlib\ns-usbdlib-_register_composite_device.md">REGISTER_COMPOSITE_DEVICE</a>

<a href="..\usbdlib\nf-usbdlib-usbd_buildregistercompositedevice.md">USBD_BuildRegisterCompositeDevice</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20 COMPOSITE_DEVICE_CAPABILITIES structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

