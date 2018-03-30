---
UID: NC:udecxusbdevice.EVT_UDECX_USB_DEVICE_ENDPOINTS_CONFIGURE
title: EVT_UDECX_USB_DEVICE_ENDPOINTS_CONFIGURE
author: windows-driver-content
description: The USB device emulation class extension (UdeCx) invokes this callback function to change the configuration by selecting an alternate setting, disabling current endpoints, or adding dynamic endpoints.
old-location: buses\evt_udecx_usb_device_endpoints_configure.htm
old-project: usbref
ms.assetid: 5E425011-BFC7-434C-9D0A-DB4481EC315F
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: EVT_UDECX_USB_DEVICE_ENDPOINTS_CONFIGURE, EvtUsbDeviceEndpointsConfigure, EvtUsbDeviceEndpointsConfigure callback function [Buses], buses.evt_udecx_usb_device_endpoints_configure, udecxusbdevice/EvtUsbDeviceEndpointsConfigure
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
req.lib: 
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	UdecxUsbDevice.h
api_name:
-	EvtUsbDeviceEndpointsConfigure
product: Windows
targetos: Windows
req.typenames: USB_DEVICE_PORT_PATH, *PUSB_DEVICE_PORT_PATH
req.product: Windows 10 or later.
---

# EVT_UDECX_USB_DEVICE_ENDPOINTS_CONFIGURE callback


## -description


The USB device emulation class extension (UdeCx) invokes this callback function to change the configuration by selecting an alternate setting, disabling current endpoints, or adding dynamic endpoints.


## -parameters




### -param UdecxUsbDevice [in]

A handle to UDE device object. The client driver created this object in a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/mt595959">UdecxUsbDeviceCreate</a>.


### -param Request [in]

A handle to a framework request object that represents the request.


### -param Params [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/mt627993">UDECX_ENDPOINTS_CONFIGURE_PARAMS</a> structure that describes the configuration options.


## -returns



This callback function does not return a value.




## -remarks



The client driver registered this callback function in a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/mt627972">UdecxUsbDeviceInitSetStateChangeCallbacks</a> by supplying a function pointer to its implementation.

The class extension invokes this  callback function to request the client driver to configure one or more new endpoints into hardware, and/or informs the driver when one or more existing endpoints is no longer being used. 

After creating endpoints, for each new endpoint, the client driver must call <a href="https://msdn.microsoft.com/library/windows/hardware/mt627988">UdecxUsbEndpointSetWdfIoQueue</a> before completing the request.


After releasing endpoints, the client driver should not use framework queue objects associated with the endpoints. The class extension considers those queues as purged to prevent future requests.


The class extension  can also request a new configuration value or an alternate setting through this callback.

This call is asynchronous. The client driver must signals completion with status by completing the request passed by the class extension. 





## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt595932">Architecture: USB Device Emulation (UDE)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt627988">UdecxUsbEndpointSetWdfIoQueue</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt595939">Write a UDE client driver</a>
 

 

