---
UID: NF:udecxusbdevice.UdecxUsbDevicePlugOutAndDelete
title: UdecxUsbDevicePlugOutAndDelete function (udecxusbdevice.h)
description: Disconnects the virtual USB device.
old-location: buses\udecxusbdeviceplugoutanddelete.htm
tech.root: usbref
ms.assetid: 27816655-1FE9-44A0-81BB-59808FE6F064
ms.date: 05/07/2018
ms.keywords: UdecxUsbDevicePlugOutAndDelete, UdecxUsbDevicePlugOutAndDelete function [Buses], buses.udecxusbdeviceplugoutanddelete, udecxusbdevice/UdecxUsbDevicePlugOutAndDelete
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
- UdecxUsbDevicePlugOutAndDelete
product:
- Windows
targetos: Windows
req.typenames: 
---

# UdecxUsbDevicePlugOutAndDelete function


## -description


Disconnects  the virtual USB device. 


## -parameters




### -param UdecxUsbDevice [in]

A handle to UDE device object. The client driver retrieved this pointer in the previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/mt595959">UdecxUsbDeviceCreate</a>.


## -returns



The method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> error code. 




## -remarks



If the USB device needs to be removed at runtime, the client driver can call this method to indicate a disconnect event. After this call completes, the client driver can no longer use the device specified by the UdecxUsbDevice parameter; it must create another device by calling <a href="https://msdn.microsoft.com/library/windows/hardware/mt595959">UdecxUsbDeviceCreate</a>. 





## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt595932">Architecture: USB Device Emulation (UDE)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt595939">Write a UDE client driver</a>
 

 

