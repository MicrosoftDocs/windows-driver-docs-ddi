---
UID: NE:wdfdevice._WDF_DEVICE_FAILED_ACTION
title: "_WDF_DEVICE_FAILED_ACTION"
author: windows-driver-content
description: The WDF_DEVICE_FAILED_ACTION enumeration identifies the action that the framework will take when a driver reports an unrecoverable software or hardware failure.
old-location: wdf\wdf_device_failed_action.htm
old-project: wdf
ms.assetid: 260fdda5-bc97-4522-96ca-1c29d41e8542
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFDeviceObjectGeneralRef_f23e41aa-e37c-45d0-b83b-0ee86eb24aba.xml, WDF_DEVICE_FAILED_ACTION, WDF_DEVICE_FAILED_ACTION enumeration, WdfDeviceFailedAttemptRestart, WdfDeviceFailedNoRestart, WdfDeviceFailedUndefined, _WDF_DEVICE_FAILED_ACTION, kmdf.wdf_device_failed_action, wdf.wdf_device_failed_action, wdfdevice/WDF_DEVICE_FAILED_ACTION, wdfdevice/WdfDeviceFailedAttemptRestart, wdfdevice/WdfDeviceFailedNoRestart, wdfdevice/WdfDeviceFailedUndefined
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Windows
req.target-min-winverclnt: 
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdfdevice.h
api_name:
-	WDF_DEVICE_FAILED_ACTION
product: Windows
targetos: Windows
req.typenames: WDF_DEVICE_FAILED_ACTION
---

# _WDF_DEVICE_FAILED_ACTION enumeration


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The WDF_DEVICE_FAILED_ACTION enumeration identifies the action that the framework will take when a driver reports an unrecoverable software or hardware failure.


## -enum-fields




### -field WdfDeviceFailedUndefined

For internal use only.


### -field WdfDeviceFailedAttemptRestart

Supported in KMDF and starting in UMDF version 2.15.  If the device's drivers are not supporting other devices that are plugged into the computer, the I/O manager unloads the drivers. Next, the Plug and Play manager attempts to restart the device by requesting the bus driver to reenumerate its devices. If the bus driver supports reenumeration, your driver will be reloaded, if it was unloaded. If several consecutive restart attempts fail (because the restarted driver again reports an error), the framework stops trying to restart the device.


### -field WdfDeviceFailedNoRestart

If the device's drivers are not supporting other devices on the system, the I/O manager unloads the drivers. 


## -remarks



The WDF_DEVICE_FAILED_ACTION enumeration is used as an input argument to <a href="https://msdn.microsoft.com/library/windows/hardware/ff546890">WdfDeviceSetFailed</a>.

Drivers typically specify <b>WdfDeviceFailedAttemptRestart</b> if they encounter an unrecoverable software error, because specifying this enumerator reloads the drivers. A driver might specify <b>WdfDeviceFailedNoRestart</b> if it encounters an unrecoverable hardware error that affects all of the driver's devices.

For information about specifying <b>WdfDeviceFailedAttemptRestart</b> in a UMDF driver, see the Remarks of <a href="https://msdn.microsoft.com/library/windows/hardware/ff546890">WdfDeviceSetFailed</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff546890">WdfDeviceSetFailed</a>
 

 

