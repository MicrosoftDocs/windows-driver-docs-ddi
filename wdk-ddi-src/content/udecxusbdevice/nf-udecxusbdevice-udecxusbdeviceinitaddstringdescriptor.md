---
UID: NF:udecxusbdevice.UdecxUsbDeviceInitAddStringDescriptor
title: UdecxUsbDeviceInitAddStringDescriptor function
author: windows-driver-content
description: Adds a USB string descriptor to the initialization parameters used to create a virtual USB device.
old-location: buses\udecxusbdeviceinitaddstringdescriptor.htm
old-project: usbref
ms.assetid: 05971A19-4B66-41F6-9043-DA9C81FA92E5
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: UdecxUsbDeviceInitAddStringDescriptor, UdecxUsbDeviceInitAddStringDescriptor function [Buses], buses.udecxusbdeviceinitaddstringdescriptor, udecxusbdevice/UdecxUsbDeviceInitAddStringDescriptor
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Udecxstub.lib
-	Udecxstub.dll
apiname:
-	UdecxUsbDeviceInitAddStringDescriptor
product: Windows
targetos: Windows
req.typenames: UDECX_USB_DEVICE_WAKE_SETTING, *PUDECX_USB_DEVICE_WAKE_SETTING
req.product: Windows 10 or later.
---

# UdecxUsbDeviceInitAddStringDescriptor function


## -description


Adds a USB string descriptor to the initialization parameters used to create a virtual USB device. 


## -syntax


````
NTSTATUS UdecxUsbDeviceInitAddStringDescriptor(
  _Inout_ PUDECXUSBDEVICE_INIT UdecxUsbDeviceInit,
  _In_    PCUNICODE_STRING     String,
  _In_    UCHAR                DescriptorIndex,
  _In_    USHORT               LanguageId
);
````


## -parameters




### -param UdecxUsbDeviceInit [in, out]

A pointer to a WDF-allocated structure that contains initialization parameters for the virtual USB device.  The client driver retrieved this pointer in the previous call to <a href="..\udecxusbdevice\nf-udecxusbdevice-udecxusbdeviceinitallocate.md">UdecxUsbDeviceInitAllocate</a>. 


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

<a href="https://msdn.microsoft.com/library/windows/hardware/mt595939">Write a UDE client driver</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540156">USB String Descriptors</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt595932">Architecture: USB Device Emulation (UDE)</a>



<a href="..\udecxusbdevice\nf-udecxusbdevice-udecxusbdeviceinitallocate.md">UdecxUsbDeviceInitAllocate</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UdecxUsbDeviceInitAddStringDescriptor function%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

