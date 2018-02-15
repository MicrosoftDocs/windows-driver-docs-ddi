---
UID: NF:udecxusbdevice.UdecxUsbDeviceInitAddDescriptor
title: UdecxUsbDeviceInitAddDescriptor function
author: windows-driver-content
description: Adds a USB descriptor to the initialization parameters used to create a virtual USB device.
old-location: buses\udecxusbdeviceinitadddescriptor.htm
old-project: usbref
ms.assetid: BC43B6AB-E34C-45A9-B666-1B323104FC48
ms.author: windowsdriverdev
ms.date: 2/8/2018
ms.keywords: buses.udecxusbdeviceinitadddescriptor, UdecxUsbDeviceInitAddDescriptor, UdecxUsbDeviceInitAddDescriptor function [Buses], udecxusbdevice/UdecxUsbDeviceInitAddDescriptor
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
-	UdecxUsbDeviceInitAddDescriptor
product: Windows
targetos: Windows
req.typenames: UDECX_USB_DEVICE_WAKE_SETTING, *PUDECX_USB_DEVICE_WAKE_SETTING
req.product: Windows 10 or later.
---

# UdecxUsbDeviceInitAddDescriptor function


## -description


Adds a USB descriptor to the initialization parameters used to create a virtual USB device.


## -syntax


````
FORCEINLINE NTSTATUS UdecxUsbDeviceInitAddDescriptor(
  _Inout_ PUDECXUSBDEVICE_INIT            UdecxUsbDeviceInit,
  _In_    reads_(DescriptorLength) PUCHAR Descriptor,
  _In_    USHORT                          DescriptorLength
);
````


## -parameters




### -param UdecxUsbDeviceInit [in, out]

A pointer to a WDF-allocated structure that contains initialization parameters for the virtual USB device.  The client driver retrieved this pointer in the previous call to <a href="..\udecxusbdevice\nf-udecxusbdevice-udecxusbdeviceinitallocate.md">UdecxUsbDeviceInitAllocate</a>. 


### -param Descriptor [in]

A caller-allocated buffer that contains the USB descriptor to add to the device.


### -param DescriptorLength [in]

The length of the descriptor buffer.


## -returns



The method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> error code. 




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/mt595939">Write a UDE client driver</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt595932">Architecture: USB Device Emulation (UDE)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn303349">Standard USB descriptors</a>



<a href="..\udecxusbdevice\nf-udecxusbdevice-udecxusbdeviceinitallocate.md">UdecxUsbDeviceInitAllocate</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UdecxUsbDeviceInitAddDescriptor function%20 RELEASE:%20(2/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

