---
UID: NF:udecxusbdevice.UdecxUsbDeviceInitAllocate
title: UdecxUsbDeviceInitAllocate function
author: windows-driver-content
description: Allocates memory for a UDECXUSBDEVICE_INIT structure that is used to initialize a virtual USB device.
old-location: buses\udecxusbdeviceinitallocate.htm
old-project: usbref
ms.assetid: 127D132B-6A40-4F6F-BCDA-473F89A1A747
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: UdecxUsbDeviceInitAllocate, UdecxUsbDeviceInitAllocate function [Buses], buses.udecxusbdeviceinitallocate, udecxusbdevice/UdecxUsbDeviceInitAllocate
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
-	UdecxUsbDeviceInitAllocate
product: Windows
targetos: Windows
req.typenames: UDECX_USB_DEVICE_WAKE_SETTING, *PUDECX_USB_DEVICE_WAKE_SETTING
req.product: Windows 10 or later.
---

# UdecxUsbDeviceInitAllocate function


## -description


Allocates memory for a  <b>UDECXUSBDEVICE_INIT</b> structure that is used to initialize a virtual USB device.


## -syntax


````
FORCEINLINE PUDECXUSBDEVICE_INIT UdecxUsbDeviceInitAllocate(
  _In_ WDFDEVICE UdecxWdfDevice
);
````


## -parameters




### -param UdecxWdfDevice [in]

A handle to a framework device object that represents the a USB device. The client driver initialized this object in the previous call to <a href="..\udecxwdfdevice\nf-udecxwdfdevice-udecxwdfdeviceaddusbdeviceemulation.md">UdecxWdfDeviceAddUsbDeviceEmulation</a>.


## -returns


This method returns a pointer to an opaque <b>UDECXUSBDEVICE_INIT</b> that contains the initialization parameters. The structure is allocated by the USB device emulation  class extension (UdeCx).



## -remarks


The UDE client driver calls this method to allocate parameters for the virtual device that is created by a subsequent call to <a href="..\udecxusbdevice\nf-udecxusbdevice-udecxusbdevicecreate.md">UdecxUsbDeviceCreate</a>. If the device is not created or the driver is finished using the resources, the driver must free the resources by calling <a href="..\udecxusbdevice\nf-udecxusbdevice-udecxusbdeviceinitfree.md">UdecxUsbDeviceInitFree</a>.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/mt595932">Architecture: USB Device Emulation (UDE)</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/mt595939">Write a UDE client driver</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UdecxUsbDeviceInitAllocate function%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

