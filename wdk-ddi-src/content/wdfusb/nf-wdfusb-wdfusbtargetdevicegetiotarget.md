---
UID: NF:wdfusb.WdfUsbTargetDeviceGetIoTarget
title: WdfUsbTargetDeviceGetIoTarget function (wdfusb.h)
description: The WdfUsbTargetDeviceGetIoTarget method returns a handle to the I/O target object that is associated with a specified USB device.
old-location: wdf\wdfusbtargetdevicegetiotarget.htm
tech.root: wdf
ms.assetid: 8c598cb8-083a-459d-b94b-958b7d625c88
ms.date: 02/26/2018
keywords: ["WdfUsbTargetDeviceGetIoTarget function"]
ms.keywords: DFUsbRef_d65932cf-8891-4687-a784-eb6f794759fd.xml, WdfUsbTargetDeviceGetIoTarget, WdfUsbTargetDeviceGetIoTarget method, kmdf.wdfusbtargetdevicegetiotarget, wdf.wdfusbtargetdevicegetiotarget, wdfusb/WdfUsbTargetDeviceGetIoTarget
req.header: wdfusb.h
req.include-header: Wdfusb.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: <=DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - WdfUsbTargetDeviceGetIoTarget
 - wdfusb/WdfUsbTargetDeviceGetIoTarget
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Wdf01000.sys
 - Wdf01000.sys.dll
 - WUDFx02000.dll
 - WUDFx02000.dll.dll
api_name:
 - WdfUsbTargetDeviceGetIoTarget
---

# WdfUsbTargetDeviceGetIoTarget function


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfUsbTargetDeviceGetIoTarget</b> method returns a handle to the I/O target object that is associated with a specified USB device.

## -parameters

### -param UsbDevice 

[in]
A handle to a USB device object that was obtained from a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbtargetdevicecreatewithparameters">WdfUsbTargetDeviceCreateWithParameters</a>.

## -returns

The <b>WdfUsbTargetDeviceGetIoTarget</b> method returns a handle to an I/O target object.

A bug check occurs if a driver-supplied object handle is invalid.

## -remarks

For more information about the <b>WdfUsbTargetDeviceGetIoTarget</b> method and USB I/O targets, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/usb-i-o-targets">USB I/O Targets</a>.


#### Examples

The following code example creates a request object and verifies that the framework can send a request to the I/O target object that is associated with a specified USB device. 

```cpp
status = WdfRequestCreate(
                          &attributes,
                          WdfUsbTargetDeviceGetIoTarget(deviceContext->UsbTargetDevice),
                          &request
                          );
```

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbtargetdevicecreatewithparameters">WdfUsbTargetDeviceCreateWithParameters</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbtargetpipegetiotarget">WdfUsbTargetPipeGetIoTarget</a>

