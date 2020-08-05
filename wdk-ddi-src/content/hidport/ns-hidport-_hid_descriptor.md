---
UID: NS:hidport._HID_DESCRIPTOR
title: _HID_DESCRIPTOR (hidport.h)
description: The HID_DESCRIPTOR structure represents a HID descriptor for a HIDClass device.
old-location: hid\hid_descriptor.htm
tech.root: hid
ms.assetid: 80a6a5d8-b13a-418d-a4bd-941d3a913c1e
ms.date: 04/30/2018
keywords: ["HID_DESCRIPTOR structure"]
ms.keywords: "*PHID_DESCRIPTOR, HID_DESCRIPTOR, HID_DESCRIPTOR structure [Human Input Devices], PHID_DESCRIPTOR, PHID_DESCRIPTOR structure pointer [Human Input Devices], _HID_DESCRIPTOR, hid.hid_descriptor, hidport/HID_DEVICE_ATTRIBUTES, hidport/PHID_DESCRIPTOR, hidstrct_07b2c0af-449d-484e-8aa8-9d7e3909d113.xml"
f1_keywords:
 - "hidport/HID_DESCRIPTOR"
 - "HID_DESCRIPTOR"
req.header: hidport.h
req.include-header: Hidport.h
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
- hidport.h
api_name:
- HID_DESCRIPTOR
targetos: Windows
req.typenames: HID_DESCRIPTOR, *PHID_DESCRIPTOR
---

# _HID_DESCRIPTOR structure


## -description


The HID_DESCRIPTOR structure represents a HID descriptor for a HIDClass device.


## -struct-fields




### -field bLength


### -field bDescriptorType


### -field bcdHID


### -field bCountry


### -field bNumDescriptors


### -field _HID_DESCRIPTOR_DESC_LIST

 


### -field _HID_DESCRIPTOR_DESC_LIST.bReportType

 


### -field _HID_DESCRIPTOR_DESC_LIST.wReportLength

 


### -field DescriptorList [1]


## -remarks



The HID class driver uses an <a href="https://docs.microsoft.com/previous-versions/hh439622(v=vs.85)">IOCTL_HID_GET_DEVICE_DESCRIPTOR</a> request to obtain a device's HID descriptor from a HID minidriver.

For information about HID descriptors, see the Universal Serial Bus (USB) standard<i> Device Class Definition for Human Interface Devices (HID)</i> located at the <a href="https://www.usb.org/">USB Implementers Forum website</a>.




## -see-also




<a href="https://docs.microsoft.com/previous-versions/hh439622(v=vs.85)">IOCTL_HID_GET_DEVICE_DESCRIPTOR</a>
 

 

