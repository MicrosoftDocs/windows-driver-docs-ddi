---
UID: NS:hidport._HID_DEVICE_ATTRIBUTES
title: "_HID_DEVICE_ATTRIBUTES"
author: windows-driver-content
description: The HID_DEVICE_ATTRIBUTES structure contains information about a HIDClass device.
old-location: hid\hid_device_attributes.htm
old-project: hid
ms.assetid: ba874c8a-b0df-475c-b34d-56ad0a3472db
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: "*PHID_DEVICE_ATTRIBUTES, HID_DEVICE_ATTRIBUTES, HID_DEVICE_ATTRIBUTES structure [Human Input Devices], PHID_DEVICE_ATTRIBUTES, PHID_DEVICE_ATTRIBUTES structure pointer [Human Input Devices], _HID_DEVICE_ATTRIBUTES, hid.hid_device_attributes, hidport/HID_DEVICE_ATTRIBUTES, hidport/PHID_DEVICE_ATTRIBUTES, hidstrct_2ba6111b-4231-40eb-9b08-0b3b396079d8.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	hidport.h
api_name:
-	HID_DEVICE_ATTRIBUTES
product: Windows
targetos: Windows
req.typenames: HID_DEVICE_ATTRIBUTES, *PHID_DEVICE_ATTRIBUTES
---

# _HID_DEVICE_ATTRIBUTES structure


## -description


The HID_DEVICE_ATTRIBUTES structure contains information about a HIDClass device.


## -struct-fields




### -field Size

Specifies the size of the structure. This member should be treated as read-only when a HID minidriver uses this structure to complete an <a href="https://msdn.microsoft.com/library/windows/hardware/ff541093">IOCTL_HID_GET_DEVICE_ATTRIBUTES</a> request.


### -field VendorID

Specifies a HID device's vendor ID.


### -field ProductID

Specifies a HID device's product ID.


### -field VersionNumber

Specifies the manufacturer's revision number for a HID device.


### -field Reserved

Reserved for internal system use.


## -remarks



The HID class driver uses this structure to obtain device attributes when it sends an <a href="https://msdn.microsoft.com/library/windows/hardware/ff541093">IOCTL_HID_GET_DEVICE_ATTRIBUTES</a> request to a HID minidriver.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541093">IOCTL_HID_GET_DEVICE_ATTRIBUTES</a>
 

 

