---
UID: NF:udecxusbendpoint.UDECX_USB_ENDPOINT_CALLBACKS_INIT
title: UDECX_USB_ENDPOINT_CALLBACKS_INIT function (udecxusbendpoint.h)
description: Initializes a UDECX_USB_ENDPOINT_CALLBACKS structure before a UdecxUsbEndpointCreate call.
old-location: buses\udecx_usb_endpoint_callbacks_init.htm
tech.root: usbref
ms.date: 09/13/2021
keywords: ["UDECX_USB_ENDPOINT_CALLBACKS_INIT function"]
ms.keywords: UDECX_USB_ENDPOINT_CALLBACKS_INIT, UDECX_USB_ENDPOINT_CALLBACKS_INIT method [Buses], buses.udecx_usb_endpoint_callbacks_init, udecxusbendpoint/UDECX_USB_ENDPOINT_CALLBACKS_INIT
req.header: udecxusbendpoint.h
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
targetos: Windows
req.typenames: 
f1_keywords:
 - UDECX_USB_ENDPOINT_CALLBACKS_INIT
 - udecxusbendpoint/UDECX_USB_ENDPOINT_CALLBACKS_INIT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Udecxstub.lib
 - Udecxstub.dll
api_name:
 - UDECX_USB_ENDPOINT_CALLBACKS_INIT
---

# UDECX_USB_ENDPOINT_CALLBACKS_INIT function

## -description

Initializes a [UDECX_USB_ENDPOINT_CALLBACKS](./ns-udecxusbendpoint-_udecx_usb_endpoint_callbacks.md) structure before a [UdecxUsbEndpointCreate](./nf-udecxusbendpoint-udecxusbendpointcreate.md) call.

## -parameters

### -param Callbacks

[out]
A pointer to a [UDECX_USB_ENDPOINT_CALLBACKS](./ns-udecxusbendpoint-_udecx_usb_endpoint_callbacks.md) to initialize.

### -param EvtUsbEndpointReset

Pointer to an [EVT_UDECX_USB_ENDPOINT_RESET](nc-udecxusbendpoint-evt_udecx_usb_endpoint_reset.md) callback function.

## -see-also

[UdecxUsbEndpointCreate](./nf-udecxusbendpoint-udecxusbendpointcreate.md)