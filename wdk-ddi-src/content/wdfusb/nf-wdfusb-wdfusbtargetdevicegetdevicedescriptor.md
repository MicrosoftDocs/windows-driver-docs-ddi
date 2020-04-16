---
UID: NF:wdfusb.WdfUsbTargetDeviceGetDeviceDescriptor
title: WdfUsbTargetDeviceGetDeviceDescriptor function (wdfusb.h)
description: The WdfUsbTargetDeviceGetDeviceDescriptor method retrieves the USB device descriptor for the USB device that is associated with a specified framework USB device object.
old-location: wdf\wdfusbtargetdevicegetdevicedescriptor.htm
tech.root: wdf
ms.assetid: b2c70976-00ce-4563-af60-0bbdd1a65540
ms.date: 02/26/2018
keywords: ["WdfUsbTargetDeviceGetDeviceDescriptor function"]
ms.keywords: DFUsbRef_a59d2f05-4ecf-400f-823e-b2d2533020a2.xml, WdfUsbTargetDeviceGetDeviceDescriptor, WdfUsbTargetDeviceGetDeviceDescriptor method, kmdf.wdfusbtargetdevicegetdevicedescriptor, wdf.wdfusbtargetdevicegetdevicedescriptor, wdfusb/WdfUsbTargetDeviceGetDeviceDescriptor
f1_keywords:
 - "wdfusb/WdfUsbTargetDeviceGetDeviceDescriptor"
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
req.irql: PASSIVE_LEVEL
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
- WdfUsbTargetDeviceGetDeviceDescriptor
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfUsbTargetDeviceGetDeviceDescriptor function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfUsbTargetDeviceGetDeviceDescriptor</b> method retrieves the USB device descriptor for the USB device that is associated with a specified framework USB device object.


## -parameters




### -param UsbDevice [in]

A handle to a USB device object that was obtained from a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbtargetdevicecreatewithparameters">WdfUsbTargetDeviceCreateWithParameters</a>.


### -param UsbDeviceDescriptor [out]

A pointer to a caller-allocated <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbspec/ns-usbspec-_usb_device_descriptor">USB_DEVICE_DESCRIPTOR</a> structure that receives the USB device descriptor.




## -remarks

A bug check occurs if a driver-supplied object handle is invalid.


For more information about the <b>WdfUsbTargetDeviceGetDeviceDescriptor</b> method and USB I/O targets, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/usb-i-o-targets">USB I/O Targets</a>.


#### Examples

The following code example obtains the USB device descriptor for a device. The example stores the descriptor in driver-defined context space.

```cpp
PMY_DEVICE_CONTEXT  myDeviceContext;

myDeviceContext = GetDeviceContext(device);

WdfUsbTargetDeviceGetDeviceDescriptor(
                                      myDeviceContext->UsbTargetDevice,
                                      &myDeviceContext->UsbDeviceDescr
                                      );
```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbspec/ns-usbspec-_usb_device_descriptor">USB_DEVICE_DESCRIPTOR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbtargetdevicecreatewithparameters">WdfUsbTargetDeviceCreateWithParameters</a>
 

 

