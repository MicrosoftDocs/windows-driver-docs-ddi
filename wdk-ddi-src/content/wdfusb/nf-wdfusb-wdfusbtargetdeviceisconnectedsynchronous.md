---
UID: NF:wdfusb.WdfUsbTargetDeviceIsConnectedSynchronous
title: WdfUsbTargetDeviceIsConnectedSynchronous function
author: windows-driver-content
description: The WdfUsbTargetDeviceIsConnectedSynchronous method determines if the specified USB device is connected.
old-location: wdf\wdfusbtargetdeviceisconnectedsynchronous.htm
old-project: wdf
ms.assetid: 1e598f83-01ad-4c3e-8044-a66041f6ad96
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WdfUsbTargetDeviceIsConnectedSynchronous
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfusb.h
req.include-header: Wdfusb.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.alt-api: WdfUsbTargetDeviceIsConnectedSynchronous
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2, UsbKmdfIrql, UsbKmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: PASSIVE_LEVEL
req.typenames: *PWDF_USB_REQUEST_TYPE, WDF_USB_REQUEST_TYPE
req.product: Windows 10 or later.
---

# WdfUsbTargetDeviceIsConnectedSynchronous function



## -description
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfUsbTargetDeviceIsConnectedSynchronous</b> method determines if the specified USB device is connected.



## -syntax

````
NTSTATUS WdfUsbTargetDeviceIsConnectedSynchronous(
  _In_ WDFUSBDEVICE UsbDevice
);
````


## -parameters

### -param UsbDevice [in]

A handle to a USB device object that was obtained from a previous call to <a href="..\wdfusb\nf-wdfusb-wdfusbtargetdevicecreatewithparameters.md">WdfUsbTargetDeviceCreateWithParameters</a>.


## -returns
<b>WdfUsbTargetDeviceIsConnectedSynchronous</b> returns the I/O target's completion status value if the operation succeeds. Otherwise, this method can return one of the following values:
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>An invalid parameter was detected.
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>The caller's IRQL was invalid.
<dl>
<dt><b>STATUS_DEVICE_NOT_CONNECTED or STATUS_DEVICE_DOES_NOT_EXIST</b></dt>
</dl>The device was not connected.

 

This method also might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.




## -remarks
For more information about the <b>WdfUsbTargetDeviceIsConnectedSynchronous</b> method and USB I/O targets, see <a href="https://msdn.microsoft.com/195c0f4b-7f33-428a-8de7-32643ad854c6">USB I/O Targets</a>.

The following code example determines if a specified USB device is connected.


## -see-also
<dl>
<dt>
<a href="..\wdfusb\nf-wdfusb-wdfusbtargetdevicecreatewithparameters.md">WdfUsbTargetDeviceCreateWithParameters</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfUsbTargetDeviceIsConnectedSynchronous method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

