---
UID: NS:usbfnbase._USBFN_CLASS_INTERFACE
title: _USBFN_CLASS_INTERFACE (usbfnbase.h)
description: Describes an interface and its endpoints.
old-location: buses\usbfn_class_interface.htm
tech.root: usbref
ms.assetid: D7173157-D532-4E71-A4E5-55A3B9626DB8
ms.date: 05/07/2018
keywords: ["USBFN_CLASS_INTERFACE structure"]
ms.keywords: "*PUSBFN_CLASS_INTERFACE, PUSBFN_CLASS_INTERFACE, PUSBFN_CLASS_INTERFACE structure pointer [Buses], USBFN_CLASS_INTERFACE, USBFN_CLASS_INTERFACE structure [Buses], _USBFN_CLASS_INTERFACE, buses.usbfn_class_interface, usbfnbase/PUSBFN_CLASS_INTERFACE, usbfnbase/USBFN_CLASS_INTERFACE"
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
req.typenames: USBFN_CLASS_INTERFACE, *PUSBFN_CLASS_INTERFACE
f1_keywords:
 - _USBFN_CLASS_INTERFACE
 - usbfnbase/_USBFN_CLASS_INTERFACE
 - PUSBFN_CLASS_INTERFACE
 - usbfnbase/PUSBFN_CLASS_INTERFACE
 - USBFN_CLASS_INTERFACE
 - usbfnbase/USBFN_CLASS_INTERFACE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - usbfnbase.h
api_name:
 - USBFN_CLASS_INTERFACE
---

# _USBFN_CLASS_INTERFACE structure


## -description

Describes an interface and its endpoints.

## -struct-fields

### -field InterfaceNumber

The index number of the interface.

### -field PipeCount

The number of endpoints contained in  the interface.

### -field PipeArr

An array of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbfnbase/ns-usbfnbase-_usbfn_pipe_information">USBFN_PIPE_INFORMATION</a> structures that describes the endpoints in the interface.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbfnbase/ns-usbfnbase-_usbfn_pipe_information">USBFN_PIPE_INFORMATION</a>

