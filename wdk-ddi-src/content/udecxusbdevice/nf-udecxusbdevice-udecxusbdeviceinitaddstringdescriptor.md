---
UID: NF:udecxusbdevice.UdecxUsbDeviceInitAddStringDescriptor
title: UdecxUsbDeviceInitAddStringDescriptor function (udecxusbdevice.h)
description: Adds a USB string descriptor to the initialization parameters used to create a virtual USB device.
old-location: buses\udecxusbdeviceinitaddstringdescriptor.htm
tech.root: usbref
ms.assetid: 05971A19-4B66-41F6-9043-DA9C81FA92E5
ms.date: 05/07/2018
ms.keywords: UdecxUsbDeviceInitAddStringDescriptor, UdecxUsbDeviceInitAddStringDescriptor function [Buses], buses.udecxusbdeviceinitaddstringdescriptor, udecxusbdevice/UdecxUsbDeviceInitAddStringDescriptor
ms.topic: function
req.header: udecxusbdevice.h
req.include-header: Udecx.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 1.15
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Udecxstub.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Udecxstub.lib
- Udecxstub.dll
api_name:
- UdecxUsbDeviceInitAddStringDescriptor
product:
- Windows
targetos: Windows
req.typenames: 
---

# UdecxUsbDeviceInitAddStringDescriptor function


## -description


Adds a USB string descriptor to the initialization parameters used to create a virtual USB device. 


## -parameters




### -param UdecxUsbDeviceInit [in, out]

A pointer to a WDF-allocated structure that contains initialization parameters for the virtual USB device.  The client driver retrieved this pointer in the previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/mt627968">UdecxUsbDeviceInitAllocate</a>. 


### -param String [in]

A Unicode string that contains the USB string descriptor to add to the device.


### -param DescriptorIndex [in]

The index of the descriptor.


### -param LanguageId [in]

The language identifier of the string. The client driver must define constants for the language support, such as:

<code>const USHORT US_ENGLISH = 0x409;
</code>


## -returns



The method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> error code. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt595932">Architecture: USB Device Emulation (UDE)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540156">USB String Descriptors</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt627968">UdecxUsbDeviceInitAllocate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt595939">Write a UDE client driver</a>
 

 

