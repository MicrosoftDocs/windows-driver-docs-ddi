---
UID: NS:usbdlib._REGISTER_COMPOSITE_DEVICE
title: _REGISTER_COMPOSITE_DEVICE (usbdlib.h)
description: The REGISTER_COMPOSITE_DEVICE structure is used with the IOCTL_INTERNAL_USB_REGISTER_COMPOSITE_DEVICE I/O control request to register a parent driver of a Universal Serial Bus (USB) multi-function device (composite driver) with the USB driver stack.
old-location: buses\register_composite_driver.htm
tech.root: usbref
ms.assetid: BBE92635-5230-454E-A6CA-80198B5B2C57
ms.date: 05/07/2018
keywords: ["REGISTER_COMPOSITE_DEVICE structure"]
ms.keywords: "*PREGISTER_COMPOSITE_DEVICE, PREGISTER_COMPOSITE_DEVICE, PREGISTER_COMPOSITE_DEVICE structure pointer [Buses], REGISTER_COMPOSITE_DEVICE, REGISTER_COMPOSITE_DEVICE structure [Buses], _REGISTER_COMPOSITE_DEVICE, buses.register_composite_driver, usbdlib/PREGISTER_COMPOSITE_DEVICE, usbdlib/REGISTER_COMPOSITE_DEVICE"
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
targetos: Windows
req.typenames: REGISTER_COMPOSITE_DEVICE, *PREGISTER_COMPOSITE_DEVICE
f1_keywords:
 - _REGISTER_COMPOSITE_DEVICE
 - usbdlib/_REGISTER_COMPOSITE_DEVICE
 - PREGISTER_COMPOSITE_DEVICE
 - usbdlib/PREGISTER_COMPOSITE_DEVICE
 - REGISTER_COMPOSITE_DEVICE
 - usbdlib/REGISTER_COMPOSITE_DEVICE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - usbdlib.h
api_name:
 - REGISTER_COMPOSITE_DEVICE
---

# _REGISTER_COMPOSITE_DEVICE structure


## -description

The <b>REGISTER_COMPOSITE_DEVICE</b> structure is used with the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbioctl/ni-usbioctl-ioctl_internal_usb_register_composite_device">IOCTL_INTERNAL_USB_REGISTER_COMPOSITE_DEVICE</a> I/O control request to register a  parent driver of a Universal Serial Bus (USB) multi-function device (composite driver)  with the USB driver stack. 

To initialize the <b>REGISTER_COMPOSITE_DEVICE</b> structure, the composite driver must call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbdlib/nf-usbdlib-usbd_buildregistercompositedevice">USBD_BuildRegisterCompositeDevice</a> routine.

## -struct-fields

### -field Version

The version of this structure. <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbdlib/nf-usbdlib-usbd_buildregistercompositedevice">USBD_BuildRegisterCompositeDevice</a> sets this  member.

### -field Size

The size of this structure. <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbdlib/nf-usbdlib-usbd_buildregistercompositedevice">USBD_BuildRegisterCompositeDevice</a> sets this  member.

### -field Reserved

Reserved. <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbdlib/nf-usbdlib-usbd_buildregistercompositedevice">USBD_BuildRegisterCompositeDevice</a> sets this  member.

### -field CapabilityFlags

The capabilities that are supported by the composite driver.
To specify that function suspend is supported by the composite driver, first initialize the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbdlib/ns-usbdlib-_composite_device_capabilities">COMPOSITE_DEVICE_CAPABILITIES</a> structure by calling the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbdlib/nf-usbdlib-composite_device_capabilities_init">COMPOSITE_DEVICE_CAPABILITIES_INIT</a> macro. Then, set the <b>CompositeDeviceCapabilityFunctionSuspend</b>
member of <b>COMPOSITE_DEVICE_CAPABILITIES</b> to 1. Finally, call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbdlib/nf-usbdlib-usbd_buildregistercompositedevice">USBD_BuildRegisterCompositeDevice</a> and pass the initialized structure in the  <i>CapabilityFlags</i> parameter.

### -field FunctionCount

The number of functions supported by the composite device. The <b>FunctionCount</b> value must not exceed 255.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbdlib/ns-usbdlib-_composite_device_capabilities">COMPOSITE_DEVICE_CAPABILITIES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbdlib/nf-usbdlib-composite_device_capabilities_init">COMPOSITE_DEVICE_CAPABILITIES_INIT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbioctl/ni-usbioctl-ioctl_internal_usb_register_composite_device">IOCTL_INTERNAL_USB_REGISTER_COMPOSITE_DEVICE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbdlib/nf-usbdlib-usbd_buildregistercompositedevice">USBD_BuildRegisterCompositeDevice</a>

