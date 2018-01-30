---
UID: NS:hidport._HID_DEVICE_ATTRIBUTES
title: "_HID_DEVICE_ATTRIBUTES"
author: windows-driver-content
description: The HID_DEVICE_ATTRIBUTES structure contains information about a HIDClass device.
old-location: hid\hid_device_attributes.htm
old-project: hid
ms.assetid: ba874c8a-b0df-475c-b34d-56ad0a3472db
ms.author: windowsdriverdev
ms.date: 12/21/2017
ms.keywords: hidstrct_2ba6111b-4231-40eb-9b08-0b3b396079d8.xml, HID_DEVICE_ATTRIBUTES structure [Human Input Devices], HID_DEVICE_ATTRIBUTES, *PHID_DEVICE_ATTRIBUTES, hidport/PHID_DEVICE_ATTRIBUTES, PHID_DEVICE_ATTRIBUTES, hid.hid_device_attributes, hidport/HID_DEVICE_ATTRIBUTES, PHID_DEVICE_ATTRIBUTES structure pointer [Human Input Devices], _HID_DEVICE_ATTRIBUTES
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	hidport.h
apiname:
-	HID_DEVICE_ATTRIBUTES
product: Windows
targetos: Windows
req.typenames: "*PHID_DEVICE_ATTRIBUTES, HID_DEVICE_ATTRIBUTES"
---

# _HID_DEVICE_ATTRIBUTES structure


## -description


The HID_DEVICE_ATTRIBUTES structure contains information about a HIDClass device.


## -syntax


````
typedef struct _HID_DEVICE_ATTRIBUTES {
  ULONG  Size;
  USHORT VendorID;
  USHORT ProductID;
  USHORT VersionNumber;
  USHORT Reserved[11];
} HID_DEVICE_ATTRIBUTES, *PHID_DEVICE_ATTRIBUTES;
````


## -struct-fields




### -field Size

Specifies the size of the structure. This member should be treated as read-only when a HID minidriver uses this structure to complete an <a href="..\hidport\ni-hidport-ioctl_hid_get_device_attributes.md">IOCTL_HID_GET_DEVICE_ATTRIBUTES</a> request.


### -field VendorID

Specifies a HID device's vendor ID.


### -field ProductID

Specifies a HID device's product ID.


### -field VersionNumber

Specifies the manufacturer's revision number for a HID device.


### -field Reserved

Reserved for internal system use.


## -remarks


The HID class driver uses this structure to obtain device attributes when it sends an <a href="..\hidport\ni-hidport-ioctl_hid_get_device_attributes.md">IOCTL_HID_GET_DEVICE_ATTRIBUTES</a> request to a HID minidriver.



## -see-also

<a href="..\hidport\ni-hidport-ioctl_hid_get_device_attributes.md">IOCTL_HID_GET_DEVICE_ATTRIBUTES</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [hid\hid]:%20HID_DEVICE_ATTRIBUTES structure%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

