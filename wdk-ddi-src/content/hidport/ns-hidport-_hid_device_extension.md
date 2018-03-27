---
UID: NS:hidport._HID_DEVICE_EXTENSION
title: "_HID_DEVICE_EXTENSION"
author: windows-driver-content
description: The HID_DEVICE_EXTENSION structure is used by a HID minidriver as its layout for the device extension of a HIDClass device's functional device object.
old-location: hid\hid_device_extension.htm
old-project: hid
ms.assetid: 409fbc3e-1221-4869-9087-693b1e4d4587
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PHID_DEVICE_EXTENSION, HID_DEVICE_EXTENSION, HID_DEVICE_EXTENSION structure [Human Input Devices], PHID_DEVICE_EXTENSION, PHID_DEVICE_EXTENSION structure pointer [Human Input Devices], _HID_DEVICE_EXTENSION, hid.hid_device_extension, hidport/HID_DEVICE_EXTENSION, hidport/PHID_DEVICE_EXTENSION, hidstrct_faf2bb84-b1f7-4cfa-84b0-5328dfb521dc.xml"
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
-	HID_DEVICE_EXTENSION
product: Windows
targetos: Windows
req.typenames: HID_DEVICE_EXTENSION, *PHID_DEVICE_EXTENSION
---

# _HID_DEVICE_EXTENSION structure


## -description


The HID_DEVICE_EXTENSION structure is used by a HID minidriver as its layout for the device extension of a HIDClass device's functional device object.


## -struct-fields




### -field PhysicalDeviceObject

Pointer to HID device's physical device object.


### -field NextDeviceObject

Pointer to the device object immediately below the functional device object in the HID device's device stack.


### -field MiniDeviceExtension

Pointer to the minidriver-specific portion of the device extension.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff539835">HidRegisterMinidriver</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [hid\hid]:%20HID_DEVICE_EXTENSION structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

