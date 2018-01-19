---
UID: NF:udecxusbdevice.UdecxUsbDeviceSignalWake
title: UdecxUsbDeviceSignalWake function
author: windows-driver-content
description: Initiates wake up from a low link power state for a virtual USB 2.0 device.
old-location: buses\udecxusbdevicesignalwake.htm
old-project: usbref
ms.assetid: BF8C1D85-6C88-4F4C-ADDB-CCE603D420F2
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: UdecxUsbDeviceSignalWake
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
req.alt-api: UdecxUsbDeviceSignalWake
req.alt-loc: Udecxstub.lib,Udecxstub.dll
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
req.typenames: *PUDECX_USB_DEVICE_WAKE_SETTING, UDECX_USB_DEVICE_WAKE_SETTING
req.product: Windows 10 or later.
---

# UdecxUsbDeviceSignalWake function



## -description
Initiates wake up from a low link power state for a virtual USB 2.0 device.




## -syntax

````
void UdecxUsbDeviceSignalWake(
  _In_ UDECXUSBDEVICE UdecxUsbDevice
);
````


## -parameters

### -param UdecxUsbDevice [in]

A handle to UDE device object. The client driver retrieved this pointer in the previous call to <a href="..\udecxusbdevice\nf-udecxusbdevice-udecxusbdevicecreate.md">UdecxUsbDeviceCreate</a>.


## -returns
This function does not return a value.


## -remarks
The client driver for the device must have enabled wake capability in the most recent <a href="..\udecxusbdevice\nc-udecxusbdevice-evt_udecx_usb_device_d0_exit.md">EVT_UDECX_USB_DEVICE_D0_EXIT</a> call.



## -see-also
<dl>
<dt>
<a href="..\udecxusbdevice\nc-udecxusbdevice-evt_udecx_usb_device_d0_exit.md">EVT_UDECX_USB_DEVICE_D0_EXIT</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/mt595932">Architecture: USB Device Emulation (UDE)</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/mt595939">Write a UDE client driver</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UdecxUsbDeviceSignalWake function%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

