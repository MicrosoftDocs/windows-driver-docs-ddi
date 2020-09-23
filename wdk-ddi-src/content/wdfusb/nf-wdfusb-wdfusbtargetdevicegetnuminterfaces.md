---
UID: NF:wdfusb.WdfUsbTargetDeviceGetNumInterfaces
title: WdfUsbTargetDeviceGetNumInterfaces function (wdfusb.h)
description: The WdfUsbTargetDeviceGetNumInterfaces method returns the number of USB device interfaces that are supported by a specified USB device.
old-location: wdf\wdfusbtargetdevicegetnuminterfaces.htm
tech.root: wdf
ms.assetid: d81bdeeb-07de-483d-9803-3577f1076e28
ms.date: 02/26/2018
keywords: ["WdfUsbTargetDeviceGetNumInterfaces function"]
ms.keywords: DFUsbRef_8819241f-cfcd-49de-8775-4f415ab63593.xml, WdfUsbTargetDeviceGetNumInterfaces, WdfUsbTargetDeviceGetNumInterfaces method, kmdf.wdfusbtargetdevicegetnuminterfaces, wdf.wdfusbtargetdevicegetnuminterfaces, wdfusb/WdfUsbTargetDeviceGetNumInterfaces
req.header: wdfusb.h
req.include-header: Wdfusb.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2, UsbKmdfIrql, UsbKmdfIrql2
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
 - WdfUsbTargetDeviceGetNumInterfaces
 - wdfusb/WdfUsbTargetDeviceGetNumInterfaces
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
 - WdfUsbTargetDeviceGetNumInterfaces
---

# WdfUsbTargetDeviceGetNumInterfaces function


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfUsbTargetDeviceGetNumInterfaces</b> method returns the number of USB device interfaces that are supported by a specified USB device.

## -parameters

### -param UsbDevice 

[in]
A handle to a USB device object that was obtained from a previous call to <a href="/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbtargetdevicecreatewithparameters">WdfUsbTargetDeviceCreateWithParameters</a>.

## -returns

<b>WdfUsbTargetDeviceGetNumInterfaces</b> returns the number of USB interfaces that the device supports.

A bug check occurs if a driver-supplied object handle is invalid.

## -remarks

For more information about the <b>WdfUsbTargetDeviceGetNumInterfaces</b> method and USB I/O targets, see <a href="/windows-hardware/drivers/wdf/usb-i-o-targets">USB I/O Targets</a>.


#### Examples

The following code example obtains the number of USB device interfaces that a specified USB device supports.

```cpp
UCHAR numInterfaces;

numInterfaces = WdfUsbTargetDeviceGetNumInterfaces(UsbDevice);
```

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbtargetdevicecreatewithparameters">WdfUsbTargetDeviceCreateWithParameters</a>