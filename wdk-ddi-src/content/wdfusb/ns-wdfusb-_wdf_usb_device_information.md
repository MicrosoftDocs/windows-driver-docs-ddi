---
UID: NS:wdfusb._WDF_USB_DEVICE_INFORMATION
title: _WDF_USB_DEVICE_INFORMATION (wdfusb.h)
description: The WDF_USB_DEVICE_INFORMATION structure contains version and capability information for a USB device.
old-location: wdf\wdf_usb_device_information.htm
tech.root: wdf
ms.assetid: 5d212a29-22b9-408d-9562-b232fc91cc9f
ms.date: 02/26/2018
ms.keywords: "*PWDF_USB_DEVICE_INFORMATION, DFUsbRef_eb36dfae-7210-4949-acbf-7d0b0edf4061.xml, PWDF_USB_DEVICE_INFORMATION, PWDF_USB_DEVICE_INFORMATION structure pointer, WDF_USB_DEVICE_INFORMATION, WDF_USB_DEVICE_INFORMATION structure, _WDF_USB_DEVICE_INFORMATION, kmdf.wdf_usb_device_information, wdf.wdf_usb_device_information, wdfusb/PWDF_USB_DEVICE_INFORMATION, wdfusb/WDF_USB_DEVICE_INFORMATION"
ms.topic: struct
f1_keywords:
 - "wdfusb/WDF_USB_DEVICE_INFORMATION"
req.header: wdfusb.h
req.include-header: Wdfusb.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- wdfusb.h
api_name:
- WDF_USB_DEVICE_INFORMATION
product:
- Windows
targetos: Windows
req.typenames: WDF_USB_DEVICE_INFORMATION, *PWDF_USB_DEVICE_INFORMATION
---

# _WDF_USB_DEVICE_INFORMATION structure


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WDF_USB_DEVICE_INFORMATION</b> structure contains version and capability information for a USB device.


## -struct-fields




### -field Size

The size, in bytes, of this structure. 


### -field UsbdVersionInformation

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usb/ns-usb-_usbd_version_information">USBD_VERSION_INFORMATION</a> structure that provides version information for the host controller driver (HCD) and the USB specification version that the device supports.


### -field HcdPortCapabilities

This member is reserved for system use.


### -field Traits

A set of bit flags that identify device traits. The flags are defined by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/ne-wdfusb-_wdf_usb_device_traits">WDF_USB_DEVICE_TRAITS</a> enumeration.


## -remarks



The <b>WDF_USB_DEVICE_INFORMATION</b> structure is filled in by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbtargetdeviceretrieveinformation">WdfUsbTargetDeviceRetrieveInformation</a> method. Before calling <b>WdfUsbTargetDeviceRetrieveInformation</b>, the driver must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdf_usb_device_information_init">WDF_USB_DEVICE_INFORMATION_INIT</a> to initialize the structure.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usb/ns-usb-_usbd_version_information">USBD_VERSION_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdf_usb_device_information_init">WDF_USB_DEVICE_INFORMATION_INIT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/ne-wdfusb-_wdf_usb_device_traits">WDF_USB_DEVICE_TRAITS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbtargetdeviceretrieveinformation">WdfUsbTargetDeviceRetrieveInformation</a>
 

 

