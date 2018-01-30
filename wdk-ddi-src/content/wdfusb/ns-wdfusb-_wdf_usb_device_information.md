---
UID: NS:wdfusb._WDF_USB_DEVICE_INFORMATION
title: "_WDF_USB_DEVICE_INFORMATION"
author: windows-driver-content
description: The WDF_USB_DEVICE_INFORMATION structure contains version and capability information for a USB device.
old-location: wdf\wdf_usb_device_information.htm
old-project: wdf
ms.assetid: 5d212a29-22b9-408d-9562-b232fc91cc9f
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdfusb/PWDF_USB_DEVICE_INFORMATION, *PWDF_USB_DEVICE_INFORMATION, wdf.wdf_usb_device_information, kmdf.wdf_usb_device_information, PWDF_USB_DEVICE_INFORMATION, WDF_USB_DEVICE_INFORMATION, DFUsbRef_eb36dfae-7210-4949-acbf-7d0b0edf4061.xml, PWDF_USB_DEVICE_INFORMATION structure pointer, wdfusb/WDF_USB_DEVICE_INFORMATION, WDF_USB_DEVICE_INFORMATION structure, _WDF_USB_DEVICE_INFORMATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdfusb.h
apiname:
-	WDF_USB_DEVICE_INFORMATION
product: Windows
targetos: Windows
req.typenames: WDF_USB_DEVICE_INFORMATION, *PWDF_USB_DEVICE_INFORMATION
req.product: Windows 10 or later.
---

# _WDF_USB_DEVICE_INFORMATION structure


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_USB_DEVICE_INFORMATION</b> structure contains version and capability information for a USB device.


## -syntax


````
typedef struct _WDF_USB_DEVICE_INFORMATION {
  ULONG                    Size;
  USBD_VERSION_INFORMATION UsbdVersionInformation;
  ULONG                    HcdPortCapabilities;
  ULONG                    Traits;
} WDF_USB_DEVICE_INFORMATION, *PWDF_USB_DEVICE_INFORMATION;
````


## -struct-fields




### -field Size

The size, in bytes, of this structure. 


### -field UsbdVersionInformation

A <a href="..\usb\ns-usb-_usbd_version_information.md">USBD_VERSION_INFORMATION</a> structure that provides version information for the host controller driver (HCD) and the USB specification version that the device supports.


### -field HcdPortCapabilities

This member is reserved for system use.


### -field Traits

A set of bit flags that identify device traits. The flags are defined by the <a href="..\wdfusb\ne-wdfusb-_wdf_usb_device_traits.md">WDF_USB_DEVICE_TRAITS</a> enumeration.


## -remarks


The <b>WDF_USB_DEVICE_INFORMATION</b> structure is filled in by the <a href="..\wdfusb\nf-wdfusb-wdfusbtargetdeviceretrieveinformation.md">WdfUsbTargetDeviceRetrieveInformation</a> method. Before calling <b>WdfUsbTargetDeviceRetrieveInformation</b>, the driver must call <a href="..\wdfusb\nf-wdfusb-wdf_usb_device_information_init.md">WDF_USB_DEVICE_INFORMATION_INIT</a> to initialize the structure.



## -see-also

<a href="..\wdfusb\ne-wdfusb-_wdf_usb_device_traits.md">WDF_USB_DEVICE_TRAITS</a>

<a href="..\usb\ns-usb-_usbd_version_information.md">USBD_VERSION_INFORMATION</a>

<a href="..\wdfusb\nf-wdfusb-wdf_usb_device_information_init.md">WDF_USB_DEVICE_INFORMATION_INIT</a>

<a href="..\wdfusb\nf-wdfusb-wdfusbtargetdeviceretrieveinformation.md">WdfUsbTargetDeviceRetrieveInformation</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_USB_DEVICE_INFORMATION structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

