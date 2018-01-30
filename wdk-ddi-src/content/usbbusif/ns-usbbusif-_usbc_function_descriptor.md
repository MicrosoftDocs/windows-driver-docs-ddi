---
UID: NS:usbbusif._USBC_FUNCTION_DESCRIPTOR
title: "_USBC_FUNCTION_DESCRIPTOR"
author: windows-driver-content
description: The USBC_FUNCTION_DESCRIPTOR structure describes a USB function and its associated interface collection.
old-location: buses\usbc_function_descriptor.htm
old-project: usbref
ms.assetid: 43ac738b-7837-4183-ad06-5c35a2af38ff
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: buses.usbc_function_descriptor, PUSBC_FUNCTION_DESCRIPTOR, USBC_FUNCTION_DESCRIPTOR structure [Buses], *PUSBC_FUNCTION_DESCRIPTOR, USBC_FUNCTION_DESCRIPTOR, usbbusif/USBC_FUNCTION_DESCRIPTOR, usbstrct_29623b3f-9def-4eb6-8735-eb695560ce27.xml, _USBC_FUNCTION_DESCRIPTOR, PUSBC_FUNCTION_DESCRIPTOR structure pointer [Buses], usbbusif/PUSBC_FUNCTION_DESCRIPTOR
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	usbbusif.h
apiname:
-	USBC_FUNCTION_DESCRIPTOR
product: Windows
targetos: Windows
req.typenames: USBC_FUNCTION_DESCRIPTOR, *PUSBC_FUNCTION_DESCRIPTOR
req.product: Windows 10 or later.
---

# _USBC_FUNCTION_DESCRIPTOR structure


## -description


The <b>USBC_FUNCTION_DESCRIPTOR</b> structure describes a USB function and its associated interface collection.


## -syntax


````
typedef struct _USBC_FUNCTION_DESCRIPTOR {
  UCHAR                     FunctionNumber;
  UCHAR                     NumberOfInterfaces;
  PUSB_INTERFACE_DESCRIPTOR *InterfaceDescriptorList;
  UNICODE_STRING            HardwareId;
  UNICODE_STRING            CompatibleId;
  UNICODE_STRING            FunctionDescription;
  ULONG                     FunctionFlags;
  PVOID                     Reserved;
} USBC_FUNCTION_DESCRIPTOR, *PUSBC_FUNCTION_DESCRIPTOR;
````


## -struct-fields




### -field FunctionNumber

The zero-based index of the interface collection.


### -field NumberOfInterfaces

The number of interfaces in the interface collection.


### -field InterfaceDescriptorList

An array of pointers to <a href="..\usbspec\ns-usbspec-_usb_interface_descriptor.md">USB_INTERFACE_DESCRIPTOR</a>-type structures that describe the interfaces in the interface collection.


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


For information on how to use user-defined callback routines to provide a custom definition of the interface collections on a device, see <a href="https://msdn.microsoft.com/3cf4e9f2-ea33-491f-94af-62d2afacc899">Customizing Enumeration of Interface Collections for Composite Devices</a>.



## -see-also

<a href="..\usbspec\ns-usbspec-_usb_interface_descriptor.md">USB_INTERFACE_DESCRIPTOR</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540160">USB Structures</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20USBC_FUNCTION_DESCRIPTOR structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

