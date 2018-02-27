---
UID: NF:udecxusbdevice.UdecxUsbDeviceInitSetEndpointsType
title: UdecxUsbDeviceInitSetEndpointsType function
author: windows-driver-content
description: Indicates the type of endpoint (simple or dynamic) in the initialization parameters that the client driver uses to create the virtual USB device.
old-location: buses\udecxusbdeviceinitsetendpointstype.htm
old-project: usbref
ms.assetid: 44760191-77DD-40A9-AA11-AE8AB55AB307
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: UdecxUsbDeviceInitSetEndpointsType, UdecxUsbDeviceInitSetEndpointsType function [Buses], buses.udecxusbdeviceinitsetendpointstype, udecxusbdevice/UdecxUsbDeviceInitSetEndpointsType
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
-	UdecxUsbDeviceInitSetEndpointsType
product: Windows
targetos: Windows
req.typenames: UDECX_USB_DEVICE_WAKE_SETTING, *PUDECX_USB_DEVICE_WAKE_SETTING
req.product: Windows 10 or later.
---

# UdecxUsbDeviceInitSetEndpointsType function


## -description


Indicates the type of endpoint (simple or dynamic) in the initialization parameters that the client driver uses to create the virtual USB device.


## -syntax


````
void UdecxUsbDeviceInitSetEndpointsType(
  _Inout_ PUDECXUSBDEVICE_INIT UdecxUsbDeviceInit,
  _In_    UDECX_ENDPOINT_TYPE  UdecxEndpointType
);
````


## -parameters




### -param UdecxUsbDeviceInit [in, out]

A pointer to a WDF-allocated structure that contains initialization parameters for the virtual USB device.  The client driver retrieved this pointer in the previous call to <a href="..\udecxusbdevice\nf-udecxusbdevice-udecxusbdeviceinitallocate.md">UdecxUsbDeviceInitAllocate</a>. 


### -param UdecxEndpointType [in]

A <a href="..\udecxusbdevice\ne-udecxusbdevice-_udecx_endpoint_type.md">UDECX_ENDPOINT_TYPE</a>-type value that indicates the type of USB endpoint.


## -returns



This function does not return a value.




## -remarks



Before creating the virtual USB device, the client driver must indicate the type of endpoint it supports. It can support one of two types (defined in <a href="..\udecxusbdevice\ne-udecxusbdevice-_udecx_endpoint_type.md">UDECX_ENDPOINT_TYPE</a>): 

<ul>
<li>Simple endpoint-The client driver creates all endpoint objects before plugging in the device. The device must have only one configuration and one interface setting per interface.
</li>
<li>Dynamic endpoint-The client creates endpoint objects in the  <a href="..\udecxusbdevice\nc-udecxusbdevice-evt_udecx_usb_device_endpoints_configure.md">EVT_UDECX_USB_DEVICE_ENDPOINTS_CONFIGURE</a> callback function.
The USB device emulation  class extension (UdeCx) invokes the driver's implementation when it gets a request to add or configure endpoints.</li>
</ul>
The <i>UdecxUsbDeviceInit</i> is an opaque structure that contains pointers to callback functions related to endpoints. If the client driver supports dynamic endpoints, then these callback functions must be implemented by the driver:

<ul>
<li>
<a href="..\udecxusbdevice\nc-udecxusbdevice-evt_udecx_usb_device_endpoints_configure.md">EVT_UDECX_USB_DEVICE_ENDPOINTS_CONFIGURE</a>
</li>
<li>
<a href="..\udecxusbdevice\nc-udecxusbdevice-evt_udecx_usb_device_endpoint_add.md">EVT_UDECX_USB_DEVICE_ENDPOINT_ADD</a>
</li>
<li>
<a href="..\udecxusbdevice\nc-udecxusbdevice-evt_udecx_usb_device_default_endpoint_add.md">EVT_UDECX_USB_DEVICE_DEFAULT_ENDPOINT_ADD</a>
</li>
</ul>
Before calling this method, the client driver must have set those pointers by calling <a href="..\udecxusbdevice\nf-udecxusbdevice-udecxusbdeviceinitsetstatechangecallbacks.md">UdecxUsbDeviceInitSetStateChangeCallbacks</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/mt595939">Write a UDE client driver</a>



<a href="..\udecxusbdevice\nc-udecxusbdevice-evt_udecx_usb_device_endpoints_configure.md">EVT_UDECX_USB_DEVICE_ENDPOINTS_CONFIGURE</a>



<a href="https://msdn.microsoft.com/4DABCC96-F3F5-43D9-9BCF-A2663ED30137">USB endpoints</a>



<a href="..\udecxusbdevice\nf-udecxusbdevice-udecxusbdeviceinitsetstatechangecallbacks.md">UdecxUsbDeviceInitSetStateChangeCallbacks</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt595932">Architecture: USB Device Emulation (UDE)</a>



<a href="..\udecxusbdevice\nf-udecxusbdevice-udecxusbdeviceinitallocate.md">UdecxUsbDeviceInitAllocate</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UdecxUsbDeviceInitSetEndpointsType function%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

