---
UID: NA:udecxusbendpoint
ms.assetid: b5af0117-5777-396c-811e-a8a0369ac894
ms.author: windowsdriverdev
ms.date: 03/13/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Udecxusbendpoint.h header



This header is used by Universal Serial Bus(USB). For more information, see
- [Universal Serial Bus(USB)](../_usbref/index.md)

Udecxusbendpoint.h contain these programming interfaces:


## Functions

| Title   | Description   |
| ---- |:---- |
| [UDECX_USB_ENDPOINT_CALLBACKS_INIT function](nf-udecxusbendpoint-udecx_usb_endpoint_callbacks_init.md) | Initializes a UDECX_USB_ENDPOINT_CALLBACKS structure before a UdecxUsbEndpointCreate call. |
| [UdecxUsbEndpointCreate function](nf-udecxusbendpoint-udecxusbendpointcreate.md) | Creates a UDE endpoint object. |
| [UdecxUsbEndpointInitFree function](nf-udecxusbendpoint-udecxusbendpointinitfree.md) | Release the resources that were allocated by the UdecxUsbSimpleEndpointInitAllocate call. |
| [UdecxUsbEndpointInitSetCallbacks function](nf-udecxusbendpoint-udecxusbendpointinitsetcallbacks.md) | Sets pointers to UDE client driver-implemented callback functions in the initialization parameters of the simple endpoint to create. |
| [UdecxUsbEndpointInitSetEndpointAddress function](nf-udecxusbendpoint-udecxusbendpointinitsetendpointaddress.md) | Sets the address of the endpoint in the initialization parameters of the simple endpoint to create. |
| [UdecxUsbEndpointPurgeComplete function](nf-udecxusbendpoint-udecxusbendpointpurgecomplete.md) | Completes an asynchronous request for canceling all I/O requests queued to the specified endpoint. |
| [UdecxUsbEndpointSetWdfIoQueue function](nf-udecxusbendpoint-udecxusbendpointsetwdfioqueue.md) | Sets a framework queue object with a UDE endpoint. |
| [UdecxUsbSimpleEndpointInitAllocate function](nf-udecxusbendpoint-udecxusbsimpleendpointinitallocate.md) | Allocates memory for an initialization structure that is used to create a simple endpoint for the specified virtual USB device. |

## Callback functions

| Title   | Description   |
| ---- |:---- |
| [EVT_UDECX_USB_ENDPOINT_PURGE callback](nc-udecxusbendpoint-evt_udecx_usb_endpoint_purge.md) | The USB device emulation class extension (UdeCx) invokes this callback function to stop queuing I/O requests to the endpoint's queue and cancel unprocessed requests. |
| [EVT_UDECX_USB_ENDPOINT_RESET callback](nc-udecxusbendpoint-evt_udecx_usb_endpoint_reset.md) | The USB device emulation class extension (UdeCx) invokes this callback function to reset an endpoint of the virtual USB device. |
| [EVT_UDECX_USB_ENDPOINT_START callback](nc-udecxusbendpoint-evt_udecx_usb_endpoint_start.md) | The USB device emulation class extension (UdeCx) invokes this callback function to start processing I/O requests on the specified endpoint of the virtual USB device. |

## Structures

| Title   | Description   |
| ---- |:---- |
| [_UDECX_USB_ENDPOINT_CALLBACKS structure](ns-udecxusbendpoint-_udecx_usb_endpoint_callbacks.md) | Contains function pointers to endpoint callback functions implemented by the UDE client driver. Initialize this structure by calling UDECX_USB_ENDPOINT_CALLBACKS_INIT. |
