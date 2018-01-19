---
UID: NF:udecxusbdevice.UdecxUsbDeviceLinkPowerEntryComplete
title: UdecxUsbDeviceLinkPowerEntryComplete function
author: windows-driver-content
description: Completes an asynchronous request for bringing the device out of a low power state.
old-location: buses\udecxusbdevicelinkpowerentrycomplete.htm
old-project: usbref
ms.assetid: 0B8FF9EB-63E5-4532-B13C-CF0FF04D9A53
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: UdecxUsbDeviceLinkPowerEntryComplete
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
req.alt-api: UdecxUsbDeviceLinkPowerEntryComplete
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

# UdecxUsbDeviceLinkPowerEntryComplete function



## -description
Completes an asynchronous request for bringing the device out of a low power state.  



## -syntax

````
void UdecxUsbDeviceLinkPowerEntryComplete(
  _In_ UDECXUSBDEVICE UdecxUsbDevice,
  _In_ NTSTATUS       CompletionStatus
);
````


## -parameters

### -param UdecxUsbDevice [in]

A handle to UDE device object. The client driver retrieved this pointer in the previous call to <a href="..\udecxusbdevice\nf-udecxusbdevice-udecxusbdevicecreate.md">UdecxUsbDeviceCreate</a>.


### -param CompletionStatus [in]

An appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> error code that indicates the success or failure of the asynchronous operation.


## -returns
This function does not return a value.


## -remarks
When the USB device emulation class extension (UdeCx) gets a request to bring the device from low power state and enter working state, it invokes the client driver's implementation of the <a href="..\udecxusbdevice\nc-udecxusbdevice-evt_udecx_usb_device_d0_entry.md">EVT_UDECX_USB_DEVICE_D0_ENTRY</a> callback function. 

After the client driver has performed the necessary steps for bringing the virtual USB device to working state, the driver calls this method to notify the class extension that it has completed the power request.


## -see-also
<dl>
<dt>
<a href="..\udecxusbdevice\nc-udecxusbdevice-evt_udecx_usb_device_d0_entry.md">EVT_UDECX_USB_DEVICE_D0_ENTRY</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/mt595932">Architecture: USB Device Emulation (UDE)</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/mt595939">Write a UDE client driver</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UdecxUsbDeviceLinkPowerEntryComplete function%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

