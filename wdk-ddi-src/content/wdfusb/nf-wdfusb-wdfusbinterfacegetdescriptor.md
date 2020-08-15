---
UID: NF:wdfusb.WdfUsbInterfaceGetDescriptor
title: WdfUsbInterfaceGetDescriptor function (wdfusb.h)
description: The WdfUsbInterfaceGetDescriptor method retrieves the USB interface descriptor that is associated with a specified alternate setting of a specified USB interface.
old-location: wdf\wdfusbinterfacegetdescriptor.htm
tech.root: wdf
ms.assetid: 70156bfa-8271-42f6-9a22-0d0b77e63b66
ms.date: 02/26/2018
keywords: ["WdfUsbInterfaceGetDescriptor function"]
ms.keywords: DFUsbRef_eb98efa1-720d-408c-824f-59cfef80bbba.xml, WdfUsbInterfaceGetDescriptor, WdfUsbInterfaceGetDescriptor method, kmdf.wdfusbinterfacegetdescriptor, wdf.wdfusbinterfacegetdescriptor, wdfusb/WdfUsbInterfaceGetDescriptor
f1_keywords:
 - "wdfusb/WdfUsbInterfaceGetDescriptor"
 - "WdfUsbInterfaceGetDescriptor"
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
- WdfUsbInterfaceGetDescriptor
targetos: Windows
req.typenames: 
---

# WdfUsbInterfaceGetDescriptor function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfUsbInterfaceGetDescriptor</b> method retrieves the USB interface descriptor that is associated with a specified alternate setting of a specified USB interface.


## -parameters




### -param UsbInterface 
[in]
A handle to a USB interface object that was obtained by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbtargetdevicegetinterface">WdfUsbTargetDeviceGetInterface</a>. 


### -param SettingIndex 
[in]
An index value that identifies an alternate setting for the interface. For more information about alternate settings, see the USB specification.


### -param InterfaceDescriptor 
[out]
A pointer to a caller-allocated <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbspec/ns-usbspec-_usb_interface_descriptor">USB_INTERFACE_DESCRIPTOR</a> structure that the framework fills in.


## -remarks


If the <i>SettingIndex</i> value is invalid, the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbspec/ns-usbspec-_usb_interface_descriptor">USB_INTERFACE_DESCRIPTOR</a> structure can receive invalid data. 

A bug check occurs if the driver supplies an invalid object handle.




For more information about the <b>WdfUsbInterfaceGetDescriptor</b> method and USB I/O targets, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/usb-i-o-targets">USB I/O Targets</a>.


#### Examples

The following code example obtains the alternate setting index for a specified USB interface. Then, the example obtains the USB interface descriptor that represents the USB interface's current alternate setting.

```cpp
BYTE  settingIndex;
USB_INTERFACE_DESCRIPTOR  interfaceDescriptor;

settingIndex = WdfUsbInterfaceGetConfiguredSettingIndex(
                             UsbInterface
                             );

WdfUsbInterfaceGetDescriptor(
                             UsbInterface,
                             settingIndex,
                             &interfaceDescriptor
                             );
```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbspec/ns-usbspec-_usb_interface_descriptor">USB_INTERFACE_DESCRIPTOR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbtargetdevicegetinterface">WdfUsbTargetDeviceGetInterface</a>
 

 

