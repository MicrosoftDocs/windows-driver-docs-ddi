---
UID: NS:udecxusbendpoint._UDECX_USB_ENDPOINT_CALLBACKS
title: _UDECX_USB_ENDPOINT_CALLBACKS (udecxusbendpoint.h)
description: Contains function pointers to endpoint callback functions implemented by the UDE client driver. Initialize this structure by calling UDECX_USB_ENDPOINT_CALLBACKS_INIT.
old-location: buses\udecx_usb_endpoint_callbacks.htm
tech.root: usbref
ms.assetid: 5AAB4474-9FDF-4ACF-AC38-F84D2682B5E0
ms.date: 05/07/2018
ms.keywords: "*PUDECX_USB_ENDPOINT_CALLBACKS, PUDECX_USB_ENDPOINT_CALLBACKS, PUDECX_USB_ENDPOINT_CALLBACKS structure pointer [Buses], UDECX_USB_ENDPOINT_CALLBACKS, UDECX_USB_ENDPOINT_CALLBACKS structure [Buses], _UDECX_USB_ENDPOINT_CALLBACKS, buses.udecx_usb_endpoint_callbacks, udecxusbendpoint/PUDECX_USB_ENDPOINT_CALLBACKS, udecxusbendpoint/UDECX_USB_ENDPOINT_CALLBACKS"
ms.topic: struct
f1_keywords:
 - "udecxusbendpoint/UDECX_USB_ENDPOINT_CALLBACKS"
req.header: udecxusbendpoint.h
req.include-header: Udecx.h
req.target-type: Windows
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- udecxusbendpoint.h
api_name:
- UDECX_USB_ENDPOINT_CALLBACKS
product:
- Windows
targetos: Windows
req.typenames: UDECX_USB_ENDPOINT_CALLBACKS, *PUDECX_USB_ENDPOINT_CALLBACKS
---

# _UDECX_USB_ENDPOINT_CALLBACKS structure


## -description


Contains function pointers to endpoint callback functions implemented by the UDE client driver. Initialize this structure by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/udecxusbendpoint/nf-udecxusbendpoint-udecx_usb_endpoint_callbacks_init">UDECX_USB_ENDPOINT_CALLBACKS_INIT</a>.


## -struct-fields




### -field Size

The size of this structure.


### -field EvtUsbEndpointReset

Required. A pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/udecxusbendpoint/nc-udecxusbendpoint-evt_udecx_usb_endpoint_reset">EVT_UDECX_USB_ENDPOINT_RESET</a> callback function implemented by a UDE client driver.


### -field EvtUsbEndpointStart

Optional. A pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/udecxusbendpoint/nc-udecxusbendpoint-evt_udecx_usb_endpoint_start">EVT_UDECX_USB_ENDPOINT_START</a> callback function implemented by a UDE client driver.


### -field EvtUsbEndpointPurge

Optional. A pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/udecxusbendpoint/nc-udecxusbendpoint-evt_udecx_usb_endpoint_purge">EVT_UDECX_USB_ENDPOINT_PURGE</a> callback function implemented by a UDE client driver.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/udecxusbendpoint/nf-udecxusbendpoint-udecxusbendpointcreate">UdecxUsbEndpointCreate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/udecxusbendpoint/nf-udecxusbendpoint-udecxusbendpointinitsetcallbacks">UdecxUsbEndpointInitSetCallbacks</a>
 

 

