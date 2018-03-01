---
UID: NC:usbbusif.USBC_START_DEVICE_CALLBACK
title: USBC_START_DEVICE_CALLBACK
author: windows-driver-content
description: The USBC_START_DEVICE_CALLBACK routine allows a USB client driver to provide a custom definition of the interface collections on a device.
old-location: buses\usbc_start_device_callback.htm
old-project: usbref
ms.assetid: f9a9510a-b55c-4566-83ce-4ed7ccafb543
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: USBC_START_DEVICE_CALLBACK, UsbcStartDeviceCallback, UsbcStartDeviceCallback callback function [Buses], buses.usbc_start_device_callback, usbbusif/UsbcStartDeviceCallback, usbinterKR_d70617c5-be67-4660-9aa3-76b4c66c2616.xml
ms.prod: windows-hardware
ms.technology: windows-devices
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
product: Windows
targetos: Windows
req.typenames: USBD_VERSION_INFORMATION, *PUSBD_VERSION_INFORMATION
req.product: Windows 10 or later.
---

# USBC_START_DEVICE_CALLBACK callback


## -description


The <b>USBC_START_DEVICE_CALLBACK</b> routine allows a USB client driver to provide a custom definition of the interface collections on a device.


## -prototype


````
USBC_START_DEVICE_CALLBACK UsbcStartDeviceCallback;

NTSTATUS UsbcStartDeviceCallback(
  _In_  PUSB_DEVICE_DESCRIPTOR        DeviceDescriptor,
  _In_  PUSB_CONFIGURATION_DESCRIPTOR ConfigurationDescriptor,
  _Out_ PUSBC_FUNCTION_DESCRIPTOR     *FunctionDescriptorBuffer,
  _Out_ PULONG                        FunctionDescriptorBufferLength,
  _In_  PDEVICE_OBJECT                FdoDeviceObject,
  _In_  PDEVICE_OBJECT                PdoDeviceObject
)
{ ... }
````


## -parameters




### -param DeviceDescriptor [in]

The device descriptor of the device.


### -param ConfigurationDescriptor [in]

The configuration of the device.


### -param *FunctionDescriptorBuffer [out]

Pointer to a buffer that contains an array of function descriptors (<a href="..\usbbusif\ns-usbbusif-_usbc_function_descriptor.md">USBC_FUNCTION_DESCRIPTOR</a>).


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

<a href="..\usbbusif\ns-usbbusif-_usbc_device_configuration_interface_v1.md">USBC_DEVICE_CONFIGURATION_INTERFACE_V1</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20USBC_START_DEVICE_CALLBACK callback function%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

