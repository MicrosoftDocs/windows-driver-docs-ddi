---
UID: NF:ucxusbdevice.UcxUsbDeviceRemoteWakeNotification
title: UcxUsbDeviceRemoteWakeNotification function
author: windows-driver-content
description: Notifies UCX that a remote wake signal from the device is received.
old-location: buses\_ucxusbdeviceremotewakenotification.htm
old-project: usbref
ms.assetid: 0C95831F-2E20-461C-8478-9A40C1F063E2
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: UcxUsbDeviceRemoteWakeNotification, UcxUsbDeviceRemoteWakeNotification method [Buses], buses._ucxusbdeviceremotewakenotification, ucxusbdevice/UcxUsbDeviceRemoteWakeNotification
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
req.irql: "<=DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	ucxusbdevice.h
apiname:
-	UcxUsbDeviceRemoteWakeNotification
product: Windows
targetos: Windows
req.typenames: UCX_USBDEVICE_CHARACTERISTIC_TYPE
req.product: Windows 10 or later.
---

# UcxUsbDeviceRemoteWakeNotification function


## -description


Notifies UCX that a remote wake signal from the device is received.


## -syntax


````
void UcxUsbDeviceRemoteWakeNotification(
  [in] UCXUSBDEVICE UsbDevice,
  [in] ULONG        Interface
);
````


## -parameters




### -param UsbDevice [in]

A handle to the USB device object for which the remote wake is received. The client driver retrieved the handle in a previous call to <a href="..\ucxusbdevice\nf-ucxusbdevice-ucxusbdevicecreate.md">UcxUsbDeviceCreate</a>.


### -param Interface [in]

The interface number that sent the remote wake notification.


## -returns



This method does not return a value.




## -remarks



    This function completes the pending remote wake request from the request driver such as the hub driver or usbccgp driver. If no such request is found, this notification is ignored.





## -see-also

<a href="..\ucxusbdevice\nf-ucxusbdevice-ucxusbdevicecreate.md">UcxUsbDeviceCreate</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UcxUsbDeviceRemoteWakeNotification method%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

