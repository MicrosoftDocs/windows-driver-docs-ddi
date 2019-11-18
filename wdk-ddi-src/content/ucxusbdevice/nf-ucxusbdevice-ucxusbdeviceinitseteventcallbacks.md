---
UID: NF:ucxusbdevice.UcxUsbDeviceInitSetEventCallbacks
title: UcxUsbDeviceInitSetEventCallbacks function (ucxusbdevice.h)
description: Initializes a UCXUSBDEVICE_INIT structure with client driver's event callback functions.
old-location: buses\_ucxusbdeviceinitseteventcallbacks.htm
tech.root: usbref
ms.assetid: 913F96FD-9C51-4A45-86A9-8830E1A395EE
ms.date: 05/07/2018
ms.keywords: UcxUsbDeviceInitSetEventCallbacks, UcxUsbDeviceInitSetEventCallbacks method [Buses], buses._ucxusbdeviceinitseteventcallbacks
ms.topic: function
f1_keywords:
 - "ucxusbdevice/UcxUsbDeviceInitSetEventCallbacks"
req.header: ucxusbdevice.h
req.include-header: Ucxclass.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- ucxusbdevice.h
api_name:
- UcxUsbDeviceInitSetEventCallbacks
product:
- Windows
targetos: Windows
req.typenames: 
---

# UcxUsbDeviceInitSetEventCallbacks function


## -description


Initializes a <b>UCXUSBDEVICE_INIT</b> structure with client driver's event callback functions.


## -parameters




### -param UsbDeviceInit [in, out]

A pointer to a <b>UCXUSBDEVICE_INIT</b> structure that UCX passes when it invokes client driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucxcontroller/nc-ucxcontroller-evt_ucx_controller_usbdevice_add">EVT_UCX_CONTROLLER_USBDEVICE_ADD</a> 		event callback function. 


### -param EventCallbacks [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucxusbdevice/ns-ucxusbdevice-_ucx_usbdevice_event_callbacks">UCX_USBDEVICE_EVENT_CALLBACKS</a> structure that contains function pointer to client driver's event callback functions. The client driver initializes the structure  by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucxusbdevice/nf-ucxusbdevice-ucx_usbdevice_event_callbacks_init">UCX_USBDEVICE_EVENT_CALLBACKS_INIT</a>.


## -remarks



An initialized <b>UCXUSBDEVICE_INIT</b> structure is used by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucxusbdevice/nf-ucxusbdevice-ucxusbdevicecreate">UcxUsbDeviceCreate</a> method to create a USB device and register the client driver's event callback functions. 

For a code example, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucxcontroller/nc-ucxcontroller-evt_ucx_controller_usbdevice_add">EVT_UCX_CONTROLLER_USBDEVICE_ADD</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucxusbdevice/ns-ucxusbdevice-_ucx_usbdevice_event_callbacks">UCX_USBDEVICE_EVENT_CALLBACKS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucxusbdevice/nf-ucxusbdevice-ucxusbdevicecreate">UcxUsbDeviceCreate</a>
 

 

