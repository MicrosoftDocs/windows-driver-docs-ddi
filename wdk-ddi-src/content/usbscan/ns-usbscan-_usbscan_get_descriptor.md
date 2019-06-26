---
UID: NS:usbscan._USBSCAN_GET_DESCRIPTOR
title: _USBSCAN_GET_DESCRIPTOR (usbscan.h)
description: The USBSCAN_GET_DESCRIPTOR structure is used as a parameter to DeviceIoControl, when the specified I/O control code is IOCTL_GET_USB_DESCRIPTOR.
old-location: image\usbscan_get_descriptor.htm
tech.root: image
ms.assetid: 250c0022-ceaa-40c6-8431-9ec53438fdb9
ms.date: 05/03/2018
ms.keywords: "*PUSBSCAN_GET_DESCRIPTOR, PUSBSCAN_GET_DESCRIPTOR, PUSBSCAN_GET_DESCRIPTOR structure pointer [Imaging Devices], USBSCAN_GET_DESCRIPTOR, USBSCAN_GET_DESCRIPTOR structure [Imaging Devices], _USBSCAN_GET_DESCRIPTOR, image.usbscan_get_descriptor, stifnc_1e92e306-420d-47ec-bb8a-8c906c3b62ea.xml, usbscan/PUSBSCAN_GET_DESCRIPTOR, usbscan/USBSCAN_GET_DESCRIPTOR"
ms.topic: struct
req.header: usbscan.h
req.include-header: Usbscan.h
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- usbscan.h
api_name:
- USBSCAN_GET_DESCRIPTOR
product:
- Windows
targetos: Windows
req.typenames: USBSCAN_GET_DESCRIPTOR, *PUSBSCAN_GET_DESCRIPTOR
---

# _USBSCAN_GET_DESCRIPTOR structure


## -description


The USBSCAN_GET_DESCRIPTOR structure is used as a parameter to <a href="https://docs.microsoft.com/windows/desktop/api/ioapiset/nf-ioapiset-deviceiocontrol">DeviceIoControl</a>, when the specified I/O control code is <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/usbscan/ni-usbscan-ioctl_get_usb_descriptor">IOCTL_GET_USB_DESCRIPTOR</a>.


## -struct-fields




### -field DescriptorType

Same as the <i>DescriptorType</i> parameter to <a href="https://docs.microsoft.com/previous-versions/ff538943(v=vs.85)">UsbBuildGetDescriptorRequest</a>.


### -field Index

Same as the <i>Index</i> parameter to <b>UsbBuildGetDescriptorRequest</b>.


### -field LanguageId

Same as the <i>LanguageId</i> parameter to <b>UsbBuildGetDescriptorRequest</b>.

