---
UID: NE:wdfcontrol._WDF_DEVICE_SHUTDOWN_FLAGS
title: "_WDF_DEVICE_SHUTDOWN_FLAGS"
author: windows-driver-content
description: The WDF_DEVICE_SHUTDOWN_FLAGS enumeration defines flags that identify types of shutdown notifications that a driver can receive.
old-location: wdf\wdf_device_shutdown_flags.htm
tech.root: wdf
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdfcontrol.h
api_name:
-	WDF_DEVICE_SHUTDOWN_FLAGS
product:
- Windows
targetos: Windows
req.typenames: WDF_DEVICE_SHUTDOWN_FLAGS
---

# _WDF_DEVICE_SHUTDOWN_FLAGS enumeration


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

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
 

 

