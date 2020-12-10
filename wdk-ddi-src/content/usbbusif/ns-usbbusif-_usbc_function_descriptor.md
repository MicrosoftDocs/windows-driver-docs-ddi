---
UID: NS:usbbusif._USBC_FUNCTION_DESCRIPTOR
title: _USBC_FUNCTION_DESCRIPTOR (usbbusif.h)
description: The USBC_FUNCTION_DESCRIPTOR structure describes a USB function and its associated interface collection.
old-location: buses\usbc_function_descriptor.htm
tech.root: usbref
ms.date: 05/07/2018
keywords: ["USBC_FUNCTION_DESCRIPTOR structure"]
ms.keywords: "*PUSBC_FUNCTION_DESCRIPTOR, PUSBC_FUNCTION_DESCRIPTOR, PUSBC_FUNCTION_DESCRIPTOR structure pointer [Buses], USBC_FUNCTION_DESCRIPTOR, USBC_FUNCTION_DESCRIPTOR structure [Buses], _USBC_FUNCTION_DESCRIPTOR, buses.usbc_function_descriptor, usbbusif/PUSBC_FUNCTION_DESCRIPTOR, usbbusif/USBC_FUNCTION_DESCRIPTOR, usbstrct_29623b3f-9def-4eb6-8735-eb695560ce27.xml"
req.header: usbbusif.h
req.include-header: Usbbusif.h
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
req.typenames: USBC_FUNCTION_DESCRIPTOR, *PUSBC_FUNCTION_DESCRIPTOR
f1_keywords:
 - _USBC_FUNCTION_DESCRIPTOR
 - usbbusif/_USBC_FUNCTION_DESCRIPTOR
 - PUSBC_FUNCTION_DESCRIPTOR
 - usbbusif/PUSBC_FUNCTION_DESCRIPTOR
 - USBC_FUNCTION_DESCRIPTOR
 - usbbusif/USBC_FUNCTION_DESCRIPTOR
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - usbbusif.h
api_name:
 - USBC_FUNCTION_DESCRIPTOR
---

# _USBC_FUNCTION_DESCRIPTOR structure


## -description

The <b>USBC_FUNCTION_DESCRIPTOR</b> structure describes a USB function and its associated interface collection.

## -struct-fields

### -field FunctionNumber

The zero-based index of the interface collection.

### -field NumberOfInterfaces

The number of interfaces in the interface collection.

### -field InterfaceDescriptorList

An array of pointers to <a href="/windows-hardware/drivers/ddi/usbspec/ns-usbspec-_usb_interface_descriptor">USB_INTERFACE_DESCRIPTOR</a>-type structures that describe the interfaces in the interface collection.

### -field HardwareId

The hardware identifier of the interface collection.

### -field CompatibleId

The compatible identifier of the interface collection.

### -field FunctionDescription

A description of the interface collection in human-readable text.

### -field FunctionFlags

Vendor-defined flags that describe the interface collection.

### -field Reserved

Reserved.

## -remarks

For information on how to use user-defined callback routines to provide a custom definition of the interface collections on a device, see <a href="/windows-hardware/drivers/ddi/index">Customizing Enumeration of Interface Collections for Composite Devices</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/_usbref/#structures">USB Structures</a>



<a href="/windows-hardware/drivers/ddi/usbspec/ns-usbspec-_usb_interface_descriptor">USB_INTERFACE_DESCRIPTOR</a>
