---
UID: NS:usbfnbase._USBFN_INTERFACE_INFO
title: _USBFN_INTERFACE_INFO (usbfnbase.h)
description: Learn how USBFN_INTERFACE_INFO describes an interface and its endpoints.
old-location: buses\usbfn_interface_info.htm
tech.root: usbref
ms.date: 05/07/2018
keywords: ["USBFN_INTERFACE_INFO structure"]
ms.keywords: "*PUSBFN_INTERFACE_INFO, PUSBFN_INTERFACE_INFO, PUSBFN_INTERFACE_INFO structure pointer [Buses], USBFN_INTERFACE_INFO, USBFN_INTERFACE_INFO structure [Buses], _USBFN_INTERFACE_INFO, buses.usbfn_interface_info, usbfnbase/PUSBFN_INTERFACE_INFO, usbfnbase/USBFN_INTERFACE_INFO"
req.header: usbfnbase.h
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
targetos: Windows
req.typenames: USBFN_INTERFACE_INFO, *PUSBFN_INTERFACE_INFO
f1_keywords:
 - _USBFN_INTERFACE_INFO
 - usbfnbase/_USBFN_INTERFACE_INFO
 - PUSBFN_INTERFACE_INFO
 - usbfnbase/PUSBFN_INTERFACE_INFO
 - USBFN_INTERFACE_INFO
 - usbfnbase/USBFN_INTERFACE_INFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - usbfnbase.h
api_name:
 - _USBFN_INTERFACE_INFO
 - PUSBFN_INTERFACE_INFO
 - USBFN_INTERFACE_INFO
---

# _USBFN_INTERFACE_INFO structure


## -description

Describes an interface and its endpoints.

## -struct-fields

### -field InterfaceNumber

The index number of the interface.

### -field Speed

The operating bus speed indicated by <a href="/windows-hardware/drivers/ddi/usbfnbase/ne-usbfnbase-_usbfn_bus_speed">USBFN_BUS_SPEED</a>-typed flags.

### -field Size

Specifies the total length, in bytes, of all data for the interface.

### -field InterfaceDescriptorSet

Pointer to the first element in the array of that contains the interface descriptor set.

## -see-also

<a href="/windows-hardware/drivers/ddi/usbfnbase/ne-usbfnbase-_usbfn_bus_speed">USBFN_BUS_SPEED</a>

