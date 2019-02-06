---
UID: NS:hidclass._HID_COLLECTION_INFORMATION
title: _HID_COLLECTION_INFORMATION (hidclass.h)
description: The HID_COLLECTION_INFORMATION structure contains general information about a top-level collection.
old-location: hid\hid_collection_information.htm
tech.root: hid
ms.assetid: 47490858-3fe0-4a94-adae-6589cad6a842
ms.date: 04/30/2018
ms.keywords: "*PHID_COLLECTION_INFORMATION, HID_COLLECTION_INFORMATION, HID_COLLECTION_INFORMATION structure [Human Input Devices], PHID_COLLECTION_INFORMATION, PHID_COLLECTION_INFORMATION structure pointer [Human Input Devices], _HID_COLLECTION_INFORMATION, hid.hid_collection_information, hidclass/HID_COLLECTION_INFORMATION, hidclass/PHID_COLLECTION_INFORMATION, hidstrct_d61a583e-66c7-4851-ba75-3e5973a95c70.xml"
ms.topic: struct
req.header: hidclass.h
req.include-header: Hidclass.h
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
-	hidclass.h
api_name:
-	HID_COLLECTION_INFORMATION
product:
- Windows
targetos: Windows
req.typenames: HID_COLLECTION_INFORMATION, *PHID_COLLECTION_INFORMATION
---

# _HID_COLLECTION_INFORMATION structure


## -description


The HID_COLLECTION_INFORMATION structure contains general information about a <a href="https://msdn.microsoft.com/dcbee8e3-d03a-45c8-92e4-0897b9f55177">top-level collection</a>.


## -struct-fields




### -field DescriptorSize

Specifies the size, in bytes, of a collection's <a href="https://msdn.microsoft.com/50ac2877-4c45-4d55-b5cc-013486892fbf">preparsed data</a>.


### -field Polled

Indicates, if <b>TRUE</b>, that the HID class driver must poll the device to receive data. Otherwise, if <b>Polled</b> is <b>FALSE</b>, the device uses asynchronous interrupts to signal the host that the device has HID reports to send to the host.


### -field Reserved1

Reserved for internal system use.


### -field VendorID

Specifies a HID device's vendor ID.


### -field ProductID

Specifies a HID device's product ID.


### -field VersionNumber

Specifies the manufacturer's revision number for a HID device.


## -remarks



Kernel-mode drivers can use an <a href="https://msdn.microsoft.com/library/windows/hardware/ff541092">IOCTL_HID_GET_COLLECTION_INFORMATION</a> to obtain a collection's <b>HID_COLLECTION_INFORMATION</b> structure.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff539870">HID_COLLECTION_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541089">IOCTL_HID_GET_COLLECTION_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541092">IOCTL_HID_GET_COLLECTION_INFORMATION</a>
 

 

