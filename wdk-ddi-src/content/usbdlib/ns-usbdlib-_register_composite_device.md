---
UID: NS:usbdlib._REGISTER_COMPOSITE_DEVICE
title: "_REGISTER_COMPOSITE_DEVICE"
author: windows-driver-content
description: The REGISTER_COMPOSITE_DEVICE structure is used with the IOCTL_INTERNAL_USB_REGISTER_COMPOSITE_DEVICE I/O control request to register a parent driver of a Universal Serial Bus (USB) multi-function device (composite driver) with the USB driver stack.
old-location: buses\register_composite_driver.htm
old-project: usbref
ms.assetid: BBE92635-5230-454E-A6CA-80198B5B2C57
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PREGISTER_COMPOSITE_DEVICE, PREGISTER_COMPOSITE_DEVICE, PREGISTER_COMPOSITE_DEVICE structure pointer [Buses], REGISTER_COMPOSITE_DEVICE, REGISTER_COMPOSITE_DEVICE structure [Buses], _REGISTER_COMPOSITE_DEVICE, buses.register_composite_driver, usbdlib/PREGISTER_COMPOSITE_DEVICE, usbdlib/REGISTER_COMPOSITE_DEVICE"
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
-	usbdlib.h
api_name:
-	REGISTER_COMPOSITE_DEVICE
product: Windows
targetos: Windows
req.typenames: REGISTER_COMPOSITE_DEVICE, *PREGISTER_COMPOSITE_DEVICE
req.product: Windows 10 or later.
---

# _REGISTER_COMPOSITE_DEVICE structure


## -description


The <b>REGISTER_COMPOSITE_DEVICE</b> structure is used with the <a href="..\usbioctl\ni-usbioctl-ioctl_internal_usb_register_composite_device.md">IOCTL_INTERNAL_USB_REGISTER_COMPOSITE_DEVICE</a> I/O control request to register a  parent driver of a Universal Serial Bus (USB) multi-function device (composite driver)  with the USB driver stack. 

To initialize the <b>REGISTER_COMPOSITE_DEVICE</b> structure, the composite driver must call the <a href="..\usbdlib\nf-usbdlib-usbd_buildregistercompositedevice.md">USBD_BuildRegisterCompositeDevice</a> routine.


## -syntax


````
typedef struct _REGISTER_COMPOSITE_DEVICE {
  USHORT                        Version;
  USHORT                        Size;
  USBDI_HANDLE                  Reserved;
  COMPOSITE_DEVICE_CAPABILITIES CapabilityFlags;
  ULONG                         FunctionCount;
} REGISTER_COMPOSITE_DEVICE, *PREGISTER_COMPOSITE_DEVICE;
````


## -struct-fields




### -field Version

The version of this structure. <a href="..\usbdlib\nf-usbdlib-usbd_buildregistercompositedevice.md">USBD_BuildRegisterCompositeDevice</a> sets this  member.


### -field Size

The size of this structure. <a href="..\usbdlib\nf-usbdlib-usbd_buildregistercompositedevice.md">USBD_BuildRegisterCompositeDevice</a> sets this  member.


### -field Reserved

Reserved. <a href="..\usbdlib\nf-usbdlib-usbd_buildregistercompositedevice.md">USBD_BuildRegisterCompositeDevice</a> sets this  member.


### -field CapabilityFlags

The capabilities that are supported by the composite driver.
To specify that function suspend is supported by the composite driver, first initialize the <a href="..\usbdlib\ns-usbdlib-_composite_device_capabilities.md">COMPOSITE_DEVICE_CAPABILITIES</a> structure by calling the <a href="..\usbdlib\nf-usbdlib-composite_device_capabilities_init.md">COMPOSITE_DEVICE_CAPABILITIES_INIT</a> macro. Then, set the <b>CompositeDeviceCapabilityFunctionSuspend</b>
member of <b>COMPOSITE_DEVICE_CAPABILITIES</b> to 1. Finally, call <a href="..\usbdlib\nf-usbdlib-usbd_buildregistercompositedevice.md">USBD_BuildRegisterCompositeDevice</a> and pass the initialized structure in the  <i>CapabilityFlags</i> parameter.


### -field FunctionCount

The number of functions supported by the composite device. The <b>FunctionCount</b> value must not exceed 255.


## -see-also

<a href="..\usbdlib\nf-usbdlib-usbd_buildregistercompositedevice.md">USBD_BuildRegisterCompositeDevice</a>



<a href="..\usbioctl\ni-usbioctl-ioctl_internal_usb_register_composite_device.md">IOCTL_INTERNAL_USB_REGISTER_COMPOSITE_DEVICE</a>



<a href="..\usbdlib\nf-usbdlib-composite_device_capabilities_init.md">COMPOSITE_DEVICE_CAPABILITIES_INIT</a>



<a href="..\usbdlib\ns-usbdlib-_composite_device_capabilities.md">COMPOSITE_DEVICE_CAPABILITIES</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20REGISTER_COMPOSITE_DEVICE structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

