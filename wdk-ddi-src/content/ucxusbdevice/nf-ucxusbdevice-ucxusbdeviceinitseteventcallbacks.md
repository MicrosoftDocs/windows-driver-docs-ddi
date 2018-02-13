---
UID: NF:ucxusbdevice.UcxUsbDeviceInitSetEventCallbacks
title: UcxUsbDeviceInitSetEventCallbacks function
author: windows-driver-content
description: Initializes a UCXUSBDEVICE_INIT structure with client driver's event callback functions.
old-location: buses\_ucxusbdeviceinitseteventcallbacks.htm
old-project: usbref
ms.assetid: 913F96FD-9C51-4A45-86A9-8830E1A395EE
ms.author: windowsdriverdev
ms.date: 2/8/2018
ms.keywords: UcxUsbDeviceInitSetEventCallbacks, buses._ucxusbdeviceinitseteventcallbacks, UcxUsbDeviceInitSetEventCallbacks method [Buses]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	ucxusbdevice.h
apiname:
-	UcxUsbDeviceInitSetEventCallbacks
product: Windows
targetos: Windows
req.typenames: UCX_USBDEVICE_CHARACTERISTIC_TYPE
req.product: Windows 10 or later.
---

# UcxUsbDeviceInitSetEventCallbacks function


## -description


Initializes a <b>UCXUSBDEVICE_INIT</b> structure with client driver's event callback functions.


## -syntax


````
inline void UcxUsbDeviceInitSetEventCallbacks(
  [in, out] PUCXUSBDEVICE_INIT             UsbDeviceInit,
  [in]      PUCX_USBDEVICE_EVENT_CALLBACKS EventCallbacks
);
````


## -parameters




### -param UsbDeviceInit [in, out]

A pointer to a <b>UCXUSBDEVICE_INIT</b> structure that UCX passes when it invokes client driver's <a href="..\ucxcontroller\nc-ucxcontroller-evt_ucx_controller_usbdevice_add.md">EVT_UCX_CONTROLLER_USBDEVICE_ADD</a> 		event callback function. 


### -param EventCallbacks [in]

A pointer to a <a href="..\ucxusbdevice\ns-ucxusbdevice-_ucx_usbdevice_event_callbacks.md">UCX_USBDEVICE_EVENT_CALLBACKS</a> structure that contains function pointer to client driver's event callback functions. The  the client driver initializes the structure  by calling <a href="..\ucxusbdevice\nf-ucxusbdevice-ucx_usbdevice_event_callbacks_init.md">UCX_USBDEVICE_EVENT_CALLBACKS_INIT</a>.


## -returns



This method does not return a value.




## -remarks



An initialized <b>UCXUSBDEVICE_INIT</b> structure is used by the <a href="..\ucxusbdevice\nf-ucxusbdevice-ucxusbdevicecreate.md">UcxUsbDeviceCreate</a> method to create a USB device and register the client driver's event callback functions. 

For a code example, see <a href="..\ucxcontroller\nc-ucxcontroller-evt_ucx_controller_usbdevice_add.md">EVT_UCX_CONTROLLER_USBDEVICE_ADD</a>.




## -see-also

<a href="..\ucxusbdevice\nf-ucxusbdevice-ucxusbdevicecreate.md">UcxUsbDeviceCreate</a>



<a href="..\ucxusbdevice\ns-ucxusbdevice-_ucx_usbdevice_event_callbacks.md">UCX_USBDEVICE_EVENT_CALLBACKS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UcxUsbDeviceInitSetEventCallbacks method%20 RELEASE:%20(2/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

