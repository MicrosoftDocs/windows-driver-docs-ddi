---
UID: NC:ucxusbdevice.EVT_UCX_USBDEVICE_ADDRESS
title: EVT_UCX_USBDEVICE_ADDRESS
author: windows-driver-content
description: The client driver's implementation that UCX calls to address the USB device.
old-location: buses\evt_ucx_usbdevice_address.htm
old-project: usbref
ms.assetid: 48bda241-18b0-44c2-8e8b-7d3ecaad8a05
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: _STREAM_INFO, STREAM_INFO, *PSTREAM_INFO
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
req.alt-api: PEVT_UCX_USBDEVICE_ADDRESS
req.alt-loc: ucxusbdevice.h
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
req.typenames: STREAM_INFO, *PSTREAM_INFO
req.product: Windows 10 or later.
---

# EVT_UCX_USBDEVICE_ADDRESS callback



## -description
The client driver's implementation that UCX calls to address the USB device.



## -prototype

````
EVT_UCX_USBDEVICE_ADDRESS EvtUcxUsbDeviceAddress;

VOID EvtUcxUsbDeviceAddress(
  _In_ UCXCONTROLLER UcxController,
  _In_ WDFREQUEST    Request
)
{ ... }

typedef EVT_UCX_USBDEVICE_ADDRESS PEVT_UCX_USBDEVICE_ADDRESS;
````


## -parameters

### -param UcxController [in]

 A handle to the UCX controller that the client driver received in a previous call to  the <a href="https://msdn.microsoft.com/library/windows/hardware/mt188033">UcxControllerCreate</a> method.


### -param Request [in]

A structure of type <a href="..\ucxusbdevice\ns-ucxusbdevice-_usbdevice_address.md">USBDEVICE_ADDRESS</a>.


## -returns
This callback function does not return a value.


## -remarks
The UCX client driver registers this callback function with the USB host controller extension (UCX) by calling the <a href="..\ucxusbdevice\nf-ucxusbdevice-ucxusbdevicecreate.md">UcxUsbDeviceCreate</a> method.

The client driver returns completion status in <i>Request</i>.  The driver can complete the WDFREQUEST asynchronously.


## -see-also
<dl>
<dt>
<a href="..\ucxusbdevice\nf-ucxusbdevice-ucx_usbdevice_event_callbacks_init.md">UCX_USBDEVICE_EVENT_CALLBACKS_INIT</a>
</dt>
<dt>
<a href="..\ucxusbdevice\nf-ucxusbdevice-ucxusbdevicecreate.md">UcxUsbDeviceCreate</a>
</dt>
<dt>
<a href="..\ucxusbdevice\nf-ucxusbdevice-ucxusbdeviceinitseteventcallbacks.md">UcxUsbDeviceInitSetEventCallbacks</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20EVT_UCX_USBDEVICE_ADDRESS callback function%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

