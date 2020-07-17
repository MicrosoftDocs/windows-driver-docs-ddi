---
UID: NF:udecxusbendpoint.UDECX_USB_ENDPOINT_CALLBACKS_INIT
title: UDECX_USB_ENDPOINT_CALLBACKS_INIT function (udecxusbendpoint.h)
description: Initializes a UDECX_USB_ENDPOINT_CALLBACKS structure before a UdecxUsbEndpointCreate call.
old-location: buses\udecx_usb_endpoint_callbacks_init.htm
tech.root: usbref
ms.assetid: AE0DA609-90E5-452F-B24E-0902C5E868A8
ms.date: 05/07/2018
keywords: ["UDECX_USB_ENDPOINT_CALLBACKS_INIT function"]
ms.keywords: UDECX_USB_ENDPOINT_CALLBACKS_INIT, UDECX_USB_ENDPOINT_CALLBACKS_INIT method [Buses], buses.udecx_usb_endpoint_callbacks_init, udecxusbendpoint/UDECX_USB_ENDPOINT_CALLBACKS_INIT
f1_keywords:
 - "udecxusbendpoint/UDECX_USB_ENDPOINT_CALLBACKS_INIT"
 - "UDECX_USB_ENDPOINT_CALLBACKS_INIT"
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
product:
- Windows
targetos: Windows
req.typenames: 
---

# UDECX_USB_ENDPOINT_CALLBACKS_INIT function


## -description


Initializes a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/udecxusbendpoint/ns-udecxusbendpoint-_udecx_usb_endpoint_callbacks">UDECX_USB_ENDPOINT_CALLBACKS</a> structure before a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/udecxusbendpoint/nf-udecxusbendpoint-udecxusbendpointcreate">UdecxUsbEndpointCreate</a> call.


## -parameters




### -param Callbacks [out]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/udecxusbendpoint/ns-udecxusbendpoint-_udecx_usb_endpoint_callbacks">UDECX_USB_ENDPOINT_CALLBACKS</a> to initialize.


### -param EvtUsbEndpointReset

TBD




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/udecxusbendpoint/nf-udecxusbendpoint-udecxusbendpointcreate">UdecxUsbEndpointCreate</a>
 

 

