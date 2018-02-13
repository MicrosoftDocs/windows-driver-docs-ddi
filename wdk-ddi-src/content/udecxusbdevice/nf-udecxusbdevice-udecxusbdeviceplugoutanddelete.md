---
UID: NF:udecxusbdevice.UdecxUsbDevicePlugOutAndDelete
title: UdecxUsbDevicePlugOutAndDelete function
author: windows-driver-content
description: Disconnects the virtual USB device.
old-location: buses\udecxusbdeviceplugoutanddelete.htm
old-project: usbref
ms.assetid: 27816655-1FE9-44A0-81BB-59808FE6F064
ms.author: windowsdriverdev
ms.date: 2/8/2018
ms.keywords: udecxusbdevice/UdecxUsbDevicePlugOutAndDelete, UdecxUsbDevicePlugOutAndDelete function [Buses], buses.udecxusbdeviceplugoutanddelete, UdecxUsbDevicePlugOutAndDelete
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
-	UdecxUsbDevicePlugOutAndDelete
product: Windows
targetos: Windows
req.typenames: UDECX_USB_DEVICE_WAKE_SETTING, *PUDECX_USB_DEVICE_WAKE_SETTING
req.product: Windows 10 or later.
---

# UdecxUsbDevicePlugOutAndDelete function


## -description


Disconnects  the virtual USB device. 


## -syntax


````
NTSTATUS UdecxUsbDevicePlugOutAndDelete(
  _In_ UDECXUSBDEVICE UdecxUsbDevice
);
````


## -parameters




### -param UdecxUsbDevice [in]

A handle to UDE device object. The client driver retrieved this pointer in the previous call to <a href="..\udecxusbdevice\nf-udecxusbdevice-udecxusbdevicecreate.md">UdecxUsbDeviceCreate</a>.


## -returns



The method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> error code. 




## -remarks



If the USB device needs to be removed at runtime, the client driver can call this method to indicate a disconnect event. After this call completes, the client driver can no longer use the device specified by the UdecxUsbDevice parameter; it must create another device by calling <a href="..\udecxusbdevice\nf-udecxusbdevice-udecxusbdevicecreate.md">UdecxUsbDeviceCreate</a>. 





## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/mt595932">Architecture: USB Device Emulation (UDE)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt595939">Write a UDE client driver</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UdecxUsbDevicePlugOutAndDelete function%20 RELEASE:%20(2/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

