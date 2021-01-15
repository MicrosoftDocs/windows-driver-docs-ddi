---
UID: NS:usbdlib._USBD_INTERFACE_LIST_ENTRY
title: _USBD_INTERFACE_LIST_ENTRY (usbdlib.h)
description: The USBD_INTERFACE_LIST_ENTRY structure is used by USB client drivers to create an array of interfaces to be inserted into a configuration request.
old-location: buses\usbd_interface_list_entry.htm
tech.root: usbref
ms.date: 05/07/2018
keywords: ["USBD_INTERFACE_LIST_ENTRY structure"]
ms.keywords: "*PUSBD_INTERFACE_LIST_ENTRY, PUSBD_INTERFACE_LIST_ENTRY, PUSBD_INTERFACE_LIST_ENTRY structure pointer [Buses], USBD_INTERFACE_LIST_ENTRY, USBD_INTERFACE_LIST_ENTRY structure [Buses], _USBD_INTERFACE_LIST_ENTRY, buses.usbd_interface_list_entry, usbdlib/PUSBD_INTERFACE_LIST_ENTRY, usbdlib/USBD_INTERFACE_LIST_ENTRY, usbstrct_f42a04be-c6c2-44c6-ae18-725929020420.xml"
req.header: usbdlib.h
req.include-header: Usbdlib.h
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
req.typenames: USBD_INTERFACE_LIST_ENTRY, *PUSBD_INTERFACE_LIST_ENTRY
f1_keywords:
 - _USBD_INTERFACE_LIST_ENTRY
 - usbdlib/_USBD_INTERFACE_LIST_ENTRY
 - PUSBD_INTERFACE_LIST_ENTRY
 - usbdlib/PUSBD_INTERFACE_LIST_ENTRY
 - USBD_INTERFACE_LIST_ENTRY
 - usbdlib/USBD_INTERFACE_LIST_ENTRY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - usbdlib.h
api_name:
 - _USBD_INTERFACE_LIST_ENTRY
 - PUSBD_INTERFACE_LIST_ENTRY
 - USBD_INTERFACE_LIST_ENTRY
---

# _USBD_INTERFACE_LIST_ENTRY structure


## -description

The <b>USBD_INTERFACE_LIST_ENTRY</b> structure is used by USB client drivers to create an array of interfaces to be inserted into a configuration request.

## -struct-fields

### -field InterfaceDescriptor

Pointer to a <a href="/windows-hardware/drivers/ddi/usbspec/ns-usbspec-_usb_interface_descriptor">USB_INTERFACE_DESCRIPTOR</a> structure that describes the interface to be added to the configuration request.

### -field Interface

Pointer to a <a href="/windows-hardware/drivers/ddi/usb/ns-usb-_usbd_interface_information">USBD_INTERFACE_INFORMATION</a> structure that describes the properties and settings of the interface pointed to by <i>InterfaceDescriptor</i>.

## -remarks

This structure is used by USB clients with the routine <a href="/windows-hardware/drivers/ddi/usbdlib/nf-usbdlib-usbd_createconfigurationrequestex">USBD_CreateConfigurationRequestEx</a>. Clients allocate an array of these structures, one for each interface to be configured. Clients must also allocate a <b>NULL</b> entry in the array to be used as a terminator before calling <b>USBD_CreateConfigurationRequestEx</b>.

## -see-also

<a href="/windows-hardware/drivers/ddi/_usbref/#structures">USB Structures</a>



<a href="/windows-hardware/drivers/ddi/usbdlib/nf-usbdlib-usbd_createconfigurationrequestex">USBD_CreateConfigurationRequestEx</a>

