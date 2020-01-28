---
UID: NS:usbfnbase._USBFN_CLASS_INTERFACE_EX
title: _USBFN_CLASS_INTERFACE_EX (usbfnbase.h)
description: Describes an interface and its endpoints.
old-location: buses\usbfn_class_interface_ex.htm
tech.root: usbref
ms.assetid: DEA417E7-FA4B-4F72-A03A-ECE921FC725C
ms.date: 05/07/2018
ms.keywords: "*PUSBFN_CLASS_INTERFACE_EX, PUSBFN_CLASS_INTERFACE_EX, PUSBFN_CLASS_INTERFACE_EX structure pointer [Buses], USBFN_CLASS_INTERFACE_EX, USBFN_CLASS_INTERFACE_EX structure [Buses], _USBFN_CLASS_INTERFACE_EX, buses.usbfn_class_interface_ex, usbfnbase/PUSBFN_CLASS_INTERFACE_EX, usbfnbase/USBFN_CLASS_INTERFACE_EX"
f1_keywords:
 - "usbfnbase/USBFN_CLASS_INTERFACE_EX"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- usbfnbase.h
api_name:
- USBFN_CLASS_INTERFACE_EX
product:
- Windows
targetos: Windows
req.typenames: USBFN_CLASS_INTERFACE_EX, *PUSBFN_CLASS_INTERFACE_EX
---

# _USBFN_CLASS_INTERFACE_EX structure


## -description


Describes an interface and its endpoints.


## -struct-fields




### -field BaseInterfaceNumber

The index number of the interface.


### -field InterfaceCount

The number of USB interfaces contained in  the selected function.


### -field PipeCount

The number of endpoints contained in  the interface.


### -field PipeArr

An array of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbfnbase/ns-usbfnbase-_usbfn_pipe_information">USBFN_PIPE_INFORMATION</a> structures that describes the endpoints in the interface.

