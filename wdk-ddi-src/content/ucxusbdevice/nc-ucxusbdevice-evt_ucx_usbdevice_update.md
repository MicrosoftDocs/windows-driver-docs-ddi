---
UID: NC:ucxusbdevice.EVT_UCX_USBDEVICE_UPDATE
title: EVT_UCX_USBDEVICE_UPDATE
author: windows-driver-content
description: The client driver's implementation that UCX calls to update device properties.
old-location: buses\evt_ucx_usbdevice_update.htm
old-project: usbref
ms.assetid: 5dbf3560-9968-4996-8bce-fb43e3918d72
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: buses.evt_ucx_usbdevice_update, EvtUcxUsbDeviceUpdate callback function [Buses], EvtUcxUsbDeviceUpdate, EVT_UCX_USBDEVICE_UPDATE, EVT_UCX_USBDEVICE_UPDATE, ucxusbdevice/EvtUcxUsbDeviceUpdate, PEVT_UCX_USBDEVICE_UPDATE callback function pointer [Buses], PEVT_UCX_USBDEVICE_UPDATE
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
-	PEVT_UCX_USBDEVICE_UPDATE
product: Windows
targetos: Windows
req.typenames: *PSTREAM_INFO, STREAM_INFO
req.product: Windows 10 or later.
---

# EVT_UCX_USBDEVICE_UPDATE callback


## -description


The client driver's implementation that UCX calls to
    update device properties.


## -prototype


````
EVT_UCX_USBDEVICE_UPDATE EvtUcxUsbDeviceUpdate;

VOID EvtUcxUsbDeviceUpdate(
  _In_ UCXCONTROLLER UcxController,
  _In_ WDFREQUEST    Request
)
{ ... }

typedef EVT_UCX_USBDEVICE_UPDATE PEVT_UCX_USBDEVICE_UPDATE;
````


## -parameters




### -param UcxController [in]

 A handle to the UCX controller that the client driver received in a previous call to  the <a href="https://msdn.microsoft.com/library/windows/hardware/mt188033">UcxControllerCreate</a> method.


### -param Request [in]

Contains the <a href="..\ucxusbdevice\ns-ucxusbdevice-_usbdevice_update.md">USBDEVICE_UPDATE</a> structure.


## -returns


This callback function does not return a value.



## -remarks


The UCX client driver registers this callback function with the USB host controller extension (UCX) by calling the <a href="..\ucxusbdevice\nf-ucxusbdevice-ucxusbdevicecreate.md">UcxUsbDeviceCreate</a> method.

The host controller driver communicates with the hardware to update descriptors, LPM parameters, whether device is a hub, and
    maximum exit latency, as needed.

The client driver returns completion status in <i>Request</i>.  The driver can complete the WDFREQUEST asynchronously.



## -see-also

<a href="..\ucxusbdevice\nf-ucxusbdevice-ucxusbdevicecreate.md">UcxUsbDeviceCreate</a>

<a href="..\ucxusbdevice\nf-ucxusbdevice-ucx_usbdevice_event_callbacks_init.md">UCX_USBDEVICE_EVENT_CALLBACKS_INIT</a>

<a href="..\ucxusbdevice\ns-ucxusbdevice-_usbdevice_update.md">USBDEVICE_UPDATE</a>

<a href="..\ucxusbdevice\nf-ucxusbdevice-ucxusbdeviceinitseteventcallbacks.md">UcxUsbDeviceInitSetEventCallbacks</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20EVT_UCX_USBDEVICE_UPDATE callback function%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

