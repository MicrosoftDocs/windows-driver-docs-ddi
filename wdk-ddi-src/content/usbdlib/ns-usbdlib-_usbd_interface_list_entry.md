---
UID: NS:usbdlib._USBD_INTERFACE_LIST_ENTRY
title: "_USBD_INTERFACE_LIST_ENTRY"
author: windows-driver-content
description: The USBD_INTERFACE_LIST_ENTRY structure is used by USB client drivers to create an array of interfaces to be inserted into a configuration request.
old-location: buses\usbd_interface_list_entry.htm
old-project: usbref
ms.assetid: 9b729c52-b03b-4b53-ae1a-9a025585ba7b
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , *, *PUSBD_INTERFACE_LIST_ENTRY, ,, A, B, C, D, E, F, I, L, N, P, PUSBD_INTERFACE_LIST_ENTRY, PUSBD_INTERFACE_LIST_ENTRY structure pointer [Buses], R, S, T, U, USBD_INTERFACE_LIST_ENTRY, USBD_INTERFACE_LIST_ENTRY structure [Buses], Y, _, _USBD_INTERFACE_LIST_ENTRY, buses.usbd_interface_list_entry, usbdlib/PUSBD_INTERFACE_LIST_ENTRY, usbdlib/USBD_INTERFACE_LIST_ENTRY, usbstrct_f42a04be-c6c2-44c6-ae18-725929020420.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	usbdlib.h
apiname:
-	USBD_INTERFACE_LIST_ENTRY
product: Windows
targetos: Windows
req.typenames: USBD_INTERFACE_LIST_ENTRY, *PUSBD_INTERFACE_LIST_ENTRY
req.product: Windows 10 or later.
---

# _USBD_INTERFACE_LIST_ENTRY structure


## -description


The <b>USBD_INTERFACE_LIST_ENTRY</b> structure is used by USB client drivers to create an array of interfaces to be inserted into a configuration request.


## -syntax


````
typedef struct _USBD_INTERFACE_LIST_ENTRY {
  PUSB_INTERFACE_DESCRIPTOR   InterfaceDescriptor;
  PUSBD_INTERFACE_INFORMATION Interface;
} USBD_INTERFACE_LIST_ENTRY, *PUSBD_INTERFACE_LIST_ENTRY;
````


## -struct-fields




### -field InterfaceDescriptor

Pointer to a <a href="..\usbspec\ns-usbspec-_usb_interface_descriptor.md">USB_INTERFACE_DESCRIPTOR</a> structure that describes the interface to be added to the configuration request.


### -field Interface

Pointer to a <a href="..\usb\ns-usb-_usbd_interface_information.md">USBD_INTERFACE_INFORMATION</a> structure that describes the properties and settings of the interface pointed to by <i>InterfaceDescriptor</i>.


## -remarks



This structure is used by USB clients with the routine <a href="..\usbdlib\nf-usbdlib-usbd_createconfigurationrequestex.md">USBD_CreateConfigurationRequestEx</a>. Clients allocate an array of these structures, one for each interface to be configured. Clients must also allocate a <b>NULL</b> entry in the array to be used as a terminator before calling <b>USBD_CreateConfigurationRequestEx</b>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540160">USB Structures</a>



<a href="..\usbdlib\nf-usbdlib-usbd_createconfigurationrequestex.md">USBD_CreateConfigurationRequestEx</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20USBD_INTERFACE_LIST_ENTRY structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

