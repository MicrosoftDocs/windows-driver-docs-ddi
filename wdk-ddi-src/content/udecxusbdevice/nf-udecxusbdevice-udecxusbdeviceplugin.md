---
UID: NF:udecxusbdevice.UdecxUsbDevicePlugIn
title: UdecxUsbDevicePlugIn function
author: windows-driver-content
description: Notifies the USB device emulation class extension (UdeCx) that the USB device has been plugged in the specified port.
old-location: buses\udecxusbdeviceplugin.htm
tech.root: usbref
ms.assetid: 6F1A1545-5B64-4481-B795-0B6433304C06
ms.author: windowsdriverdev
ms.date: 5/7/2018
ms.keywords: UdecxUsbDevicePlugIn, UdecxUsbDevicePlugIn function [Buses], buses.udecxusbdeviceplugin, udecxusbdevice/UdecxUsbDevicePlugIn
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Udecxstub.lib
-	Udecxstub.dll
api_name:
-	UdecxUsbDevicePlugIn
product:
- Windows
targetos: Windows
req.typenames: 
---

# UdecxUsbDevicePlugIn function


## -description


Notifies the USB device emulation class extension (UdeCx) that the USB device has been plugged in the specified port.


## -parameters




### -param UdecxUsbDevice [in]

A handle to UDE device object. The client driver retrieved this pointer in the previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/mt595959">UdecxUsbDeviceCreate</a>.


### -param Options [in]

A <a href="https://msdn.microsoft.com/library/windows/hardware/mt627998">UDECX_USB_DEVICE_PLUG_IN_OPTIONS</a>-type value that indicates the port to which the device is plugged. At most one of Usb20PortNumber, Usb30PortNumber can be non-zero. NULL disables plug-in options (use defaults).



## -returns



The method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> error code. 




## -remarks



After the client driver calls this method, the class extension sends I/O requests and invokes callback functions on the endpoints and the device. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt595932">Architecture: USB Device Emulation (UDE)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt595939">Write a UDE client driver</a>
 

 

