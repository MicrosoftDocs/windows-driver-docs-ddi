---
UID: NE:wdfcontrol._WDF_DEVICE_SHUTDOWN_FLAGS
title: "_WDF_DEVICE_SHUTDOWN_FLAGS"
author: windows-driver-content
description: The WDF_DEVICE_SHUTDOWN_FLAGS enumeration defines flags that identify types of shutdown notifications that a driver can receive.
old-location: wdf\wdf_device_shutdown_flags.htm
old-project: wdf
ms.assetid: e394f8de-7257-4baa-9057-bd4bad34212d
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFDeviceObjectControllerDevObjRef_67312956-1032-4272-9b69-ed1674b5e951.xml, WDF_DEVICE_SHUTDOWN_FLAGS, WDF_DEVICE_SHUTDOWN_FLAGS enumeration, WdfDeviceLastChanceShutdown, WdfDeviceShutdown, _WDF_DEVICE_SHUTDOWN_FLAGS, kmdf.wdf_device_shutdown_flags, wdf.wdf_device_shutdown_flags, wdfcontrol/WDF_DEVICE_SHUTDOWN_FLAGS, wdfcontrol/WdfDeviceLastChanceShutdown, wdfcontrol/WdfDeviceShutdown
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdfcontrol.h
api_name:
-	WDF_DEVICE_SHUTDOWN_FLAGS
product: Windows
targetos: Windows
req.typenames: WDF_DEVICE_SHUTDOWN_FLAGS
req.product: Windows 10 or later.
---

# _WDF_DEVICE_SHUTDOWN_FLAGS enumeration


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WDF_DEVICE_SHUTDOWN_FLAGS</b> enumeration defines flags that identify types of shutdown notifications that a driver can receive.


## -enum-fields




### -field WdfDeviceShutdown

The driver is notified when the system is losing its power, but before file systems are flushed.


### -field WdfDeviceLastChanceShutdown

The driver is notified when the system is losing its power, and after all file systems have been flushed.


## -remarks



The <b>WDF_DEVICE_SHUTDOWN_FLAGS</b> enumeration is used as an input parameter to <a href="https://msdn.microsoft.com/library/windows/hardware/ff545847">WdfControlDeviceInitSetShutdownNotification</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545847">WdfControlDeviceInitSetShutdownNotification</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_DEVICE_SHUTDOWN_FLAGS enumeration%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

