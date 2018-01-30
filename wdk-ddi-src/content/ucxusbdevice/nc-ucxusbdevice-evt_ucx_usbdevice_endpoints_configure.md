---
UID: NC:ucxusbdevice.EVT_UCX_USBDEVICE_ENDPOINTS_CONFIGURE
title: EVT_UCX_USBDEVICE_ENDPOINTS_CONFIGURE
author: windows-driver-content
description: The client driver's implementation that UCX calls to configure endpoints in the controller.
old-location: buses\evt_ucx_usbdevice_endpoints_configure.htm
old-project: usbref
ms.assetid: 2f374912-985d-47e0-9fda-b43242375cb5
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: buses.evt_ucx_usbdevice_endpoints_configure, EvtUcxUsbDeviceEndpointsConfigure callback function [Buses], EvtUcxUsbDeviceEndpointsConfigure, EVT_UCX_USBDEVICE_ENDPOINTS_CONFIGURE, EVT_UCX_USBDEVICE_ENDPOINTS_CONFIGURE, ucxusbdevice/EvtUcxUsbDeviceEndpointsConfigure, PEVT_UCX_USBDEVICE_ENDPOINTS_CONFIGURE callback function pointer [Buses], PEVT_UCX_USBDEVICE_ENDPOINTS_CONFIGURE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ucxusbdevice.h
req.include-header: Ucxclass.h
req.target-type: Windows
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
req.lib: 
req.dll: 
req.irql: DISPATCH_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	ucxusbdevice.h
apiname:
-	PEVT_UCX_USBDEVICE_ENDPOINTS_CONFIGURE
product: Windows
targetos: Windows
req.typenames: STREAM_INFO, *PSTREAM_INFO
req.product: Windows 10 or later.
---

# EVT_UCX_USBDEVICE_ENDPOINTS_CONFIGURE callback


## -description


The client driver's implementation that UCX calls to configure endpoints in the controller.


## -prototype


````
EVT_UCX_USBDEVICE_ENDPOINTS_CONFIGURE EvtUcxUsbDeviceEndpointsConfigure;

VOID EvtUcxUsbDeviceEndpointsConfigure(
  _In_ UCXCONTROLLER UcxController,
  _In_ WDFREQUEST    Request
)
{ ... }

typedef EVT_UCX_USBDEVICE_ENDPOINTS_CONFIGURE PEVT_UCX_USBDEVICE_ENDPOINTS_CONFIGURE;
````


## -parameters




### -param UcxController [in]

 A handle to the UCX controller that the client driver received in a previous call to  the <a href="https://msdn.microsoft.com/library/windows/hardware/mt188033">UcxControllerCreate</a> method.


### -param Request [in]

Contains a structure of type <a href="..\ucxendpoint\ns-ucxendpoint-_endpoints_configure.md">ENDPOINTS_CONFIGURE</a> structure.


## -returns


This callback function does not return a value.



## -remarks


The UCX client driver registers this callback function with the USB host controller extension (UCX) by calling the <a href="..\ucxusbdevice\nf-ucxusbdevice-ucxusbdevicecreate.md">UcxUsbDeviceCreate</a> method.

In the callback, the driver programs or deprograms the endpoints, as described in the <a href="..\ucxendpoint\ns-ucxendpoint-_endpoints_configure.md">ENDPOINTS_CONFIGURE</a> structure.

This callback does not enable or disable the default endpoint. The default endpoint’s state is tied to the state of the device.   The driver implements enable and disable operations in the <a href="..\ucxusbdevice\nc-ucxusbdevice-evt_ucx_usbdevice_disable.md">EVT_UCX_USBDEVICE_DISABLE</a> and <a href="..\ucxusbdevice\nc-ucxusbdevice-evt_ucx_usbdevice_enable.md">EVT_UCX_USBDEVICE_ENABLE</a> callback functions.

The client driver returns completion status in <i>Request</i>.  The driver can complete the WDFREQUEST asynchronously.



## -see-also

<a href="..\ucxusbdevice\nf-ucxusbdevice-ucxusbdevicecreate.md">UcxUsbDeviceCreate</a>

<a href="..\ucxendpoint\ns-ucxendpoint-_endpoints_configure.md">ENDPOINTS_CONFIGURE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20EVT_UCX_USBDEVICE_ENDPOINTS_CONFIGURE callback function%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

