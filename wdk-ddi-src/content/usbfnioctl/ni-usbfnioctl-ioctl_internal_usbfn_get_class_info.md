---
UID: NI:usbfnioctl.IOCTL_INTERNAL_USBFN_GET_CLASS_INFO
title: IOCTL_INTERNAL_USBFN_GET_CLASS_INFO (usbfnioctl.h)
description: The class driver sends this request IO control code to retrieve information about the available pipes for a device, as configured in the registry.
old-location: buses\ioctl_internal_usbfn_get_class_info.htm
tech.root: usbref
ms.assetid: 870D7D8C-B2FE-487A-9098-C004E6C7E159
ms.date: 05/07/2018
keywords: ["IOCTL_INTERNAL_USBFN_GET_CLASS_INFO IOCTL"]
ms.keywords: IOCTL_INTERNAL_USBFN_GET_CLASS_INFO, IOCTL_INTERNAL_USBFN_GET_CLASS_INFO control, IOCTL_INTERNAL_USBFN_GET_CLASS_INFO control code [Buses], buses.ioctl_internal_usbfn_get_class_info, usbfnioctl/IOCTL_INTERNAL_USBFN_GET_CLASS_INFO
f1_keywords:
 - "usbfnioctl/IOCTL_INTERNAL_USBFN_GET_CLASS_INFO"
 - "IOCTL_INTERNAL_USBFN_GET_CLASS_INFO"
req.header: usbfnioctl.h
req.include-header: 
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
- usbfnioctl.h
api_name:
- IOCTL_INTERNAL_USBFN_GET_CLASS_INFO
targetos: Windows
req.typenames: 
---

# IOCTL_INTERNAL_USBFN_GET_CLASS_INFO IOCTL


## -description


The class driver sends this request  IO control code to retrieve information about the available pipes for a device, as configured in the registry.


## -ioctlparameters




### -input-buffer

NULL.


### -input-buffer-length

None.


### -output-buffer

A pointer to a buffer that contains a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbfnbase/ns-usbfnbase-_usbfn_class_information_packet">USBFN_CLASS_INFORMATION_PACKET</a> structure. Upon completion, UFX populates the structure with the name, the device interface GUID, and details of the interface when operating at a particular bus speed.


### -output-buffer-length

The size of a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbfnbase/ns-usbfnbase-_usbfn_class_information_packet">USBFN_CLASS_INFORMATION_PACKET</a> structure.


### -in-out-buffer








### -inout-buffer-length








### -status-block

If the request is successful, the USB function class extension (UFX) returns STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise it returns a status value for which NT_SUCCESS(status) equals FALSE. 


## -remarks



The class driver should send this IOCTL request during initialization so that it can enumerate the endpoints and attributes.



