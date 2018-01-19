---
UID: NE:wdfcontrol._WDF_DEVICE_SHUTDOWN_FLAGS
title: _WDF_DEVICE_SHUTDOWN_FLAGS
author: windows-driver-content
description: The WDF_DEVICE_SHUTDOWN_FLAGS enumeration defines flags that identify types of shutdown notifications that a driver can receive.
old-location: wdf\wdf_device_shutdown_flags.htm
old-project: wdf
ms.assetid: e394f8de-7257-4baa-9057-bd4bad34212d
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _WDF_DEVICE_SHUTDOWN_FLAGS, WDF_DEVICE_SHUTDOWN_FLAGS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wdfcontrol.h
req.include-header: Wdf.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.alt-api: WDF_DEVICE_SHUTDOWN_FLAGS
req.alt-loc: wdfcontrol.h
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
req.typenames: WDF_DEVICE_SHUTDOWN_FLAGS
req.product: Windows 10 or later.
---

# _WDF_DEVICE_SHUTDOWN_FLAGS enumeration



## -description
<p class="CCE_Message">[Applies to KMDF only]

The <b>WDF_DEVICE_SHUTDOWN_FLAGS</b> enumeration defines flags that identify types of shutdown notifications that a driver can receive.



## -syntax

````
typedef enum _WDF_DEVICE_SHUTDOWN_FLAGS { 
  WdfDeviceShutdown            = 0x01,
  WdfDeviceLastChanceShutdown  = 0x02
} WDF_DEVICE_SHUTDOWN_FLAGS;
````


## -enum-fields

### -field WdfDeviceShutdown

The driver is notified when the system is losing its power, but before file systems are flushed.


### -field WdfDeviceLastChanceShutdown

The driver is notified when the system is losing its power, and after all file systems have been flushed.


## -remarks
The <b>WDF_DEVICE_SHUTDOWN_FLAGS</b> enumeration is used as an input parameter to <a href="..\wdfcontrol\nf-wdfcontrol-wdfcontroldeviceinitsetshutdownnotification.md">WdfControlDeviceInitSetShutdownNotification</a>.


## -see-also
<dl>
<dt>
<a href="..\wdfcontrol\nf-wdfcontrol-wdfcontroldeviceinitsetshutdownnotification.md">WdfControlDeviceInitSetShutdownNotification</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_DEVICE_SHUTDOWN_FLAGS enumeration%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

