---
UID: NS:usbscan._USBSCAN_GET_DESCRIPTOR
title: "_USBSCAN_GET_DESCRIPTOR"
author: windows-driver-content
description: The USBSCAN_GET_DESCRIPTOR structure is used as a parameter to DeviceIoControl, when the specified I/O control code is IOCTL_GET_USB_DESCRIPTOR.
old-location: image\usbscan_get_descriptor.htm
old-project: image
ms.assetid: 250c0022-ceaa-40c6-8431-9ec53438fdb9
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: usbscan/PUSBSCAN_GET_DESCRIPTOR, stifnc_1e92e306-420d-47ec-bb8a-8c906c3b62ea.xml, USBSCAN_GET_DESCRIPTOR structure [Imaging Devices], USBSCAN_GET_DESCRIPTOR, PUSBSCAN_GET_DESCRIPTOR structure pointer [Imaging Devices], *PUSBSCAN_GET_DESCRIPTOR, image.usbscan_get_descriptor, _USBSCAN_GET_DESCRIPTOR, usbscan/USBSCAN_GET_DESCRIPTOR, PUSBSCAN_GET_DESCRIPTOR
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	usbscan.h
apiname:
-	USBSCAN_GET_DESCRIPTOR
product: Windows
targetos: Windows
req.typenames: "*PUSBSCAN_GET_DESCRIPTOR, USBSCAN_GET_DESCRIPTOR"
req.product: Windows 10 or later.
---

# _USBSCAN_GET_DESCRIPTOR structure


## -description


The USBSCAN_GET_DESCRIPTOR structure is used as a parameter to <a href="https://msdn.microsoft.com/1d35c087-6672-4fc6-baa1-a886dd9d3878">DeviceIoControl</a>, when the specified I/O control code is <a href="..\usbscan\ni-usbscan-ioctl_get_usb_descriptor.md">IOCTL_GET_USB_DESCRIPTOR</a>.


## -syntax


````
typedef struct _USBSCAN_GET_DESCRIPTOR {
  UCHAR  DescriptorType;
  UCHAR  Index;
  USHORT LanguageId;
} USBSCAN_GET_DESCRIPTOR, *PUSBSCAN_GET_DESCRIPTOR;
````


## -struct-fields




### -field DescriptorType

Same as the <i>DescriptorType</i> parameter to <a href="https://msdn.microsoft.com/library/windows/hardware/ff538943">UsbBuildGetDescriptorRequest</a>.


### -field Index

Same as the <i>Index</i> parameter to <b>UsbBuildGetDescriptorRequest</b>.


### -field LanguageId

Same as the <i>LanguageId</i> parameter to <b>UsbBuildGetDescriptorRequest</b>.

