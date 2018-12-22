---
UID: NF:ucxusbdevice.UcxUsbDeviceRemoteWakeNotification
title: UcxUsbDeviceRemoteWakeNotification function
description: Notifies UCX that a remote wake signal from the device is received.
old-location: buses\_ucxusbdeviceremotewakenotification.htm
tech.root: usbref
ms.assetid: 0C95831F-2E20-461C-8478-9A40C1F063E2
ms.date: 05/07/2018
ms.keywords: UcxUsbDeviceRemoteWakeNotification, UcxUsbDeviceRemoteWakeNotification method [Buses], buses._ucxusbdeviceremotewakenotification, ucxusbdevice/UcxUsbDeviceRemoteWakeNotification
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
req.lib: 
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	ucxusbdevice.h
api_name:
-	UcxUsbDeviceRemoteWakeNotification
product:
- Windows
targetos: Windows
req.typenames: 
---

# UcxUsbDeviceRemoteWakeNotification function


## -description


Notifies UCX that a remote wake signal from the device is received.


## -parameters




### -param UsbDevice [in]

A handle to the USB device object for which the remote wake is received. The client driver retrieved the handle in a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/mt188052">UcxUsbDeviceCreate</a>.


### -param Interface [in]

The interface number that sent the remote wake notification.


## -returns



This method does not return a value.




## -remarks



    This function completes the pending remote wake request from the request driver such as the hub driver or usbccgp driver. If no such request is found, this notification is ignored.





## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt188052">UcxUsbDeviceCreate</a>
 

 

