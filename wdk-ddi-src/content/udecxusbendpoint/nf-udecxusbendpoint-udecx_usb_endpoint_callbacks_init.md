---
UID: NF:udecxusbendpoint.UDECX_USB_ENDPOINT_CALLBACKS_INIT
title: UDECX_USB_ENDPOINT_CALLBACKS_INIT function
author: windows-driver-content
description: Initializes a UDECX_USB_ENDPOINT_CALLBACKS structure before a UdecxUsbEndpointCreate call.
old-location: buses\udecx_usb_endpoint_callbacks_init.htm
old-project: UsbRef
ms.assetid: AE0DA609-90E5-452F-B24E-0902C5E868A8
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: udecxusbendpoint/UDECX_USB_ENDPOINT_CALLBACKS_INIT, UDECX_USB_ENDPOINT_CALLBACKS_INIT, buses.udecx_usb_endpoint_callbacks_init, UDECX_USB_ENDPOINT_CALLBACKS_INIT method [Buses]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Udecxstub.lib
-	Udecxstub.dll
apiname:
-	UDECX_USB_ENDPOINT_CALLBACKS_INIT
product: Windows
targetos: Windows
req.typenames: UDECX_USB_ENDPOINT_INIT_AND_METADATA, *PUDECX_USB_ENDPOINT_INIT_AND_METADATA
req.product: Windows 10 or later.
---

# UDECX_USB_ENDPOINT_CALLBACKS_INIT function


## -description


Initializes a <a href="..\udecxusbendpoint\ns-udecxusbendpoint-_udecx_usb_endpoint_callbacks.md">UDECX_USB_ENDPOINT_CALLBACKS</a> structure before a <a href="..\udecxusbendpoint\nf-udecxusbendpoint-udecxusbendpointcreate.md">UdecxUsbEndpointCreate</a> call.


## -syntax


````
FORCEINLINE void UDECX_USB_ENDPOINT_CALLBACKS_INIT(
  _Out_ PUDECX_USB_ENDPOINT_CALLBACKS Callbacks
);
````


## -parameters




### -param Callbacks [out]

A pointer to a <a href="..\udecxusbendpoint\ns-udecxusbendpoint-_udecx_usb_endpoint_callbacks.md">UDECX_USB_ENDPOINT_CALLBACKS</a> to initialize.


### -param EvtUsbEndpointReset

TBD




## -returns



This method does not return a value.




## -see-also

<a href="..\udecxusbendpoint\nf-udecxusbendpoint-udecxusbendpointcreate.md">UdecxUsbEndpointCreate</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [UsbRef\buses]:%20UDECX_USB_ENDPOINT_CALLBACKS_INIT method%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

