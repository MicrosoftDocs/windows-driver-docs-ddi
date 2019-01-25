---
UID: NC:usbbusif.USBC_START_DEVICE_CALLBACK
title: USBC_START_DEVICE_CALLBACK (usbbusif.h)
description: The USBC_START_DEVICE_CALLBACK routine allows a USB client driver to provide a custom definition of the interface collections on a device.
old-location: buses\usbc_start_device_callback.htm
tech.root: usbref
ms.assetid: f9a9510a-b55c-4566-83ce-4ed7ccafb543
ms.date: 05/07/2018
ms.keywords: USBC_START_DEVICE_CALLBACK, USBC_START_DEVICE_CALLBACK callback, UsbcStartDeviceCallback, UsbcStartDeviceCallback callback function [Buses], buses.usbc_start_device_callback, usbbusif/UsbcStartDeviceCallback, usbinterKR_d70617c5-be67-4660-9aa3-76b4c66c2616.xml
ms.topic: callback
req.header: usbbusif.h
req.include-header: Usbbusif.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	usbbusif.h
api_name:
-	UsbcStartDeviceCallback
product:
- Windows
targetos: Windows
req.typenames: 
---

# USBC_START_DEVICE_CALLBACK callback function


## -description


The <b>USBC_START_DEVICE_CALLBACK</b> routine allows a USB client driver to provide a custom definition of the interface collections on a device.


## -parameters




### -param DeviceDescriptor [in]

The device descriptor of the device.


### -param ConfigurationDescriptor [in]

The configuration of the device.


### -param *FunctionDescriptorBuffer [out]

Pointer to a buffer that contains an array of function descriptors (<a href="https://msdn.microsoft.com/library/windows/hardware/ff539001">USBC_FUNCTION_DESCRIPTOR</a>).


### -param FunctionDescriptorBufferLength [out]

The length in bytes of the buffer that <i>FunctionDescriptorBuffer</i> points to.


### -param FdoDeviceObject [in]

The function device object for the device.


### -param PdoDeviceObject [in]

The physical device object for the device.


## -returns



If the operation succeeds, the vendor-supplied callback routine must return STATUS_SUCCESS.




## -remarks



For a general description of the callback routine mechanism, see <a href="https://msdn.microsoft.com/3cf4e9f2-ea33-491f-94af-62d2afacc899">Customizing Enumeration of Interface Collections for Composite Devices</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff538990">USBC_DEVICE_CONFIGURATION_INTERFACE_V1</a>
 

 

