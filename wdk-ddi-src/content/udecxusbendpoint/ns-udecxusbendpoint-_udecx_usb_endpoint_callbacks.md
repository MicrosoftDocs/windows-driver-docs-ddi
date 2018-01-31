---
UID: NS:udecxusbendpoint._UDECX_USB_ENDPOINT_CALLBACKS
title: "_UDECX_USB_ENDPOINT_CALLBACKS"
author: windows-driver-content
description: Contains function pointers to endpoint callback functions implemented by the UDE client driver. Initialize this structure by calling UDECX_USB_ENDPOINT_CALLBACKS_INIT.
old-location: buses\udecx_usb_endpoint_callbacks.htm
old-project: usbref
ms.assetid: 5AAB4474-9FDF-4ACF-AC38-F84D2682B5E0
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: "_UDECX_USB_ENDPOINT_CALLBACKS, udecxusbendpoint/PUDECX_USB_ENDPOINT_CALLBACKS, PUDECX_USB_ENDPOINT_CALLBACKS, udecxusbendpoint/UDECX_USB_ENDPOINT_CALLBACKS, PUDECX_USB_ENDPOINT_CALLBACKS structure pointer [Buses], *PUDECX_USB_ENDPOINT_CALLBACKS, buses.udecx_usb_endpoint_callbacks, UDECX_USB_ENDPOINT_CALLBACKS, UDECX_USB_ENDPOINT_CALLBACKS structure [Buses]"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	udecxusbendpoint.h
apiname:
-	UDECX_USB_ENDPOINT_CALLBACKS
product: Windows
targetos: Windows
req.typenames: "*PUDECX_USB_ENDPOINT_CALLBACKS, UDECX_USB_ENDPOINT_CALLBACKS"
req.product: Windows 10 or later.
---

# _UDECX_USB_ENDPOINT_CALLBACKS structure


## -description


Contains function pointers to endpoint callback functions implemented by the UDE client driver. Initialize this structure by calling <a href="..\udecxusbendpoint\nf-udecxusbendpoint-udecx_usb_endpoint_callbacks_init.md">UDECX_USB_ENDPOINT_CALLBACKS_INIT</a>.


## -syntax


````
typedef struct _UDECX_USB_ENDPOINT_CALLBACKS {
  ULONG                        Size;
  PFN_UDECX_USB_ENDPOINT_RESET EvtUsbEndpointReset;
  EVT_UDECX_USB_ENDPOINT_START EvtUsbEndpointStart;
  EVT_UDECX_USB_ENDPOINT_PURGE EvtUsbEndpointPurge;
} UDECX_USB_ENDPOINT_CALLBACKS, *PUDECX_USB_ENDPOINT_CALLBACKS;
````


## -struct-fields




#### - Size

The size of this structure.


#### - EvtUsbEndpointReset

Required. A pointer to an <a href="..\udecxusbendpoint\nc-udecxusbendpoint-evt_udecx_usb_endpoint_reset.md">EVT_UDECX_USB_ENDPOINT_RESET</a> callback function implemented by a UDE client driver.


#### - EvtUsbEndpointStart

Optional. A pointer to an <a href="..\udecxusbendpoint\nc-udecxusbendpoint-evt_udecx_usb_endpoint_start.md">EVT_UDECX_USB_ENDPOINT_START</a> callback function implemented by a UDE client driver.


#### - EvtUsbEndpointPurge

Optional. A pointer to an <a href="..\udecxusbendpoint\nc-udecxusbendpoint-evt_udecx_usb_endpoint_purge.md">EVT_UDECX_USB_ENDPOINT_PURGE</a> callback function implemented by a UDE client driver.


## -see-also

<a href="..\udecxusbendpoint\nf-udecxusbendpoint-udecxusbendpointcreate.md">UdecxUsbEndpointCreate</a>

<a href="..\udecxusbendpoint\nf-udecxusbendpoint-udecxusbendpointinitsetcallbacks.md">UdecxUsbEndpointInitSetCallbacks</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UDECX_USB_ENDPOINT_CALLBACKS structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

