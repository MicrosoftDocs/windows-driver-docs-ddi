---
UID: NF:wdfcontrol.WdfControlDeviceInitSetShutdownNotification
title: WdfControlDeviceInitSetShutdownNotification function
author: windows-driver-content
description: The WdfControlDeviceInitSetShutdownNotification method sets shutdown notification information for a control device object.
old-location: wdf\wdfcontroldeviceinitsetshutdownnotification.htm
old-project: wdf
ms.assetid: 43a5a017-f5de-4906-acbb-96419b4a3f1c
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFDeviceObjectControllerDevObjRef_ee736de4-6e27-46d9-8f83-40d7368c960a.xml, WdfControlDeviceInitSetShutdownNotification, WdfControlDeviceInitSetShutdownNotification method, kmdf.wdfcontroldeviceinitsetshutdownnotification, wdf.wdfcontroldeviceinitsetshutdownnotification, wdfcontrol/WdfControlDeviceInitSetShutdownNotification
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfcontrol.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: ControlDeviceInitAPI, DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
api_name:
-	WdfControlDeviceInitSetShutdownNotification
product:
- Windows
targetos: Windows
req.typenames: WDF_DEVICE_SHUTDOWN_FLAGS
req.product: Windows 10 or later.
---

# WdfControlDeviceInitSetShutdownNotification function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfControlDeviceInitSetShutdownNotification</b> method sets shutdown notification information for a control device object.


## -parameters




### -param DeviceInit [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff546951">WDFDEVICE_INIT</a> structure that the driver obtained by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff545841">WdfControlDeviceInitAllocate</a>.


### -param Notification [in]

A pointer to the driver's <a href="https://msdn.microsoft.com/365e669b-b4a1-432a-ab0c-9292a910256e">EvtDeviceShutdownNotification</a> event callback function.


### -param Flags [in]

One or more <a href="https://msdn.microsoft.com/library/windows/hardware/ff551282">WDF_DEVICE_SHUTDOWN_FLAGS</a>-typed flags that indicate when the <a href="https://msdn.microsoft.com/365e669b-b4a1-432a-ab0c-9292a910256e">EvtDeviceShutdownNotification</a> callback function will be called.


## -returns



None




## -remarks



The driver must call <b>WdfControlDeviceInitSetShutdownNotification</b> before calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff545926">WdfDeviceCreate</a>. For more information about calling <b>WdfControlDeviceInitSetShutdownNotification</b>, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-control-device-objects">Using Control Device Objects</a>.


#### Examples

For a code example that uses <b>WdfControlDeviceInitSetShutdownNotification</b>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff545841">WdfControlDeviceInitAllocate</a>.

<div class="code"></div>



## -see-also




<a href="https://msdn.microsoft.com/365e669b-b4a1-432a-ab0c-9292a910256e">EvtDeviceShutdownNotification</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546951">WDFDEVICE_INIT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551282">WDF_DEVICE_SHUTDOWN_FLAGS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545926">WdfDeviceCreate</a>
 

 

